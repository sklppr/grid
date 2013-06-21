# grid

A fluid, fraction-based grid framework for responsive/adaptive layouts.

## Features & Usage

Features:

- Fluid grid based on fractions (1/1, 3/4, 2/3, 1/2, 1/3, 1/4, 1/6, 1/8, 1/10)
- Irregular and nested layouts (nesting cells and rows)
- Positioning (prepend, append, push, pull)
- Grid flavors (additional layouts based on media queries)
- Adaptive cells (changing width based on layout)
- Adaptive rows (enabled/disabled based on layout)

Creating a basic grid:

```scss
// Basic grid without prepend, append, push, pull.
@include grid;
// Basic grid including prepend, append, push, pull.
@include grid($extended: true);
```

Creating grid flavors:

```scss
@media screen {
  
  @media (max-width: 480px) {
    // Grid flavor without prepend, append, push, pull.
    @include grid-flavor("compact");
    // Grid flavor including prepend, append, push, pull.
    @include grid-flavor("compact", $extended: true);
  }
  
}
```

Take a look at `demo.html` and `demo.scss` for more details.

## Cross-browser support

Fully supported: Chrome, Safari 4+, Firefox 3.5+, Internet Explorer 8+.  
Opera 9+ also works, but Opera ignores decimal places of percentages, so two-thirds/thirds/sixths/eigths will be too small.

Firefox < 3.5 requires a legacy clearfix which has its downsides.  
Internet Explorer < 8 requires special fractions, several hacks and additional content elements (assumed to have `.content`).

Enabling legacy support:

```scss
@include grid($legacy: true);
@include grid-flavor("wide", $legacy: true);
```
