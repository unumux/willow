# Utility Glossary

A glossary of utility [classes](#classes), [functions](#functions) and [mixins](#mixins) in the **Willow** library.

## Classes

`.butter` : removes margin between two adjacent `.butter` elements or components, allowing them to butt up against one another.

`.flex-grow` : applies flex-grow to a component or element causing it to fill the available space of the parent. _Note: the parent must be a flex parent_

`.sr-only` : visually hides information that is intended only for screen readers.

---

## Functions

### `breakpoint($breakpoint, $breakpoint-map)`

- Parameters:
  - `$breakpoint`: a value from the `$breakpoint-map` you pass as the 2nd argument
  - `$breakpoint-map`: a scss variable that is the name of the map you wish to use

- Requirements:
  - use in a `@media` query

- Returns:
  - a number and pixel unit from a collection of breakpoints (992px)

- Example:

```SCSS
    @media screen and (min-width: breakpoint(sm, $grid-breakpoints)) {
        ...
    }

    // compiles to

    @media screen and (min-width: 576px) {
        ...
    }

    // map used
    $grid-breakpoints: (
        xs: 0,
        sm: 576px,
        md: 768px,
        lg: 992px,
        xl: 1200px
    )
```

### `line-height($font-size)`

- Parameters:
  - `$font-size`: a number with a rem unit based (ie. 1.6rem)

- Returns:
  - a unitless line-height value based on the min and max line-height and font sizes in the theme or your project

- Example:

```SCSS
    .my-component__heading {
        font-size: $font-size-xxl;
        line-height: line-height($font-size-xxl);
    }
```

### `pow($ratio, $exponent)`

- Parameters:
  - `$ratio`: a number. This number should remain constant through your project, so use the same value for `$ratio` in every instance where you call `pow()`
  - `$exponent`: a whole number greater than zero

- Returns:
  - the value of `$ratio` multiplied by itself `$exponent` times

- Example:

```SCSS
    $golden-ratio: 1.618;
    $golden-ratio-l: pow($golden-ratio, 2);
    $golden-ratio-xl: pow($golden-ratio, 3);
```

### `space($scale)`

- Parameters:
  - `$scale`: a number greater than zero. Decimals less than 1 are allowed (ie. 0.5). Decimals values beyond one are not allowed (ie. 1.25).  Set to 1 by default.

- Returns:
  - the value of `$base` (a variable set in your theme or in Willow) multiplied by the value of the golden ratio (1.618) multiplied by itself `$scale` times

- Example:

```SCSS
    // set in Willow or a theme
    $base: 1.6rem;

    // in your styles
    .my-component {
        margin-top: space(2);
        // returns 4.1886rem
    }

    // a better application would be to use the existing space variables or create your own
    $my-space-xl: space(9);
    $padding-inset-xl: $my-space-xl #{$my-space-xl / 2};

    .my-jumbotron {
        padding: $padding-inset-xl;
        // becomes padding: 17.74rem 8.87rem;
    }
```

### `strip-unit($number)`

- Parameters:
  - `$number`: a number with a unit (ie. 10px)

- Returns:
  - `$number` with no unit (px, %, rem)

- Example:

```SCSS
    strip-units(10px); 
    //returns 10
```

---

## Mixins

### `icon($type)`

- sets properties and values for an icon based on the component and it's modifier

- possible `$type` values:
  - $icon-menu
  - $icon-menu-inverse
  - $icon-menu-close
  - $icon-menu-close-inverse
  - $icon-close
  - $icon-close-inverse
  - $icon-info
  - $icon-info-inverse
  - $icon-success
  - $icon-success-inverse
  - $icon-warning
  - $icon-warning-inverse
  - $icon-error
  - $icon-error-inverse

- Example:

```SCSS
    .my-alert--positive {
        &:before {
            @include icon($icon-success);

        }
    }

    /*
        properties set:
        background-image: ...;
        height: ...;
        width: ...;
    */
```

### `set-button-style($modifier, $state)`

- sets button properties and values for a specific button type (`$modifier`) and `$state` (ie. hover, focus, active, visited)

- possible `$modifier` values:
  - $neutral
  - $primary
  - $positive
  - $negative
  - $cta
  - $inline
  - $ghost
  - $ghost-inverse

- possible `$state` values:
  - "default"
  - "hover"
  - "focus"
  - "active"
  - "visited"
  - "disabled"

- Example:

```SCSS

    .my-button--primary {
        @include set-button-style($primary, "default");

        &:hover {
            @include set-button-style($primary, "hover");
        }
    }

    .my-button--negative {
        @include set-button-style($negative, "default");

        &:focus {
            @include set-button-style($negative, "focus");
        }
    }

    /*
        properties set:
        background-color: ...;
        border: ...;
        color: ...;
    */
```

### `set-text-style($style)`

- sets font properties and values for the provided font/text `$style`

- possible `$style` values:
  - $text-style-heading-1
  - $text-style-heading-2
  - $text-style-heading-3
  - $text-style-heading-4
  - $text-style-heading-5
  - $text-style-heading-6
  - $text-style-content-1
  - $text-style-content-2
  - $text-style-content-3

- Example:

```SCSS
    body {
        @include set-text-style($text-style-content-1);
    }

    h1 {
        @include set-text-style($text-style-heading-1);
    }

    small {
        @include set-text-style($text-style-content-3);
    }

    .my-component__heading {
        @include set-text-style($text-style-heading-3);
    }

    /*
        properties set:
        font-family: ...;
        font-size: ...;
        font-weight: ...;
        line-height: ...;

        @media screen and (min-width: breakpoint(medium)) {
            font-size: ...;
            line-height: ...;
        }
    */
```

### `sr-only()`

- sets properties to visibly hide an element without hiding it from assistive technology

- Example:

```SCSS
    .my-navigation__heading {
        @include sr-only;
    }

    /* properties set:
        position: absolute;
        width: 1px;
        height: 1px;
        padding: 0;
        margin: -1px;
        overflow: hidden;
        clip: rect(0,0,0,0);
        border: 0;
    */
```