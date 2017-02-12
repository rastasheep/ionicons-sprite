# Ionicons sprite
### SVG sprite icon set based on [Ionicons icons](http://ionicons.com).

- [Check the demo](https://rastasheep.github.io/ionicons-sprite)
- [Download sprite](https://github.com/rastasheep/ionicons-sprite/releases)
- [How to use?](#-how)

## What, why, how?

[Quite](https://css-tricks.com/icon-fonts-vs-svg/) a
[few](https://www.sitepoint.com/icon-fonts-vs-svg-debate/)
[people](https://una.im/svg-icons) have already written articles about this
topic,so this one will be short.

### • What?

Icon fonts suck on so many levels. So this is my two cents on making life with
SVGs and popular ionicon font a little bit easier. Inline only symbols that you
need and forget about additional requests, icon flickering and other stuff.

### • Why?

> There are basically three options we have when it comes to icon systems:
> - Font/glyph icons
> - CSS-based data URIs
> - SVG icons
>
> SVG icons are superior. I'm (not) sorry — they are. SVG is scalable,
> widely-supported, and allows for much more flexibility and dynamic editing.
>
> Font icons and data URI's in CSS content are a hack, while SVG icons
> represent visualizations in the format we expect without weird workarounds
> for breaking accessibility due to re-defining native DOM elements.

~ [Una Kravets](https://una.im/svg-icons/)

### • How?

Firstly, you need to add to your page inline `<svg>` with `<defs>` tag in it (it
just means that you are defining stuff to use later) which will contain
all definitions. Each `<symbol>` tag will have a unique ID, and will wrap all
the paths and whatnot thus forming an icon.

```html
<svg width="0" height="0" style="position:absolute">
  <defs>
    <symbol viewBox="0 0 512 512" id="ion-university">
      <!-- all the paths and shapes and whatnot for this icon -->
    </symbol>

    <symbol viewBox="0 0 512 512" id="ion-wand">
      <!-- all the paths and shapes and whatnot for this icon -->
    </symbol>

    <!-- etc -->
  </defs>
</svg>
```

You can get symbols with example for all icons by clicking on them [on demo
site](https://rastasheep.github.io/ionicons-sprite), or finding them in sprite
file in [the
repo](https://github.com/rastasheep/ionicons-sprite/blob/master/sprite.svg).

When you add all desired icons you can use them wherever, for example:

```html
<svg class="ion ion-wand">
  <use xlink:href="#ion-wand"></use>
</svg>
```

As this is plain html, you have the ability to style them with CSS. For that
purpose you can use class names added to SVGs.  Note that the icon will be
enormous (100% wide) if you don't specify it's dimensions.

```css
/* Example icon styling */
.ion {
  display: inline-block;
  width: 32px;
  height: 32px;
  stroke-width: 0;
  stroke: currentColor;
  fill: currentColor;
}

/* Single-colored icons can be modified like so */
.ion-wand {
  width: 42px;
  height: 42px;
  color: red;
}
```

## License

Ionicons is licensed under the [MIT license](http://opensource.org/licenses/MIT).

Ionicons-sprite is licensed under the [MIT license](http://opensource.org/licenses/MIT).
