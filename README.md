---
title: Component Library
collection: 
  - index
  - home
permalink: false
---
# **Willow**

- [Introduction](#introduction)

- [Installation and Usage](#installation-and-usage)

- [Components](#components)

- [Available Themes](#available-themes)

- [Customizing](#customizing)
  - [Recommended SCSS Directory Structure For Your Project](#recommended-scss-directory-structure-for-your-project)
  - [So you need to make a new component](#so-you-need-to-make-a-new-component)
  - [So you need to customize a component](#so-you-need-to-customize-a-component)
  - [So you need to change a theme](#so-you-need-to-change-a-theme)

- [Contributing](#contributing)

---

## Introduction

**Willow** is a library of reusable user interface components built with front-end code (HTML and SCSS) to allow for faster, more consistent product development.

The library consists of semantic and accessible markup for a variety of components that can be paired with a [theme](#available-themes) to give components a consistent and branded appearance.

### **Willow** is...

- an evolving open source library that will have frequent updates and encourages [contributions](CONTRIBUTING.md)
- written to meet UnumUX [CSS/SCSS](https://github.com/unumux/ux-standards/wiki/CSS-&-SCSS-Standards) and [Accessibility](https://unumux.github.io/enterprise-accessibility-standards/) Standards
- built to work with all modern browsers (IE 10, Chrome, Firefox, Safari)
- based on the principles of:
  - [Atomic Design](http://bradfrost.com/blog/post/atomic-web-design/) : small, independent - atomic - parts, can be combined into larger molecular structures. Molecular structures can be combined into larger organisms, which can then serve as the foundation for templates and full pages
  - [BEM](http://getbem.com) : a naming convention that makes front-end code easier to read, understand, work with, maintain and scale

---

## Installation and Usage

There are 2 methods for installing and using **Willow** for your project

### Method 1: Compiled and Minified CSS Files

- Installation
  - Download a theme's CSS file, and add it to your project's styles folder
    - [Theme-Enterprise-Default](https://github.com/unumux/theme-enterprise-default) - [download](https://github.com/unumux/theme-enterprise-default/releases/download/0.1.1/theme-enterprise-default.min.css)
    - [Theme-Unum-Default](https://github.com/unumux/theme-unum-default) - [download](https://github.com/unumux/theme-unum-default/releases/download/0.1.1/theme-unum-default.min.css)
    - [Theme-Coloniallife-Default](https://github.com/unumux/theme-coloniallife-default) - [download](https://github.com/unumux/theme-coloniallife-default/releases/download/0.1.1/theme-coloniallife-default.min.css)

- Usage
  - After you include the CSS file in your style folder, you can reference it in your index.html file
    - ```<link rel="stylesheet" href="styles/theme-cl-default.min.css">```
  - Then as you add **Willow** HTML the components will inherit styling.

### Method 2: NPM

If you have [node](https://nodejs.org) on your machine, you can use npm to install **Willow** themes and components.

- Installation
  - Install **Willow** components
    - From Terminal in your project directory run the following:
      ```node
      npm install --save-dev @unumux/willow
      ```
  - Install a Theme - you will need the [theme's name](#available-themes)
    - From Terminal in your project directory run the following:
      ```node
      npm install --save-dev @unumux/theme-name-goes-here
      ```

- Usage
  - Include a theme and **Willow** components in your project's primary SCSS file like so:
    ```SCSS
    // Your project's primary scss file
    //--------------------------------------------------
    //  1. Import Themes and Custom Theme Styles
    //--------------------------------------------------
    // Willow theme variables are needed first
    // the file path for this may look something like "../node_modules/@unumux/theme-enterprise-default/styles"
    @import "path/to/willow/theme/root/scss/file";

    // this is your custom style variables
    // here you can overwrite Willow variable or create new variables
    @import "path/to/my-project/styles/theme/theme.scss";

    //--------------------------------------------------
    // 2. Imports Willow and Custom Components
    //--------------------------------------------------
    // Willow Components use the theme variables imported above
    // the file path for this may look something like "../node_modules/@unumux/components/styles"
    @import "path/to/willow/components/root/scss/file";

    // here you can style new components you created to use the above theme variables
    // you can also target existing Willow Components and customize their default styling
    @import "path/to/my-project/styles/components/components.scss";
    ```

### Need Installation Help

Do you have questions or need help with setup? Did you run into errors while following these instructions? Feel free to open an issue here:

[Open An Issue](https://github.com/unumux/willow/issues/new)

---

## Components

- [Banner](./components/banner)
- [Breadcrumbs](./components/breadcrumbs)
- [Button](./components/button)
- [Dialog](./components/dialog)
- [Footer Navigation](./components/footer-nav)
- [Global Alerts](./components/global-alert)
- [Grid](./components/grid)
- [Icons](./components/icons)
- [Inline Alerts](./components/inline-alert)
- [Logo Link](./components/logo-link)
- [Modal](./components/modal)
- [Page](./components/page)
- [Page Content](./components/page-content)
- [Page Footer](./components/page-footer)
- [Page Header](./components/page-header)
- [Primary Navigation](./components/primary-nav)
- [Secondary Navigation](./components/secondary-nav)
- [Skip Link](./components/skip-nav)
- [Styling Context](./components/styling-context)
- [Summary](./components/summary)

---

## Available Themes

### Company Specific

- [Theme-Enterprise-Default](https://github.com/unumux/theme-enterprise-default)
- [Theme-Unum-Default](https://github.com/unumux/theme-unum-default)
- [Theme-Coloniallife-Default](https://github.com/unumux/theme-coloniallife-default)

---

## Customizing

[Recommended SCSS Directory Structure For Your Project](#recommended-scss-directory-structure-for-your-project)

[So you need to make a new component](#so-you-need-to-make-a-new-component)

[So you need to customize a component](#so-you-need-to-customize-a-component)

[So you need to change a theme](#so-you-need-to-change-a-theme)

---

### Recommended SCSS Directory Structure For Your Project

We recommend you setup your project's styling folders and files using this [pattern](https://github.com/unumux/standard-project-structure).

---

### So you need to customize a component

You can customize **Willow** components via two methods

#### Method 1: Change the look of a component globally

_Example: You want to change the size of all **willow-buttons** everywhere they appear_

- In your SCSS/CSS, select the component's class name and add the styling you want
- **Note**: This method may require targeting multiple component versions such as willow-button and willow-button--primary

```SCSS
// file: styles/components/overrides/willow/button/_button.scss
.willow-button,
.willow-button--primary,
.willow-button--positive,
.willow-button--negative,
.willow-button[disabled],
.willow-button[data-disabled="true"] {
  padding: 30px 45px;
}
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

...

---

### So you need to change a theme

Themes are created to allow you to override the values of variables from your own SCSS.

Note: Changes to theme variables will be inherited throughout the html across many components, so tread lightly.

- In your project's SCSS
  - we recommend the ```styles/theme/variables/theme-specific/theme-specific.scss``` file

---

### Main Variables That Can Be Overridden

...

---

## Contributing

Everyone is encouraged [to contribute](https://github.com/unumux/willow/blob/master/CONTRIBUTING.md) to the project by [forking](https://help.github.com/articles/fork-a-repo) and submitting a pull request. (If you are new to GitHub, you might start with a [basic tutorial](https://help.github.com/articles/set-up-git).)

Found an issue of have an idea for enhancement? Open an [issue](https://github.com/unumux/willow/issues/new).
