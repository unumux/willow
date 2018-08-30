[Back to Main Readme](../README.md) > [Docs](./readme.md) > Theming

# Theming

- [Understanding Themes](#understanding-themes)
- [Available Themes](#available-themes)

---

## Understanding Themes

Themes for **Willow** only contain SCSS variables. These variables are then used in the **Willow** library components which makes them theme-able.

**Willow** comes with default settings for all necessary variables, so the library can be installed and utilized without a theme. Using **Willow** without a theme will produce components styled in grayscale colors and simple/common fonts - somewhat like a [wireframe](https://en.wikipedia.org/wiki/Website_wireframe).  You can choose to override these styles by [importing a theme](#installation-and-usage) or by creating your own them that sets new values for the variables.

There are 3 groups of variables:

- Constants
  - These variables are a fixed value, that is not expected to change and that is not abstracted. Primarily used for color and font settings.
    ```scss
    // theme-name/variables/constants/_colors.scss file
    $color-white: #fff;
    $color-bahama-blue: #285a83;
    $color-razzmatazz: #f22672;

    // theme-name/variables/constants/_fonts.scss file
    $font-family-primary: "Ubuntu", "helvetica", "arial", "sans-serif" !default;
    ```

- Theme-Specific
  - These variables are assigned values from Constant variables and begin the processes of giving purpose and priority to our colors and abstracting the variables.
    ```scss
    // theme-name/variables/_theme-specific.scss
    $theme-base: $color-white;
    $theme-primary: $color-bahama-blue;
    $theme-action: $color-bahama-blue;
    $theme-action-negative: $color-razzmatazz;
    $theme-text-inverse: $color-white;
    ```

- Component-Specific
  - These variables are used in the SCSS for a component. They are assigned values from the Theme-Specific variables, and their variable name describes the property being effected.
    ```scss
    // theme-name/variables/component-specific/_base.scss file
    $component-body-background-color: $theme-base !default;
    $component-link-color: $theme-primary !default;

    // theme-name/variables/component-specific/_page-header file
    $component-page-header-background-color: $theme-primary !default;

    // theme-name/variables/component-specific/_button.scss file
    $component-button-background-color: $theme-action !default;
    $component-button-negative-background-color: $theme-action-negative !default;
    ```

---

## Available Themes

|         Theme Name         | Documentation                                               |
|:-------------------------- |:-----------------------------------------------------------:|
|     theme-unum-default     |[docs](https://github.com/unumux/theme-unum-default)         |
| theme-coloniallife-default |[docs](https://github.com/unumux/theme-coloniallife-default) |

([Back to top](#theming))
