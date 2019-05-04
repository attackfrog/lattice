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

### Customization

If you want a different number of columns than 6, add the variable `$grid-columns` to `_variables_custom.scss` with your desired value. 

You can also customize the size of the gap between columns and rows with the `$grid-gap` variable.