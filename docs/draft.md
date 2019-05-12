# Lattice Documentation

## Grid System

Lattice uses a grid system based on CSS Grid. It has six columns by default, but this can be customized in the Sass files if desired. 

To use it, give a container element the `gridbox` class and define the widths of its children using `colspan-*`, where `*` is a number between 1 and 6. An element with `colspan-1`, for example, will be 1/6th the width of the container element.

```
<div class="gridbox">
    <div class="colspan-2"></div>
    <div class="colspan-4></div>
</div>
```

If you put two elements side by side this way that can't fit onto one line (a `colspan-3` and a `colspan-5`, for example), the one on the right will wrap down onto a new line. 

By default there is a small gap between each column (and row). If you don't want a gap, use `gridbox-gapless` instead of `gridbox`.

### Responsive Grid

You can also give elements different widths for different screen sizes. 

* `colspan-*` applies for all screens,
* `colspan-m-*` applies for medium screens and larger, 
* `colspan-l-*` applies for large screens and larger,
* `colspan-xl-*` applies for very large screens

Values for larger screen sizes will overwrite ones for smaller sizes, so if you do `<div class="colspan-6 colspan-l-3">`, the div will be 6 wide below the large breakpoint and 3 wide above it.

If you just provide a width at larger screen sizes, the element will be full width by default at smaller screen sizes.

### Customization

If you want a different number of columns than 6, add the variable `$grid-columns` to `_variables-custom.scss` with your desired value. 

You can also customize the size of the gap between columns and rows with the `$grid-gap` variable.

-------------------------------------------------------------------------------

## Text Formatting

Lattice uses [PT Sans](https://www.fontsquirrel.com/fonts/pt-sans) as its base font face. Heading sizes are scaled according to a "minor third" 1.2 ratio on smaller screens and at a "perfect fourth" 1.333 ratio on larger screens. 

There are several classes you can use to style text:

* `text-lead` - Increases text size and makes it more visible. Use this for a leading paragraph.
* `text-large` - Increases text size.
* `text-small` - Decreases text size.
* `text-left` - Aligns text to the left.
* `text-right` - Aligns text to the right.
* `text-center` - Centers text.
* `text-justify` - Justifies text.

In addition, `<code>` and `<pre>` elements have been styled to stand out more.

### Customization

Add the following to `_variables-custom.scss` to change their values:

* `$base-font-size` - change the base font size (16px by default)
* `$font-family` - change the font family
* `$font-scale-ratio-large` - change the font scaling ratio at larger screen sizes
* `$font-scale-ratio-small` - change the font scaling ratio at smaller screen sizes
* `$code-border-radius` - change the border radius of `<code>` and `<pre>` elements

-------------------------------------------------------------------------------

## Colors

Lattice uses a two-color complementary color scheme. By default the primary color is turquoise/teal and the secondary color is pink, but this can of course be customized in the Sass files. A number of background color classes are provided for you to style elements (especially cards.) 

* Primary colors
    * `.bgcolor-primary-offwhite`
    * `.bgcolor-primary-light`
    * `.bgcolor-primary-bright`
    * `.bgcolor-primary-dim`
    * `.bgcolor-primary-dark`
* Secondary colors
    * `.bgcolor-secondary-offwhite`
    * `.bgcolor-secondary-light`
    * `.bgcolor-secondary-bright`
    * `.bgcolor-secondary-dim`
    * `.bgcolor-secondary-dark`
* Greyscale colors (you can substitute 'gray' for 'grey' below if you prefer)
    * `.bgcolor-grey-offwhite`
    * `.bgcolor-grey-light`
    * `.bgcolor-grey-bright`
    * `.bgcolor-grey-dim`
    * `.bgcolor-grey-dark`

### Customization

Customizing the colors in Lattice is easy. Change the default hues from turquoise/teal and pink by adding the variables `$hue-primary` and `$hue-secondary` to `_variables-custom.scss` with your own HSLA hue values (0-255). 

You can also change the default saturation and lightness values for the various shades of each color. Add the custom variables `$saturation-*` and `$lightness-*` to `_variables-custom.scss`, replacing `*` with either `light`, `bright`, `dim`, `dark`, `offwhite`, or `black`.

-------------------------------------------------------------------------------

## Button Component

Both button (`<button>`) and anchor (`<a>`) elements can be styled as buttons. 

Buttons come in four sizes:
* `.button`
* `.button-small`
* `.button-large`
* `.button-huge`

...and four colors:
* `.button-primary`
* `.button-secondary`
* `.button-grey` (or `.button-gray`)
* `.button-clear` (a transparent button)

These size and color styles are intended to be combined, eg. `class="button button-primary"`.

### Customization

TODO