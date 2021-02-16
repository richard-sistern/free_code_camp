# CSS

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