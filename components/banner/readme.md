# **Willow-Banner**

[Demo](https://unumux.github.io/willow-testing-site/)

A banner is a highlighted area of a page used to call out a single piece of information or action. This area is typically styled to stand out visually from the rest of the page’s content and can contain a concise heading, sentence and action component such as a [willow-button](../button).

A banner's background spans the full width of the screen/viewport while its content is restricted to the width of the `.container-fluid`. It cannot contain multiple columns. The banner component has a default background color but this color can be updated by a developer either by updating the `$component-banner-background-color` variable (which will update all banner backgrounds), or by adding a unique class name to the banner and adding new styling.

---

## HTML Snippet

```html
<section class="willow-banner" role="region">
  <div class="container-fluid">
    <h1 class="willow-banner__heading">Heading Text</h1>
    <div class="willow-banner__content">
        <!-- insert components here -->
    </div>
    <ul class="willow-banner__actions">
        <li class="willow-banner__action"><!-- insert action component here --></li>
    </ul>
  </div>
</section>
```

---

## Elements

### willow-banner

- Required
- Restrictions
  - Should Contain: the Bootstrap `.container-fluid` element

#### _Notes_

- The use of `role="region"` with the `<section>` element ensures that **willow-banner** is accessible for user agents that do not support HTML5. The use of both `<section>` and `<role="region">` together may create a warning in an [HTML validator](https://validator.w3.org/) but we left this pattern intact for now to cover all of our accessibility bases.
- To change the background-color on **all** banners you can set the `$component-banner-background-color` variable to a new color value. If you want to change the color for just one or a few banners you can add a unique class to each banner and style the `background-color` property for that class.

---

### container-fluid

- Required
- Restrictions
  - Should Contain: **willow-banner** elements

#### _Notes_

- The `container-fluid` class from Bootstrap is used within **willow-banner** to restrict the width of the component's content while allowing styles applied to the main **willow-banner** block to span the full-width of the [willow-page-container](../page-container) component.

---

### willow-banner__heading

- Required
- Restrictions
  - Should Contain: text

#### _Notes_

- **willow-banner__heading** is visible by default and even if it is hidden, it is required to meet accessibility standards
- To hide the **willow-banner__heading** add the `sr-only` utility class to the element

---

### willow-banner__content

- Required
- Restrictions
  - Should Contain: one or more components

---

### willow-banner__actions

- Optional
- Restrictions
  - Should Contain: one or more **willow-banner__action** elements

---

### willow-banner__action

- Optional
- Repeatable
- Restrictions
  - Should Contain: one _actionable_ component (such as [willow-button](../button) or a link)
