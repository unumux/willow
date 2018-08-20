[Back to Main Readme](../README.md)

# Getting Started

- [Installation and Usage](#installation-and-usage)

---

## Installation and Usage

**Willow** components come styled with default colors and font stylings, so the library can be installed and utilized without a theme. Using **Willow** without a theme will produce components styled in grayscale colors and simple/common fonts - somewhat like a [wireframe](https://en.wikipedia.org/wiki/Website_wireframe).

### Installation

- Install **Willow** as a development dependency in your project.
    ```bash
    npm install --save-dev @unumux/willow
    ```
- Optional: To install the Unum theme:
    ```bash
    npm install --save-dev @unumux/theme-unum-default
    ```
- Optional: To install the Colonial Life theme:
    ```bash
    npm install --save-dev @unumux/theme-coloniallife-default
    ```

### Usage

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
    @import "node_modules/@unumux/[theme-name-here]/styles";
    @import "node_modules/@unumux/willow/styles";
    ```
Now as you add [**Willow** components](./docs/components-page-layout-examples.md#components) to your HTML your compiler should run and you will see styled components in your browser.

## Need Installation Help

Do you have questions or need help with setup? Did you run into errors while following these instructions? Feel free to open an issue here:

[Open An Issue](https://github.com/unumux/willow/issues/new)

([Back to top](#getting-started))
