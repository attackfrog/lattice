# Lattice Documentation

## Grid System

Lattice uses a grid system based on CSS Grid. It has six columns by default, but this can be customized in the Sass files if desired. 

To use it, give a container element the `.gridbox` class and define the widths of its children using `.colspan-*`, where `*` is a number between 1 and 6. An element with `.colspan-1`, for example, will be 1/6th the width of the container element.

```
<div class="gridbox">
    <div class="colspan-2"></div>
    <div class="colspan-4></div>
</div>
```

If you put two elements side by side this way that can't fit onto one line (a `.colspan-3` and a `.colspan-5`, for example), the one on the right will wrap down onto a new line. 

By default there is a small gap between each column (and row). If you don't want a gap, use `.gridbox-gapless` instead of `.gridbox`.

### Responsive Grid

You can also give elements different widths for different screen sizes. 

* `.colspan-*` applies for all screens,
* `.colspan-m-*` applies for medium screens and larger, 
* `.colspan-l-*` applies for large screens and larger,
* `.colspan-xl-*` applies for very large screens

Values for larger screen sizes will overwrite ones for smaller sizes, so if you do `<div class="colspan-6 colspan-l-3">`, the div will be 6 wide below the large breakpoint and 3 wide above it.

If you just provide a width at larger screen sizes, the element will be full width by default at smaller screen sizes.

```
<div class="gridbox">
    <div class="colspan-l-2 colspan-s-3"></div>
    <div class="colspan-l-2 colspan-s-3"></div>
    <div class="colspan-l-2 colspan-s-3"></div>
    <div class="colspan-l-6 colspan-s-3"></div>
</div>
```
...renders like the below (with .bgcolor-* styling added for visibility.) Try resizing your screen to see how it looks above and below the large breakpoint.

--- Example ---

### Customization

If you want a different number of columns than 6, add the variable `$grid-columns` to `_variables-custom.scss` with your desired value. 

You can also customize the size of the gap between columns and rows with the `$grid-gap-cols` and `$grid-gap-rows` variables.

If you want to use different breakpoints than the default, you can customize them with `$breakpoint-small`, `$breakpoint-medium` and `$breakpoint-large`. The default values are 640px, 960px, and 1200px respectively.

-------------------------------------------------------------------------------

## Text Formatting

