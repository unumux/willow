# **Willow**

- [Introduction](#introduction)

- [Installation and Usage](#installation-and-usage)

- [Components](#components)

- [Page Layout](#page-layout)
  - [Basics](#basics)
  - [Creating Page Columns](#creating-page-columns)
  - [Customizing the Bootstrap Grid](#customizing-the-bootstrap-grid)

- [Understanding Themes](#understanding-themes)

- [Available Themes](#available-themes)

- [Customizing](#customizing)
  - [Recommended SCSS Directory Structure For Your Project](#recommended-scss-directory-structure-for-your-project)
  - [So you need to make a new component](#so-you-need-to-make-a-new-component)
  - [So you need to customize a component](#so-you-need-to-customize-a-component)
  - [So you need to change a theme](#so-you-need-to-change-a-theme)

- [Issues and Feedback](#issues-and-feedback)

- [Glossaries](#glossaries)

---

## Introduction

**Willow** is a library of reusable user interface components built with front-end code (HTML and SCSS) to allow for faster, more consistent product development.

The library consists of semantic and accessible markup for a variety of components that can be paired with your own custom theme or a provided [theme](#available-themes) to give components a consistent and branded appearance.

### **Willow** is...

- written to meet UnumUX [CSS/SCSS](https://unumux.github.io/enterprise-css-standards/index.html) and [Accessibility](https://unumux.github.io/enterprise-accessibility-standards/) Standards
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

### **Method 1: As an NPM Package: SCSS Files**

#### _Notes_

- Requires [node](https://nodejs.org) and a tool to compile the SCSS into CSS, such as Gulp, Webpack or Grunt.
- Allows single components imports instead of the entire library

#### Installation

- Install **Willow** as a development dependency in your project.
    ```bash
    npm install --save-dev @unumux/willow
    ```
- Optional: To install a provided theme, you will need the [theme's name](#available-themes):
    ```bash
    npm install --save-dev @unumux/theme-name-goes-here
    ```

#### Usage

- Include the entire library by importing **Willow's** stylesheet in your primary SCSS file.
    ```SCSS
    @import "node_modules/@unumux/willow/styles";
    ```
- Include single components by importing the component's stylesheet in your primary SCSS file.
    ```SCSS
    @import "node_modules/@unumux/willow/components/banner/styles/banner";
    @import "node_modules/@unumux/willow/components/breadcrumbs/styles/breadcrumbs";
    ```
- Optional: To use a provided theme, include the theme's stylesheet in your primary SCSS file **BEFORE the line that imports Willow**:
    ```SCSS
    @import "node_modules/@unumux/theme-name-here/styles";
    @import "node_modules/@unumux/willow/styles";
    ```
Now as you add [**Willow** components](#components) to your HTML your compiler should run and you will see styled components in your browser.

### **Method 2: As Compiled and Minified CSS Files**

#### Installation

- To use **Willow** without a theme, download **Willow's** minified CSS file and add it to your project's styles folder
  - [Willow CSS](https://github.com/unumux/willow/releases/download/0.3.0/willow.min.css)
- To add a theme, download a theme's minified CSS file, and add it to your project's styles folder. You can delete the **Willow** CSS file if you previously included it.
  - [Minified CSS Downloads](#minified-css-downloads)

#### Usage

- After you include a minified CSS file in your styles folder, you can reference it in your index.html file
    ```HTML
    <!-- If using Willow without a theme -->
    <link rel="stylesheet" href="styles/willow.min.css">
    ```

    ```HTML
    <!-- If using a theme you only need to include the theme's min file -->
    <link rel="stylesheet" href="styles/theme-name.min.css">
    ```

Now as you add [**Willow** components](#components) to your HTML file they will inherit styling

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

### Layout

- [Page Container](./components/page-container)
- [Page Header](./components/page-header)
- [Page Content](./components/page-content)
- [Page Footer](./components/page-footer)
- [Grid](./components/grid)

### Navigation

- [Breadcrumbs](./components/breadcrumbs)
- [Logo Link](./components/logo-link)
- [Footer Navigation](./components/footer-nav)
- [Primary Navigation](./components/primary-nav)
- [Secondary Navigation](./components/secondary-nav)
- [Skip Link](./components/skip-nav)

### Calls to Action and Alerts

- [Banner](./components/banner)
- [Button](./components/button)
- [Cards](./components/card)
- [Dialog](./components/dialog)
- [Global Alerts](./components/global-alert)
- [Inline Alerts](./components/inline-alert)
- [Modal](./components/modal)

### Other

- [Icons](./components/icons)
- [Styling Context](./components/styling-context)

---

## Page Layout

### Basics

**Willow** uses a combination of the [willow-page-container](./components/page-container) and [Bootstrap's fluid container](https://getbootstrap.com/docs/4.0/layout/overview/) to handle page layouts.

[willow-page-container](./components/page-container) makes the page a [flex column](https://css-tricks.com/snippets/css/a-guide-to-flexbox/) which gives the ability to apply the [`.flex-grow` utility class](utilities.md) to any component or row to make it fill extra page height. **willow-page-container** also allows a max-width for styling such as background-colors and images.

The [Bootstrap](https://getbootstrap.com/docs/4.0/layout/overview/) fluid container contains a page's content to a certain width and provides a [grid system](https://getbootstrap.com/docs/4.0/layout/grid/) for page columns.

To utilize these layout helpers, start your page with `<div class="willow-page-container"></div>` and place all of your content for the page inside of this component. 

### Creating Page Columns

To create page columns, use the Bootstrap `<div class="container-fluid">` element and add `<div class="row"></div>` and `<div class="col"></div>` as needed. _Note: you will need to determine the correct `col` class name to use [Bootstrap documentation](https://getbootstrap.com/docs/4.0/layout/grid/#grid-options)._

A common example of a column layout would be a page section contains secondary navigation and content.  On a mobile device the secondary navigation needs to be above the content, and on desktop the pieces should be next to each other.

```html
<div class="willow-page-container">
  <main class="willow-page-content" id="" role="main">
    <div class="container-fluid">
      <h1 class="willow-page-content__heading">Heading for content</h1>
      <div class="row">
        <div class="col-lg-3">
          <!-- insert secondary nav -->
        </div>
        <div class="col-lg-9">
          <!-- insert willow-page-content component -->
        </div>
      </div>
    </div>
  </main>
</div>
```

### Customizing the Bootstrap Grid

Bootstrap provides documentation about [customizing the grid](https://getbootstrap.com/docs/4.0/layout/grid/#customizing-the-grid)

_Note: To update bootstrap grid variables, you have to do this before you import a Willow theme._

```scss
// file: my-project/styles/styles.scss
$grid-columns: 10;

//theme import
@import "node_modules/@unumux/theme-name-here/styles";
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

---

### Recommended SCSS Directory Structure For Your Project

We recommend you setup your project's styling folders and files using this project [pattern](https://github.com/unumux/willow-testing-site).

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

### Main Variables That Can Be Overridden

...

---

## Issues and Feedback

Found an issue of have an idea for enhancement? Open an [issue](https://github.com/unumux/willow/issues/new).

---

## Glossaries

- [Component Modifiers](modifiers.md)
- [Utility Classes, Functions and Mixins](utilities.md)
