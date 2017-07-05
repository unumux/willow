---
component: willow-banner
collection:
    - component
    - navigation
permalink: false
---
# **Willow-Banner**

[Demo](http://codepen.io/team/UnumUX/pen/YZNzQM)

A banner is a highlighted area of a page used to call out a single piece of information or action. This area is typically styled to stand out visually from the rest of the page’s content and can contain a concise heading, sentence and action component such as a [willow-button](../button).

A banner spans the full width of the screen/viewport. It cannot contain multiple columns. The banner component can have a background image set by the developer. If one is not set a fallback color will be displayed.

---

## HTML Snippet

```html
<section class="willow-banner" role="region">
  <h1 class="willow-banner__heading">Heading Text</h1>
  <div class="willow-banner__content">
      <!-- insert components here -->
  </div>
  <ul class="willow-banner__actions">
      <li class="willow-banner__action"><!-- insert action component here --></li>
  </ul>
</section>
```

---

## Elements

### willow-banner

- Required
- Restrictions
  - Should Contain: **willow-banner** elements

#### _Notes_

- The use of `role="region"` with the `<section>` element ensures that **willow-banner** is accessible for user agents that do not support HTML5. The use of both `<section>` and `<role="region">` together may create a warning in an [HTML validator](https://validator.w3.org/) but we left this pattern intact for now to cover all of our accessibility bases.
- To include a background image on **willow-banner** you will need to target the banner in your SCSS/CSS and set the `background-image` property. If you use the `.willow-banner` class, you will be targeting all banners on the site, so be sure to be more specific by adding your own class to the **willow-banner** component.

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