[Back to Main Readme](../README.md) > [Docs](./readme.md) > Getting Started

# Getting Started

- [Installation and Usage](#installation-and-usage)
- [Help](#help)

---

## Installation and Usage

**Willow** components come styled with default colors and font stylings, so the library can be installed and utilized without a theme. Using **Willow** without a theme will produce components styled in grayscale colors and simple/common fonts - somewhat like a [wireframe](https://en.wikipedia.org/wiki/Website_wireframe).

1. Install **Willow** as a development dependency in your project.
    ```bash
    npm install --save-dev @unumux/willow
    ```

2. Include the entire library by importing **Willow's** stylesheet in your primary SCSS file.
    ```SCSS
    @import "node_modules/@unumux/willow/styles";
    ```
    **Or:** Include single components by importing the component's stylesheet in your primary SCSS file.
      ```SCSS
      @import   "node_modules/@unumux/willow/components/banner/styles/banner";
      @import   "node_modules/@unumux/willow/components/button/styles/button";
      ```

3. Optional - Install a theme as a development dependency
    ```bash
    # Unum Theme
    npm install --save-dev @unumux/theme-unum-default

    # Colonial Life Theme
    npm install --save-dev @unumux/theme-coloniallife-default
    ```

4. Optional - Include a theme's stylesheet in your primary SCSS file **BEFORE the line that imports Willow**:
    ```SCSS
    // Unum Theme
    @import "node_modules/@unumux/theme-unum-default/styles";
    @import "node_modules/@unumux/willow/styles";
    ```
    ```SCSS
    // Colonial Life Theme
    @import "node_modules/@unumux/theme-coloniallife-default/styles";
    @import "node_modules/@unumux/willow/styles";
    ```

5. Now you're ready to start building
    - [Make a Page](./tutorials/make-a-page.md)
    - [Check out other Tutorials](./tutorials/readme.md)
    - [Review the Component List](./components.md)

---

## Help

Have questions or need help with setup? Get errors while following these instructions? Open an issue to let us know:

[Open An Issue](https://github.com/unumux/willow/issues/new)

([Back to top](#getting-started))
