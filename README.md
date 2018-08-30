# Willow

- [Introduction](#introduction)
  - [Requirements](#requirements)
  - [Browser Support](#browser-support)

- [Getting Started](./docs/getting-started.md)
  - [Installation and Usage](./docs/getting-started.md#installation-and-usage)
  - [Help](./docs/getting-started.md#help)

- [Tutorials](./docs/tutorials/readme.md)
  - [Make a page](./docs/tutorials/make-a-page.md)
    - [Setup](./docs/tutorials/make-a-page.md#setup)
    - [Adding common components](./docs/tutorials/make-a-page.md#add-common-components)
    - [Adding more components](./docs/tutorials/make-a-page.md#add-more-components)
    - Maybe more sections here ....
  - Make a component
  - Make a theme
  - Customize an existing component
  - Customize an existing theme
  - Contribute to Willow

- [Components](./docs/components.md)
  - [List](./docs/components.md#list)
  - [Related Links](./docs/components.md#related-links)

- Deeper Dives
  - [Page Layout](./docs/page-layout.md#page-layout)
    - [Basics](./docs/page-layout.md#basics)
    - [Creating Page Columns](./docs/page-layout.md#creating-page-columns)
    - [Customizing the Bootstrap Grid](./docs/page-layout.md#customizing-the-bootstrap-grid)
  
  - [Theming](./docs/theming.md)
    - [Understanding Themes](./docs/theming.md#understanding-themes)
    - [Available Themes](./docs/theming.md#available-themes)
  
  - [Customizing](./docs/customizing.md)
    - [Recommended SCSS Directory Structure For Your Project](./docs/customizing.md#recommended-scss-directory-structure-for-your-project)
    - [So you need to make a new component](./docs/customizing.md#so-you-need-to-make-a-new-component)
    - [So you need to customize a component](./docs/customizing.md#so-you-need-to-customize-a-component)
    - [So you need to change a theme](./docs/customizing.md#so-you-need-to-change-a-theme)
  
- [Issues and Feedback](#issues-and-feedback)

- [Glossaries](#glossaries)
  - [Component Modifiers](./docs/component-modifiers.md)
  - [Utilities](./docs/utilities.md)

---

## Introduction

**Willow** is a library of reusable user interface components built with front-end code (HTML and SCSS) to allow for faster, more consistent product development.

The library consists of semantic and accessible markup for a variety of components that can be paired with your own custom theme or a provided [theme](./docs/theming.md#available-themes) to give components a consistent and branded appearance.

### Requirements

Willow requires [node](https://nodejs.org) and a tool to compile the SCSS into CSS, such as Gulp, Webpack or Grunt.

### **Willow** is...

- written to meet Unum [CSS/SCSS](https://unumux.github.io/enterprise-css-standards/index.html) and [Accessibility](https://unumux.github.io/enterprise-accessibility-standards/) Standards
- influenced by the principles of:
  - [Atomic Design](http://bradfrost.com/blog/post/atomic-web-design/) : small, independent - atomic - parts, can be combined into larger molecular structures. Molecular structures can be combined into larger organisms, which can then serve as the foundation for templates and full pages
  - [BEM](http://getbem.com) : a naming convention that makes front-end code easier to read, understand, work with, maintain and scale

### Browser Support

- Internet Explorer 10, 11 and Edge
- Chrome, Safari, Firefox

---

## Issues and Feedback

Found an issue of have an idea for enhancement? Open an [issue](https://github.com/unumux/willow/issues/new).

---

## Glossaries

- [Component Modifiers](./docs/modifiers.md)
- [Utility Classes, Functions and Mixins](./docs/utilities.md)

([Back to top](#willow))
