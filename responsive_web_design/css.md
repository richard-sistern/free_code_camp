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

Multiple, box-shadows can be used and are separated using commas

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

