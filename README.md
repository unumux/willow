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

- [Available Themes](#available-themes)

- [Components](#components)

- [Customizing](#customizing)
  - [Recommended SCSS Directory Structure For Your Project](#recommended-scss-directory-structure-for-your-project)
  - [So you need to make a new component](#so-you-need-to-make-a-new-component)
  - [So you need to customize a component](#so-you-need-to-customize-a-component)
  - [So you need to change a theme](#so-you-need-to-change-a-theme)

- [Issues and Feedback](#issues-and-feedback)

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

### Method 1: NPM

If you have [node](https://nodejs.org) on your machine, you can use npm to install **Willow** themes and components.

- Installation
  - Install a Theme as a development dependency for your project. You will need the [theme's name](#available-themes)
    ```bash
    npm install --save-dev @unumux/theme-name-goes-here
    ```

- Usage
  - Include the theme in your project's primary SCSS file:
    ```SCSS
    @import "../node_modules/@unumux/theme-name-here/styles";
    ```

### Method 2: Compiled and Minified CSS Files

- Installation
  - Download a theme's CSS file, and add it to your project's styles folder
    - [Available Themes](#available-themes)

- Usage
  - After you include the CSS file in your styles folder, you can reference it in your index.html file
    ```HTML
    <link rel="stylesheet" href="styles/theme-name.min.css">
    ```
  - Then as you add **Willow** components to your HTML file they will inherit styling

### Need Installation Help

Do you have questions or need help with setup? Did you run into errors while following these instructions? Feel free to open an issue here:

[Open An Issue](https://github.com/unumux/willow/issues/new)

---

## Available Themes

|         Theme Name         | Documentation                                               | CSS Download |
|:-------------------------- |:-----------------------------------------------------------:|:------------:|
|  theme-enterprise-default  |[docs](https://github.com/unumux/theme-enterprise-default)   |[theme-enterprise-default.min.css](https://github.com/unumux/theme-enterprise-default/releases/download/0.1.1/theme-enterprise-default.min.css)|
|     theme-unum-default     |[docs](https://github.com/unumux/theme-unum-default)         |[theme-unum-default.min.css](https://github.com/unumux/theme-unum-default/releases/download/0.1.1/theme-unum-default.min.css)|
| theme-coloniallife-default |[docs](https://github.com/unumux/theme-coloniallife-default) |[theme-coloniallife-default.min.css](https://github.com/unumux/theme-coloniallife-default/releases/download/0.1.1/theme-coloniallife-default.min.css)|

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

## Customizing

[Recommended SCSS Directory Structure For Your Project](#recommended-scss-directory-structure-for-your-project)

[So you need to make a new component](#so-you-need-to-make-a-new-component)

[So you need to customize a component](#so-you-need-to-customize-a-component)

[So you need to change a theme](#so-you-need-to-change-a-theme)

---

### Recommended SCSS Directory Structure For Your Project

We recommend you setup your project's styling folders and files using this project [pattern](https://github.com/unumux/standard-project-structure).

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

## Issues and Feedback

Found an issue of have an idea for enhancement? Open an [issue](https://github.com/unumux/willow/issues/new).
