# Builder pattern
## Purpose for using it
* some objects are simple and can be created in a single constructor call
* other objects require a lot of ceremony to create
* having an object with 10 constructor arguments is not productive
  * eg instead of concatenating multiple strings, use a string builder instead
* instead, opt for piecewise construction
  * eg allow people to construct objects piece by piece
* builder provides an API for constructing an object step by step
### summary: A builder is essentially a separate component, so when piecewise object construction is complicated, provide an API for doing it succinctly
## Why do we need it
* because sometimes you just want a bit of convenience when building up objects
  * especially if those objects are complicated
## example
* the following is an example of not creating a html builder
  * resulting in a tedious method of creating a html
```c#
public class Program {
  public static void Main() {
    string hello = "hello";
    // StringBuilder is a type of builder to build strings
    System.Text.StringBuilder sb = new System.Text.StringBuilder();
    sb.Append("<p>");
    sb.Append(hello);
    sb.Append("</p>");
    System.Console.WriteLine(sb);

    string[] words = new[] {"Hello", "World"};
    sb.Clear();
    sb.Append("<ul>");
    foreach (string word in words)
      sb.AppendFormat($"<li>{word}</li>");
    sb.Append("</ul>");
    System.Console.WriteLine(sb);
    /*
    <p>hello</p>
    <ul><li>Hello</li><li>World</li></ul>
    */
  }
}
```
* Creating a html builder
```c#
using System.Collections.Generic;

public class HtmlElement {
  public string Name, Text;
  public List<HtmlElement> Elements = new List<HtmlElement>();
  private const int indentSize = 2;

  public HtmlElement() {
  }

  public HtmlElement(string name, string text) {
    Name = name ?? throw new System.ArgumentNullException(paramName: nameof(name));
    Text = text ?? throw new System.ArgumentNullException(paramName: nameof(text));
  }

  private string ToStringImpl(int indent) {
    System.Text.StringBuilder sb = new System.Text.StringBuilder();
    string i = new string(' ', indentSize * indent);
    sb.AppendLine($"{i}<{Name}>");

    if (!string.IsNullOrWhiteSpace(Text)) {
      sb.Append(new string(' ', indentSize * (indent + 1)));
      sb.AppendLine(Text);
    }

    foreach (var e in Elements) {
      sb.Append(e.ToStringImpl(indent + 1));
    }
    sb.AppendLine($"{i}</{Name}>");
    return sb.ToString();
  }

  public override string ToString() {
    return ToStringImpl(0);
  }
}

public class HtmlBuilder {
  private readonly string rootName;
  HtmlElement root = new HtmlElement();

  public HtmlBuilder(string rootName) {
    this.rootName = rootName;
    root.Name = rootName;
  }

  public void AddChild(string childName, string childText) {
    HtmlElement e = new HtmlElement(childName, childText);
    root.Elements.Add(e);
  }

  public override string ToString() {
    return root.ToString();
  }

  public void Clear() {
    root = new HtmlElement{Name = rootName};
  }
}

public class Program {
  public static void Main() {
    HtmlBuilder builder = new HtmlBuilder("ul");
    builder.AddChild("li", "hello");
    builder.AddChild("li", "world");
    System.Console.WriteLine(builder.ToString());
    /*
    <ul>
      <li>
        hello
      </li>
      <li>
        world
      </li>
    </ul>
    */
  }
}
```
* Fluent builder
  * enable chaining of methods
```c#
using System.Collections.Generic;

public class HtmlElement {
  public string Name, Text;
  public List<HtmlElement> Elements = new List<HtmlElement>();
  private const int indentSize = 2;

  public HtmlElement() {
  }

  public HtmlElement(string name, string text) {
    Name = name ?? throw new System.ArgumentNullException(paramName: nameof(name));
    Text = text ?? throw new System.ArgumentNullException(paramName: nameof(text));
  }

  private string ToStringImpl(int indent) {
    System.Text.StringBuilder sb = new System.Text.StringBuilder();
    string i = new string(' ', indentSize * indent);
    sb.AppendLine($"{i}<{Name}>");

    if (!string.IsNullOrWhiteSpace(Text)) {
      sb.Append(new string(' ', indentSize * (indent + 1)));
      sb.AppendLine(Text);
    }

    foreach (var e in Elements) {
      sb.Append(e.ToStringImpl(indent + 1));
    }
    sb.AppendLine($"{i}</{Name}>");
    return sb.ToString();
  }

  public override string ToString() {
    return ToStringImpl(0);
  }
}

public class HtmlBuilder {
  private readonly string rootName;
  HtmlElement root = new HtmlElement();

  public HtmlBuilder(string rootName) {
    this.rootName = rootName;
    root.Name = rootName;
  }

  // change void to HtmlBuilder to return this object
  public HtmlBuilder AddChild(string childName, string childText) {
    HtmlElement e = new HtmlElement(childName, childText);
    root.Elements.Add(e);
    return this;
  }

  public override string ToString() {
    return root.ToString();
  }

  public void Clear() {
    root = new HtmlElement{Name = rootName};
  }
}

public class Program {
  public static void Main() {
    HtmlBuilder builder = new HtmlBuilder("ul");
    builder.AddChild("li", "hello").AddChild("li", "world");
    System.Console.WriteLine(builder.ToString());
  }
}
```
* Fluent Builder inheritance with recursive generics
* Functional Builder
* Faceted Builder
