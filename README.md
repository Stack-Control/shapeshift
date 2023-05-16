# Shapeshift

Shapeshift is a Symfony Bundle and a powerful templating language built on top of Twig. 

## What it does

With Shapeshift you can express HTML in a simplified way using JSON markup. Shapeshift then processes the data to populate predefined HTML blocks (we call them shapes). You can use out-of-box shapes or define your own. You can even combine multiple shapes to code a full template for a webpage.

## The Benefits
The JSON markup is generally more expressive and flexible, making it easier for you to generate markup programmatically. Shapes can also be stored in databases, making it suitable for website builders or user-generated content. Design and layout tweaks can then be implemented, without updating (possibly thousands of) datasets.

## Usage

You can easily define a shape, for example:

```jsonc
// src/shapes/foo.shape

{
  "name": "My first shape",
  "type": "p",
  "options": null,
  "content": "The future belongs to those who believe in the beauty of their dreams."
}
```

Shapeshift would compile this to:

```html
<p>The future belongs to those who believe in the beauty of their dreams.</p>
```

A more complex shape could look similar to this:

```jsonc
// src/shapes/foo.shape
{
  "name": "A complex shape",
  "type": "shapeshift.complex_shape",
  "options": null,
  "content": {
    "headline": "The future belongs to those who believe in the beauty of their dreams.",
    "img": "...",
    "cta": "...",
    "action": "..."
}
```

Shapeshift could compile this to:

```html
<div class="a-card">
  <h1>The future belongs to those who believe in the beauty of their dreams.</h1>
  <img src="..." alt="..." class="a-card-img" />
  <a href="..." class="a-card-btn">...</a>
</div>
```





