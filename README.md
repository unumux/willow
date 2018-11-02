# Willow

- [Introduction](#introduction)
  - [Requirements](#requirements)
  - [Browser Support](#browser-support)

- [Docs](./docs/readme.md)
  - [Getting Started](./docs/getting-started.md)
    - [Installation and Usage](./docs/getting-started.md#installation-and-usage)
    - [Help](./docs/getting-started.md#help)
  - [Basic Tutorials](./docs/tutorials/readme.md)
    - [Make a page](./docs/tutorials/make-a-page.md)
    - [Make a component](./docs/tutorials/make-a-component.md)*
    - [Make a theme](./docs/tutorials/make-a-theme.md)*
    - [Customize an existing component](./docs/tutorials/customize-component.md)*
    - [Customize an existing theme](./docs/tutorials/customize-theme.md)*
    - [Contribute to or Maintain Willow](./CONTRIBUTING.md)
  - [Components](./docs/components.md)
  - [Deep Dives](./docs/deep-dives/readme.md)
    - [Page Layout](./docs/deep-dives/page-layout.md)
    - [Theming](./docs/deep-dives/theming.md)
    - [Customizing](./docs/deep-dives/customizing.md)

- [Issues and Feedback](#issues-and-feedback)

- [Glossaries](#glossaries)
  - [Component Modifiers](./docs/component-modifiers.md)
  - [Utilities](./docs/utilities.md)

*Pages are a work in progress

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
