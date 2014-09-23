# Hoggle

An inline-block based grid system. Still very much in its early stages.

View the [demo](http://therealalan.github.io/hoggle-test/). There's a [hoggle-test](https://github.com/TheRealAlan/hoggle-test) built on Middleman to play with.

## Requirements

- Sass
- something like Autoprefixer

This is a prefix free, inline-block based grid system. You'll need something like [Autoprefixer](https://github.com/postcss/autoprefixer) to handle your vendor prefixes. Whitespace may be an issue with the inline-block columns. If you're writing your HTML using HAML, you can clear out the whitespace with a `>` at the end of the tags. Since it's an inline-block grid, there are several advantages, one being the ability to easily vertically align content.

## Get the Gem

For now, there's just a gem. Add this to your gemfile.

```
gem "hoggle", :github => "TheRealAlan/hoggle"
```

## Include the SCSS

Include the Hoggle stylesheets:

``` scss
@import "hoggle";
```

## Usage

### Columns

Columns are wrapped in a `.row` class. Rows can be wrapped in a `.container` class to limit and center the width of the columns to the maximum column width for the screen size.

Columns are defined with the class `.col` and any combination of classes determining the width at different screen sizes. By default, these are `.x-small-*`, `.small-*`, `.medium-*`, `.large-*`, and `.x-large-*`. This means the column will fill the column space from the specified screen size up. Different column sizes can be set for different screen sizes.

The default breakpoints are set as follows:

``` scss
$x_small: 0px;
$small: 480px;
$medium: 768px;
$large: 992px;
$x_large: 1200px;
```

The `.col` width is determined by the suffix of the class names. The default available sizes are halves, thirds, quarters, and eighths.

``` html
<div class="row">
  <div class="col medium-1of1">
    
  </div>
  <div class="medium-1of2">
    
  </div>
  <div class="medium-1of3">
    
  </div>
  etc.
</div>
```

### Different Columns, Different Sizes

``` html
<div class="col large-1of8 medium-1of4 small-1of2">
  
</div>
```

### Offsets

``` html
<div class="row">
  <div class="col medium-1of2 medium-offset-1of2">
    
  </div>
</div>
```

### Hide / Show Utilities

There are classes for each size to hide and show elements that are appropriate. Just remember that they're still rendered, just visibly hidden. It won’t stop images from loading.

``` html
<div class="show-large">

</div>
<div class="hide-small">

</div>
```

### Vertically Centered Content

Vertically center content with `.middle`.

Vertically centering works because the columns are set to `inline-block`. This tends to be problematic because of whitespace that gets created between tags when the page is limited. If you’re using HAML, you can easily eliminate whitespace by placein a `>` at the end of the `.row` and column tags. If you're writing plain html, a workaround is to place the opening and closing tags together, like `</div><div>`.

Content can be aligned to the bottom by using `.bottom` as well.

### Swapped Columns

Swap column layout with <code class="code">.swap</code>. The order will stack correctly at phone sizes.

### Padding & Margin Helpers

Padding and margin can be added with classes that are multiples of `$base`, which by default are 6px. For example, `.pad-3` would result in 18px of padding on all four sides. There are separate classes for direction as well. For top and bottom, `.pad-v-*`, and for left and right, `.pad-h-*`. Add padding to just one side using `.pad-top-*`, `.pad-right-*`, `.pad-bottom-*`, and `.pad-left-*`.

### Responsive Padding & Margin Helpers

Often there’s a need for changing margins and paddings for different screen sizes. The margin and padding classes can also be set with screen size prefixes, just like the column widths. For example, `.x-small-margin-bottom-3` will only add 18px of margin when the columns are stacked on a phone.