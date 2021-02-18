# HTML

## Forms

```html
<form action="https://freecatphotoapp.com/submit-cat-photo">
    <label for="indoor"><input id="indoor" type="radio" name="indoor-outdoor" value="indoor" checked> Indoor</label>
    <label for="outdoor"><input id="outdoor" type="radio" name="indoor-outdoor" value="outdoor"> Outdoor</label><br>
    <label for="loving"><input id="loving" type="checkbox" name="personality" value="loving" checked> Loving</label>
    <label for="lazy"><input id="lazy" type="checkbox" name="personality" value="lazy"> Lazy</label>
    <label for="energetic"><input id="energetic" type="checkbox" name="personality" value="energetic"> Energetic</label><br>
    <input type="text" placeholder="cat photo URL" required>
    <button type="submit">Submit</button>
  </form>
```



**Audio**

```html
<audio id="meowClip" controls>
  <source src="audio/meow.mp3" type="audio/mpeg" />
  <source src="audio/meow.ogg" type="audio/ogg" />
</audio>
```

**Date Picker**

```html
<label for="input1">Enter a date:</label>
<input type="date" id="input1" name="input1">
```



## Accessibility

Images should always have an `alt` tag, although any decorative images should use an empty string.

```html
<img src="visualDecoration.jpeg" alt="">
```

 Each page should always have one (and only one) `h1` element and header tags should be used in descending order.

HTML 5 added the following which are used by screen readers, etc. for navigation and page summary:

- main (one per page)
- header (used within body and above main)
- footer
- nav
- article (section blog entries, forum posts, etc.)
- section (groups thematically related content)

The separation can be though of as `<div>` - groups content `<section>` - groups related content `<article>` - groups independent, self-contained content.

The `figure` element wraps an image, diagram or chart along with its caption.

Specify a shortcut key 

```html
<button accesskey="b">Important Button</button>
<a id="second" href="#" accesskey="c">
```

