# CSS



## The Basics

Google [Fonts](https://fonts.google.com/) can be imported with

```html
<link href="https://fonts.googleapis.com/css?family=Lobster" rel="stylesheet" type="text/css">
```

This can be referenced with `font-family: FAMILY_NAME, GENERIC_NAME;`.  The `GENERIC_NAME` is used as a fallback to one of the fonts available in most browsers:

- monospace
- serif
- sans-serif

Edges can be smoothed with `border-radius`

```css
 .thick-green-border {
      border-color: green;
      border-width: 10px;
      border-style: solid;
      border-radius: 10px;
 }
```

A `border-radius` of 50% creates a circle

**Clockwise Notation**

You can provide margin/padding values for all sides on a single line.  This is effectively top, right, bottom, left.

```css
padding: 10px 20px 10px 20px;
```

Also possible to use the`[attr=value]` attribute selector to apply a style

```css
[type='radio'] {
  margin: 20px 0px 20px 0px;
}
```

**Absolute vs Relative**

Absolute unties relate to physical units of length.  Relative units, such as `em` or `rem` are relative to another length value. 

**Variables**

```css
--penguin-skin: gray;

background: var(--penguin-skin);

/* Can provide a fallback with */
background: var(--penguin-skin, black);
```

Variables in the `:root` selector are available globally and can be overridden later.

## Applied Visual Design

- `<s>` strike through text
- `<em>` emphasis (italic)

```css
rgba(45, 45, 45, 0.1)
```

*the `a`* is the alpha/level of opacity.  Range 0..1

**Box Shadow**

Has property values for

- `offset-x` (push the shadow horizontally form the element)
- `offset-y` (push the shadow vertically from the element)
- `blur-radius` (optional)
- `spread-radius` (optional)
- `color`

```css
box-shadow: 0 10px 20px rgba(0,0,0,0.19), 0 6px 6px rgba(0,0,0,0.23);
```

Multiple, box-shadows can be used and are separated using commas.

**Opacity**

The `opacity` property is used to adjust the opacity, or conversely, the transparency of an item:

- A value of 1 is opaque, which isn't transparent at all
- A value of 0.5 is half see-through
- A value of 0 is completely transparent

The following transformations are available with `text-transform`:

- lowercase
- uppercase
- capitalize
- initial
- inherit
- none

**Positioning**

When a position is set to `relative`, you are specifying how CSS should move it *relative* to its current position in the normal flow of the page.  The movement is effectively the opposite direction to that specified.  To move something up by 10px:

```css
p {
  position: relative;
  bottom: 10px;
}
```

When using `absolute` positioning, an element is locked in place relative to its parent container.  This puts the element outside of the normal document flow.

This is similar to `fixed` positioning, which locks an element relative to the browser window.  The difference being, elements with a fixed position don't move when the user scrolls.

Elements with a `float` property and removed from normal document flow and pushed to either the left of right of their containing parent element.

```html
<head>
  <style>
  #left {
   float: left;
   width: 50%;
  }
  #right {
   float: right;
   width: 40%;
  }
  aside, section {
   padding: 2px;
   background-color: #ccc;
  }
 </style>
</head>
<body>
 <header>
  <h1>Welcome!</h1>
 </header>
 <section id="left">
  <h2>Content</h2>
    <p>Good stuff</p>
 </section>
 <aside id="right">
  <h2>Sidebar</h2>
    <p>Links</p>
 </aside>
</body>
```

You can use `z-index` to change the order of overlapping elements.

To centre a block element horizontally, you can set its `margin` to auto.

```html
<style>
  div {
    background-color: blue;
    height: 100px;
    width: 100px;
    margin: auto;
  }
</style>
<div></div>
```

**Hue, Saturation and Lightness (HSL)**

```css
hsl(240, 100%, 50%)
```

This is useful when adjusting a base colour slightly.

**Linear Gradient**

CSS can provide colour transitions, also known as gradients

```css
background: linear-gradient(gradient_direction, color 1, color 2, color 3, ...);

background: linear-gradient(90deg, red, yellow, rgb(204, 204, 255));

background: linear-gradient(35deg, #CCFFFF, #FFCCCC)
```

There is also a repeating variant

```css
background: repeating-linear-gradient(
      45deg,
      yellow 0px,
      yellow 40px,
      black 40px,
      black 80px
    );
```

Another option

```css
background: url("https://cdn-media-1.freecodecamp.org/imgr/MJAkxbh.png")
```

To change the scale (size) of an element

```css
p {
  transform: scale(2);
}
```

This can also be used to add interactivity or highlighting to an element

```css
p:hover {
  transform: scale(2.1);
}
```

A transform can also skew

```css
transform: skewX(-24deg);
transform: skewY(-10deg);
```



## Compatibility

```css
background: red; /* Fallback option for older browsers */
background: var(--red-color); /* Used by modern browsers */
```

A media query can be used to change a variable

```css
 :root {
  --penguin-size: 300px;
 }

 @media (max-width: 350px) {
  :root {
   --penguin-size: 200px;
  }
 }
```

**Responsive Images**

```css
img {
  max-width: 100%;
  height: auto;
}
```

The `max-width` of `100%` ensures the image is never wider than it's parent container.  The `height` of `auto` keeps the images original aspect ratio.

## Flexbox

```html
<style>
  #box-container {
    height: 500px;
    display: flex;
  }

  #box-1 {
    background-color: dodgerblue;
    width: 50%;
    height: 50%;
  }

  #box-2 {
    background-color: orangered;
    width: 50%;
    height: 50%;
  }
</style>
<div id="box-container">
  <div id="box-1"></div>
  <div id="box-2"></div>
</div>
```

Column

```html
<style>
  #box-container {
    display: flex;
    height: 500px;
    flex-direction: column;
  }
  #box-1 {
    background-color: dodgerblue;
    width: 50%;
    height: 50%;
  }

  #box-2 {
    background-color: orangered;
    width: 50%;
    height: 50%;
  }
</style>

<div id="box-container">
  <div id="box-1"></div>
  <div id="box-2"></div>
</div>
```

Can use `justify-content` to adjust flexbox behaviour.  The default alignment is `flex-start` and there are also `flex-end`, `space-between`, `space-around` and `space-evenly` options.