Lattice uses [PT Sans](https://www.fontsquirrel.com/fonts/pt-sans) as its base font face. Heading sizes are scaled according to a "minor third" 1.2 ratio on smaller screens and at a "perfect fourth" 1.333 ratio on larger screens. 

There are several classes you can use to style text:

* `.text-lead` - Increases text size and makes it more visible. Use this for a leading paragraph.
* `.text-large` - Increases text size.
* `.text-small` - Decreases text size.
* `.text-left` - Aligns text to the left.
* `.text-right` - Aligns text to the right.
* `.text-center` - Centers text.
* `.text-justify` - Justifies text.
* `.text-bold` - Bolds text.
* `.text-italic` - Italicizes text.
* `.text-underline` - Underlines text.
* `.text-shadow-dark` - Applies a dark-colored shadow behind text.
* `.text-shadow-light` - Applies a light-colored shadow behind text.

In addition, `<code>` and `<pre>` elements have been styled to stand out more.

### Customization

Add the following to `_variables-custom.scss` to change their values:

* `$font-family` - change the font family
* `$base-font-size` - change the base font size (16px by default)
* `$font-scale-ratio-large` - change the font scaling ratio at larger screen sizes
* `$font-scale-ratio-small` - change the font scaling ratio at smaller screen sizes
* `$paragraph-line-height` - change the spacing between lines of text within paragraphs
* `$code-border-radius` - change the border radius of `<code>` and `<pre>` elements
* `$code-font-size` - change the size of `<code>` and `<pre>` text
* `$code-padding` - change the padding of `<code>` elements
* `$pre-padding` - change the padding of `<pre>` elements
* `$list-indent` - change the indentation of `<ul>` and `<ol>` lists
* `$list-item-spacing` - change the vertical spacing between list items
* `$font-size-large` - change the font size of the `.text-lead` and `.text-large` classes
* `$font-size-small` - change the font size of the `.text-small` class
* `$text-shadow-dark` - change the styling of the shadow for the `.text-shadow-dark` class
* `$text-shadow-light` - change the styling of the shadow for the `.text-shadow-light` class

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

You can also change the default saturation and lightness values for the various shades of each color. Add the [custom variable maps](https://sass-lang.com/documentation/values/maps) `$saturation` and `$lightness` to `_variables-custom.scss` and insert values for `light`, `bright`, `dim`, `dark`, `offwhite`, `black`, `light-grey`, `bright-grey`, `dim-grey`, `dark-grey`, `offwhite-grey`, and `black-grey` into them. A template is included in `_variables-custom.scss` to make this process easier.

-------------------------------------------------------------------------------

### Button Component

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

#### Customization

You can customize the appearance of buttons by adding these variables to `_variables-custom.scss`:
* `$button-border-radius` - change the border rounding radius of buttons
* `$button-padding-sides` change the horizontal padding of buttons
* `$button-padding-topbot` - change the vertical padding of buttons
* `$button-font-size` - change the base font size of buttons
* `$button-interact-shading` - change the percentage that the button lightens or darkens by when hovered over and pressed

You can also customize the sizes of the different button classes using a scaling factor, which is applied to the button's padding and font size. `$button-scale`, which is 1 by default, is applied to `.button` elements, and `$button-scale-small`, `$button-scale-large`, and `$button-scale-huge` are applied to `.button-small`, `.button-large`, and `.button-huge` elements respectively. 

Additionally, you can alter the colors of the button classes. `$button-hue-primary`, `$button-hue-secondary`, and `$button-hue-clear` all accept HSL hue values 0-255.

If you'd prefer to write your own button styles from scratch, you can overwrite the mixins that define their properties. In `_mixins-custom.scss`, create a `button($size)` mixin that accepts the scaling factor to redefine the button's styling and/or create a `@mixin button-color($hue, $bgshade, $textshade)` mixin to redefine the button's coloring, including its coloring in the hover, focus, and active states. `$bgshade` and `$textshade` should accept the values `offwhite`, `light`, `bright`, `dim`, `dark`, `black`, and those same values with `-grey` appended to them (eg. `offwhite-grey`.)

-------------------------------------------------------------------------------

### Card Component

Cards are a styled container element for holding content. They aren't colored by default, and are intended to be used in combination with the `.bgcolor-*` classes. 

They consist of three parts: a `.card` container element, into which are put a `.card-heading` header element and a `.card-body` body element. `.card-expand` can be added to the `.card` element to expand its width to fit the containing element.

```
<div class="card bgcolor-secondary-dim">
    <div class="card-heading">
        Card heading
    </div>
    <div class="card-body">
        Card body content...
    </div>
</div>
```
The above code renders like this:

---Example---

#### Customization

Cards can be customized by adding the following variables to `_variables-custom.scss`:
* `$card-margin` - change the margin around cards
* `$card-padding` - change the padding of cards
* `$card-border-radius` - change cards' border radius
* `$card-shadow` - change the styling of the drop shadow behind cards
* `$card-heading-font-size` - change the font size of card headings
* `$card-heading-font-weight` - change the font weight of card headings (bold by default)
* `$card-heading-padding-bottom` - change the padding under card headings
* `$card-heading-shadow` - change the small shadow under card headings

If you'd prefer to write your own card styles from scratch, you can do so by adding the `card()`, `card-heading()`, and `card-body()` mixins to `_mixins-custom.scss`. The styles in these mixins are applied to `.card`, `.card-heading`, and `.card-body` elements respectively.

-------------------------------------------------------------------------------

### Container Component

Containers are simple styles intended to be used as wrappers for page content. `.container-full` containers span the full width of the page and add some padding. `.container` containers also add some padding, but are restricted to a maximum width of 1024px. `.container-centered` containers span the full page width, but center any elements that are within them.

#### Customization

You can change the width of `.container` containers by adding the variable `$container-width` to `_variables-custom.scss`. You can also change the container padding with the `$container-padding` variable.

-------------------------------------------------------------------------------

### Hero Component

A hero is a stylized container element, intended to be used for content that should stand out from the rest of the page. To use one, apply the `.hero` class to the relevant container. Text within the hero container is styled slightly differently than regular text. Hero elements combine well with the `.bgcolor-*` color classes, and can also be made semitransparent by adding the `.hero-transparent` class to them (to allow background images to show through, for example.)

#### Customization

Hero containers can be customized by adding the following variables to `_variables-custom.scss`:
* `$hero-padding` - change the padding within the hero container
* `$hero-heading-font-weight` - change the font weight of heading elements in the hero container
* `$hero-paragraph-font-size` - change the font size of `<p>` elements in the hero container
* `$hero-paragraph-alpha` - change the transparency of `<p>` elements in the hero container
* `$hero-transparent-alpha` - change the transparency of the background of hero containers when the `.hero-transparent` class is applied

-------------------------------------------------------------------------------

### Navbar Component

To add some navigation capability to your page, use the navbar component. Apply the `.navbar` class to a `<nav>` element, and within that create a `<ul>` list whose `<li>` items are the content items you wish to have in your navigation bar. 

Navbars are left-justified by default, but you can center-justify them by applying the `.navbar-center` class to the `<nav>`, or right-justify them by applying the `.navbar-right` class. If you want some elements to be left-justified and some right-justified, put an empty `<li>` item between them with the class `.fill`.

Navbar elements are somewhat responsive, handling screen sizes too narrow to fill all their elements by wrapping their content onto multiple rows. If you don't want your navbar to do this, give it the class `.navbar-nowrap`. 

Navbars don't have any color by default, so they combine well with the `.bgcolor-*` classes. 

```
<nav class="navbar bgcolor-grey-dim">
    <ul>
        <li><img src="" alt="Image Item"></li>
        <li>Text Item</li>
        <li><a href="">Link Item</a></li>
        <li class="fill"></li>
        <li>Right-justified Item</li>
    </ul>
</nav>
```

#### Customization

You can customize various navbar styling properties by adding these variables to `_variables-custom.scss`:
* `$navbar-height` - change the height of the navbar
* `$navbar-item-spacing` - change the spacing between navbar items
* `$navbar-text-font-weight` - change the font weight of non-link navbar text
* `$navbar-link-font-weight` - change the font weight of navbar links
* `$navbar-link-underline-thickness` - change the thickness of the on-hover underlining of navbar links
* `$navbar-image-max-height` - change the maximum height of images in the navbar

Alternatively you can write your own navbar style from scratch as a mixin called `navbar()`, in `_mixins-custom.scss`. If you do this, you'll also want to add a mixin called `nav-align($align)` that will take care of center- and right-justifying the navbar when passed `center` and `right`. A `nav-fill()` mixin will be applied to the `.fill` class. If your navbar wraps for small screens, you may also want to write a mixin called `nav-nowrap()` that turns that behavior off. 

-------------------------------------------------------------------------------

### Visbility Components

You may want to have certain parts of your page show for some screen sizes and not others. If this is the case, you can use visibility components to show and hide them. The `.hidden-*` classes hide an element below a certain breakpoint, and the `.shown-*` classes hide an element above a breakpoint.

* `.hidden-small` - hidden below the small breakpoint
* `.hidden-medium` - hidden below the medium breakpoint
* `.hidden-large` - hidden below the large breakpoint
* `.shown-small` - shown only below the small breakpoint, and hidden above it
* `.shown-medium` - shown only below the medium breakpoint, and hidden above it
* `.shown-large` - shown only below the large breakpoint, and hidden above it

#### Customization

If you want to use different breakpoints, you can alter them in `_variables-custom.scss` by adding the `$breakpoint-small`, `$breakpoint-medium`, and/or `$breakpoint-large` variables. Note that these are shared with the `.colspan-*` classes in Lattice's grid functionality.

