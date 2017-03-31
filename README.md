---
title: Component Library
collection: 
  - index
  - home
permalink: false
---
# **Willow UI Components**

- [Introduction](#introduction)

- [Getting Started](#getting-started)
  - [installation](#installation)
  - [Including **Willow** in a Project](#including-in-a-project)

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

**Willow** UI Component Library is a collection of reusable components built with front-end code (HTML and CSS) to allow for faster, more consistent product development.

The library consists of semantic and accessible markup for a variety of components that can be paired with a [theme](#available-themes) to quickly give components a consistent and brand compliant appearance.

### **Willow** is...

- written to meet UnumUX [CSS/SCSS](https://github.com/unumux/ux-standards/wiki/CSS-&-SCSS-Standards) and [Accessibility](https://unumux.github.io/enterprise-accessibility-standards/) Standards
- built to work with all modern browsers (IE 10, Chrome, Firefox, Safari)
- based on the principles of:
  - [Atomic Design](http://bradfrost.com/blog/post/atomic-web-design/) : small, independent - atomic - parts, can be combined into larger molecular structures. Molecular structures can be combined into larger organisms, which can then serve as the foundation for templates and full pages
  - [BEM](http://getbem.com) : a naming convention that makes front-end code easier to read, understand, work with, maintain and scale


---

## Getting Started

[Installation](#installation)

[Including **Willow** in a Project](#including-in-a-project)

---

### Installation

#### Download a Compiled and Minified CSS File

**Willow** CSS files provide a compiled and minified stylesheet for each theme that can be add to a project and referenced in the index.html files. Then when **Willow** HTML is added they will inherit the styling accordingly.

- [Theme-Enterprise-Default](https://github.com/unumux/theme-enterprise-default) - [download](...)
- [Theme-Unum-Default](https://github.com/unumux/theme-unum-default) - [download](...)
- [Theme-Coloniallife-Default](https://github.com/unumux/theme-coloniallife-default) - [download](...)


#### Install Components and A Theme with NPM

If you have node installed on your machine, you can use npm to install **Willow**.

1 - npm install components
2 - npm install theme of your choice

...

#### Need Installation Help

Do you have questions or need help with setup? Did you run into any weird errors while following these instructions? Feel free to open an issue here:

[Open An Issue](https://github.com/unumux/willow/issues/new)

---

### Including in a Project

_If you downloaded a minified css file_, you can include the CSS file in your project and reference it in your index.html file. Then as you add **Willow** HTML they will automatically inherit their styles.

_If you installed via NPM and are using SCSS_ you can include **Willow** and a theme in your project's primary SCSS file like so:

```SCSS
// Your project's primary scss file - recommended name _styles.scss
//-----------------------------------
// Import Themes and Custom Styles
//-----------------------------------
//Willow theme variables are needed first
//the file path for this may look something like "../node_modules/@unumux/theme-enterprise-default/styles"
@import "path/to/willow/theme/root/scss/file";

//this is your custom style variables
//here you can overwrite Willow variable or create new variables
@import "path/to/my-project/styles/theme/theme.scss";

//-----------------------------------
// Component Imports
//-----------------------------------
//Willow Components use the variables you imported above
//the file path for this may look something like "../node_modules/@unumux/components/styles"
@import "path/to/willow/components/root/scss/file";

//here you can style any new components you wrote to use the above variables
//you can also target existing Willow Components and change their default styling
@import "path/to/my-project/styles/components/components.scss";
```

---

## Customizing

[Recommended SCSS Directory Structure For Your Project](#recommended-scss-directory-structure-for-your-project)

[So you need to make a new component](#so-you-need-to-make-a-new-component)

[So you need to customize a component](#so-you-need-to-customize-a-component)

[So you need to change a theme](#so-you-need-to-change-a-theme)

---

### Recommended SCSS Directory Structure For Your Project

In your project we recommend you setup your styling using the following directory pattern.

[Project Structure Example](https://github.com/unumux/standard-project-structure)

---

### So you need to customize a component

You can customize the **Willow** components via two methods

- Method 1: Change the look of a component globally
  - _Example: I want to change the size of all **willow-buttons** everywhere they appears_
  - Target the component class name and add the styling you want
  ```SCSS
    .willow-button,
    .willow-button--primary,
    .willow-button--positive,
    .willow-button--negative,
    .willow-button[disabled],
    .willow-button[data-disabled="true"] {
      padding: 30px 45px;
    }
  ```

- Method 2: Change the look of only one instances of a component
  - _Example: I want to change just the **willow-button** that is in my **willow-modal**_
  - Add a unique class to the one component you want to change then target that class and add your styling

---

### So you need to make a new component

...

---

### So you need to change a theme

You can change the theme by updating the values of the theme variables.  Note: These changes will be inherited throughout the html across many components.

---

### Main Variables That Can Be Overridden

...

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

## Contributing

Everyone is encouraged [to contribute](https://github.com/unumux/willow/blob/master/CONTRIBUTING.md) to the project by [forking](https://help.github.com/articles/fork-a-repo) and submitting a pull request. (If you are new to GitHub, you might start with a [basic tutorial](https://help.github.com/articles/set-up-git).)

Found an issue of have an idea for enhancement? Open an [issue](https://github.com/unumux/willow/issues/new).