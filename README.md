# **Willow**

- [Introduction](#introduction)

- [Installation and Usage](#installation-and-usage)

- [Components](#components)

- [Layout](#layout)

- [Understanding Themes](#understanding-themes)

- [Available Themes](#available-themes)

- [Customizing](#customizing)
  - [Recommended SCSS Directory Structure For Your Project](#recommended-scss-directory-structure-for-your-project)
  - [So you need to make a new component](#so-you-need-to-make-a-new-component)
  - [So you need to customize a component](#so-you-need-to-customize-a-component)
  - [So you need to change a theme](#so-you-need-to-change-a-theme)
  - [So you need to change the Bootstrap grid](#so-you-need-to-change-the-bootstrap-grid)

- [Issues and Feedback](#issues-and-feedback)

---

## Introduction

**Willow** is a library of reusable user interface components built with front-end code (HTML and SCSS) to allow for faster, more consistent product development.

The library consists of semantic and accessible markup for a variety of components that can be paired with your own custom theme or a provided [theme](#available-themes) to give components a consistent and branded appearance.

### **Willow** is...

- written to meet UnumUX [CSS/SCSS](https://github.com/unumux/ux-standards/wiki/CSS-&-SCSS-Standards) and [Accessibility](https://unumux.github.io/enterprise-accessibility-standards/) Standards
- influenced by the principles of:
  - [Atomic Design](http://bradfrost.com/blog/post/atomic-web-design/) : small, independent - atomic - parts, can be combined into larger molecular structures. Molecular structures can be combined into larger organisms, which can then serve as the foundation for templates and full pages
  - [BEM](http://getbem.com) : a naming convention that makes front-end code easier to read, understand, work with, maintain and scale

### Browser Support

Willow is built to work with modern browsers

- Internet Explorer 10, 11 and Edge
- Chrome, Safari, Firefox

---

## Installation and Usage

**Willow** components come styled with default colors and font stylings, so the library can be installed and utilized without a theme. Using **Willow** without a theme will produce components styled in grayscale colors and simple/common fonts - somewhat like a [wireframe](https://en.wikipedia.org/wiki/Website_wireframe).

There are 2 methods for installing and using **Willow** in a project

### **Method 1: As an NPM Package**

NOTE: This method requires [node](https://nodejs.org) be installed and that your project use a tool to compile the SCSS into CSS, such as Gulp, Webpack or Grunt.

- Installation
  - Install **Willow** as a development dependency in your project.
    ```bash
    npm install --save-dev @unumux/willow
    ```
  - Optional: To install a provided theme, you will need the [theme's name](#available-themes):
    ```bash
    npm install --save-dev @unumux/theme-name-goes-here
    ```

- Usage
  - Include **Willow's** stylesheet in your primary SCSS file.
    ```SCSS
    @import "node_modules/@unumux/willow/styles";
    ```
  - Optional: To use a provided theme, include the theme's stylesheet in your primary SCSS file **BEFORE the line that imports Willow**:
    ```SCSS
    @import "node_modules/@unumux/theme-name-here/styles";
    @import "node_modules/@unumux/willow/styles";
    ```
  - Now as you add [**Willow** components](#components) to your HTML your compiler should run and you will see styled components in your browser.

### **Method 2: As Compiled and Minified CSS Files**

- Installation
  - To use **Willow** without a theme, download **Willow's** CSS file and add it to your project's styles folder
    - [Willow CSS](https://github.com/unumux/willow/releases/download/0.3.0/willow.min.css)
  - To add a theme, download a theme's CSS file, and add it to your project's styles folder. You can delete the **Willow** CSS file if you previously included it.
    - [Minified CSS Downloads](#minified-css-downloads)

- Usage
  - After you include a CSS file in your styles folder, you can reference it in your index.html file
    ```HTML
    <!-- If using Willow without a theme -->
    <link rel="stylesheet" href="styles/willow.min.css">
    ```

    ```HTML
    <!-- If using a theme you only need to include the theme's min file -->
    <link rel="stylesheet" href="styles/theme-name.min.css">
    ```
  - Now as you add [**Willow** components](#components) to your HTML file they will inherit styling

### **Minified CSS Downloads**

|            File            | CSS Download |
|:-------------------------- |:------------:|
|Willow                      |[willow.min.css](https://github.com/unumux/willow/releases/download/0.3.0/willow.min.css)|
|Unum Theme                  |[theme-unum-default.min.css](https://github.com/unumux/theme-unum-default/releases/download/0.5.0/theme-unum-default.min.css)|
|Colonial Life Theme         |[theme-coloniallife-default.min.css](https://github.com/unumux/theme-coloniallife-default/releases/download/0.6.0/theme-coloniallife-default.min.css)|

### **Need Installation Help**

Do you have questions or need help with setup? Did you run into errors while following these instructions? Feel free to open an issue here:

[Open An Issue](https://github.com/unumux/willow/issues/new)

---

## Components

### Required

- [Layout](#layout)
- [Skip Link](./components/skip-nav)

### Optional

- [Banner](./components/banner)
- [Breadcrumbs](./components/breadcrumbs)
- [Button](./components/button)
- [Cards](./components/cards)
- [Dialog](./components/dialog)
- [Footer Navigation](./components/footer-nav)
- [Global Alerts](./components/global-alert)
- [Icons](./components/icons)
- [Inline Alerts](./components/inline-alert)
- [Logo Link](./components/logo-link)
- [Modal](./components/modal)
- [Page Content](./components/page-content)
- [Page Footer](./components/page-footer)
- [Page Header](./components/page-header)
- [Primary Navigation](./components/primary-nav)
- [Secondary Navigation](./components/secondary-nav)
- [Styling Context](./components/styling-context)

---

## Layout

**Willow** uses [Bootstrap](http://v4-alpha.getbootstrap.com/layout/grid/) to contain the page's content and provide a grid system.

To utilize this, setup a container on your page with `<div class="container"></div>`. All of your content for the page should go inside of this element.

**Willow** components and your own components can be added directly to this container (meaning you don't have to put everything in a row or column) and they will fill the space.

To create columns, use the `<div class="row"></div>` element with `<div class="col"></div>` elements. _Note: you will need to determine the correct `col` class name to use, we recommend the [Bootstrap documentation](http://v4-alpha.getbootstrap.com/layout/grid/#grid-options)._

A common example of a column layout would be a page section contains secondary navigation and content.  On a mobile device the secondary navigation needs to be above the content, and on desktop the pieces should be next to each other.

```html
<div class="container">
  <div class="row">
    <div class="col-lg-3">
      <!-- insert secondary nav -->
    </div>
    <div class="col-lg-9">
      <!-- insert willow-page-content component -->
    </div>
  </div>
</div>
```

### Customize the Bootstrap Grid

**Willow** takes the bootstrap breakpoint, container width and gutter values as they come. If you want to update these checkout the section on [customizing the grid](#so-you-need-to-change-the-bootstrap-grid).

### Willow's Bootstrap Customization

**Willow** adds styles to the `.container` class to make it a [flex column](https://css-tricks.com/snippets/css/a-guide-to-flexbox/). This gives the ability to apply the [utility class](utilities.md) `.flex-grow` to any component or row to make it fill extra page height.

```scss
.container {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}
```

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

## Available Themes

|         Theme Name         | Documentation                                               |
|:-------------------------- |:-----------------------------------------------------------:|
|     theme-unum-default     |[docs](https://github.com/unumux/theme-unum-default)         |
| theme-coloniallife-default |[docs](https://github.com/unumux/theme-coloniallife-default) |

---

## Customizing

[Recommended SCSS Directory Structure For Your Project](#recommended-scss-directory-structure-for-your-project)

[So you need to make a new component](#so-you-need-to-make-a-new-component)

[So you need to customize a component](#so-you-need-to-customize-a-component)

[So you need to change a theme](#so-you-need-to-change-a-theme)

[So you need to change the Bootstrap grid](#so-you-need-to-change-the-bootstrap-grid)

---

### Recommended SCSS Directory Structure For Your Project

We recommend you setup your project's styling folders and files using this project [pattern](https://github.com/unumux/standard-project-structure).

---

### So you need to customize a component

You can customize **Willow** components via two methods

#### Method 1: Change the look of a component globally

_Example 1: You want to change the size of all **willow-buttons** everywhere they appear_

- In your SCSS/CSS, select the component's class name and add the styling you want
- **Note**: This method may require targeting multiple component versions such as willow-button and willow-button--primary

```SCSS
// file: my-project/styles/components/overrides/willow/button/_button.scss
.willow-button,
.willow-button--primary,
.willow-button--positive,
.willow-button--negative,
.willow-button[disabled],
.willow-button[data-disabled="true"] {
  padding: 30px 45px;
}
```

_Example 2: You want to change the background color of positive buttons_

- You would accomplish this by overriding a 'component-specific' variable for the positive buttons
- Find the variable you want to override by looking at the component's `_default-variables.scss` file located in the styles folder in every component folder. [**Willow** Repo](https://github.com/unumux/willow) 
- Override the value of that variable in your `_styles.scss` file above the import for the theme
  ```SCSS
  $my-color: #37c0e3;
  $component-button-positive-background-color: $my-color;

  @import "node_modules/@unumux/theme-name-here/styles";
  ```

#### Method 2: Change the look of only one instances of a component

_Example: I want to change just the **willow-button** that is in my **willow-modal**_

- Add a unique class to the specific component(s) you want to change then select that class and add your styling

```HTML
<button class="willow-button modal-button">
```

```SCSS
// file: styles/components/overrides/willow/button/_button.scss
.modal-button {
  background-color: orange;
}
```

---

### So you need to make a new component

You can make your own components and utilize variables from **Willow** to make your component have the same look and feel.

---

### So you need to change a theme

Themes are made with `!default` flags to allow you to override the values with your own SCSS.

Note: Changes to theme variables are used across many components, so tread lightly.

- In your project's SCSS
  - we recommend the `my-project/styles/theme/variables/theme-specific/theme-specific.scss` file

---

### So you need to change the Bootstrap grid

Bootstrap uses [variables](https://v4-alpha.getbootstrap.com/layout/grid/#variables) to control the grid. You can override these to customize how the system works.

#### Method 1: Override Variable in your Project

In your main styles file where you import the theme for Willow. You can declare the variables and override them like so:

```scss
//my-project/styles/styles.scss file

//Override variables above the import of the theme
$grid-gutter-width-base: 40px;

$container-max-widths: (
  sm: 500px,
  lg: 900px,
);

@import "node_modules/@unumux/theme-name-here/styles";

```

#### Method 2: Override Variables in your Theme

If you are creating your own theme for **Willow** components to use, you can override these variables by:

- In the `theme-name/variables/theme-specific` folder, create a new folder called vendors
- In the vendors folder create a new partial called _bootstrap.scss
- In this partial add the bootstrap variables you want to override, and change their values
- Make sure you import your new file in the _theme-specific.scss file

```scss
//theme-name/variables/theme-specific/vendors/bootstrap.scss file

$grid-breakpoints: (
  sm: 506px,
  lg: 972px
);

```

---

### Main Variables That Can Be Overridden

...

---

## Issues and Feedback

Found an issue of have an idea for enhancement? Open an [issue](https://github.com/unumux/willow/issues/new).
