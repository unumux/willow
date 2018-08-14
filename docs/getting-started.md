[Back to Main Readme](../readme.md)

# Getting Started

- [Installation and Usage](#installation-and-usage)

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
