## Slides ([slide])

For organizational purpose of slides, read [Slides](organizational_elements/slides)

- A slide is a outer element
    - It cannot be nested and cannot be present into another elements
- Each slide must start with a title (`# Title`)
    - This is the title of the slide and appears in the lesson navigation
- Elements into a slide must not be intented
    - i.e. No unnecessary whitespace left of its nested elements

### Attributes

The slide element has no attributes

### Exampes

```
[slide]
# Slide title
<!-- Other elements -->
[/slide]
```

## Anchors ([anchor])

Anchors are simple links elements

- They can appear anywhere
    - i.e. standalone or inside other elements
- Anchors are inline elements
    - i.e. they do not make a new line
- Anchors can be self-closed

### Attributes

Anchors support two attributes:
- `href` sets the location of the anchor
- `title` sets the hover text of an anchor

### Examples

```
[anchor href=http://google.com ]google[/anchor]
<!-- the whitespace before the closing ] is mandatory here, otherwise the anchor will be considered self-closing -->
[anchor href=http://google.com/ ]google[/anchor]
[anchor href="http://google.com/"]google[/anchor]
[anchor href="http://google.com/" title="Link to google" ]google[/anchor]
[anchor href="http://google.com/" title=google ]google[/anchor]
```

## Images ([image])

Images show images
- They can appear anywhere
- i.e. standalone or inside other elements
- Images can be self-closed

### Attributes

Images support single attribute:
- `src` sets the location of the image

### Examples


```
[image src="http://link-to-image" /]
[image src="http://link-to-image"][/image]
```

## Code tasks ([code-task])

Code tasks define a task to be executed by the judge.

### Attributes

Code tasks has the following attributes:
-   `title` sets the title of the task
-   `executionStrategy` sets the execution strategy
    -   i.e. how the code to be executed
    - Possible values are `csharp-dot-net-core-code` and `csharp-code`
-   `requiresInput` is set when reading from the standart input is required
    -   optional
        
### Nested elements

Code task can have only the following nested elements:

-   [\[code-editor\]](#code-editor-code-editor)
    - Here users write their code
    - Mandatory
-   [\[task-description\]](#task-description-task-description)
    - The description of the code task
    - Mandatory
-   [\[code-io\]](#code-inputoutput-code-io)
    - Add this element when the user needs IO (standart input/output)
    - Optional

### Examples

```
[code-task title="Calculating the area of a square" executionStrategy="csharp-dot-net-core-code" requiresInput]
[code-editor ...] [/code-editor]
[task-description] [/task-description]
[/code-task]

[code-task title="Calculating the area of a square" executionStrategy="csharp-code"]
[code-editor ...] [/code-editor]
[task-description] [/task-description]
[code-io /]
[/code-task]

[code-task title="Calculating the area of a square" executionStrategy="csharp-dot-net-core-code" requiresInput]
[code-editor ...] [/code-editor]
[task-description] [/task-description]
[code-io /]
[/code-task]
```

## Code editor ([code-editor])

The code editor is the element, where users write their code

### Attributes

Code editor support single attribute:
- `language` sets the language type
    -   Possible values are: `csharp`

Code editor can contain predifined code

### Examples


```
[code-editor language=csharp]
[/code-editor]

[code-editor language=csharp]
using System;
public class App
{
    public static void Main()
    {
        // Write your code here
    }
}
[/code-editor]


[code-editor language=csharp]
using System;
public class App
{
    public static void Main()
    {
        var a = int.Parse(Console.ReadLine());
        var square = ; // calculate the square of `a`
    }
}
[/code-editor]
```

## Task description ([task-description])

Task description holds the description of the task.
It can contains any custom elements and valid markdown

### Attributes

Task description has no attributes

### Examples

```
[task-description]
Read a number from the console and calculate its square
[/task-description]

[task-description]
Read a **number** from the console and calculate its logarithm.

Use [anchor href="https://en.wikipedia.org/wiki/Logarithm"]Wikipedia[/anchor] for refference
[/task-description]
```

## Code Input/Output ([code-io])

Code Input/Output has two behaviors:
- Sets what to be read from the console
    - This works, when the parent `[code-task]` has attribute `requiresInput`
- Prints the result from the execution of the code

### Attributes

Code input/output has no attributes

### Examples

```
[code-io /]
[code-io][/code-io]
```