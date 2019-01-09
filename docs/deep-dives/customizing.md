[Back to Main Readme](../README.md) > [Docs](./readme.md) > Customizing

# Customizing

- [Recommended SCSS Directory Structure For Your Project](#recommended-scss-directory-structure-for-your-project)
- [So you need to make a new component](#so-you-need-to-make-a-new-component)
- [So you need to customize a component](#so-you-need-to-customize-a-component)
- [So you need to change a theme](#so-you-need-to-change-a-theme)

---

## Recommended SCSS Directory Structure For Your Project

We recommend you setup your project's styling folders and files using this project [pattern](https://github.com/unumux/willow-testing-site).

---

## So you need to customize a component

You can customize **Willow** components via two methods

### Method 1: Change the look of a component globally

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

### Method 2: Change the look of only one instances of a component

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

## So you need to make a new component

You can make your own components and utilize variables from **Willow** to make your component have the same look and feel.

---

## So you need to change a theme

Themes are made with `!default` flags to allow you to override the values with your own SCSS.

Note: Changes to theme variables are used across many components, so tread lightly.

- In your project's SCSS
  - we recommend the `my-project/styles/theme/variables/theme-specific/theme-specific.scss` file

([Back to top](#customizing))
