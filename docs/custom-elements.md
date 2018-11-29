# Interactive Content Creation

## Slides

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

## Anchors

Anchors are simple links elements

- They can appear anywhere
    - i.e. standalone or inside other elements
- Anchors are inline elements
    - i.e. they do not make a new line
- Anchors can be self-closed

### Attributes

- Anchors support two attributes:
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

## Images

## Code tasks