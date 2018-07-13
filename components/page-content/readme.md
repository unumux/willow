# **Willow-Page-Content**

A component for positioning/layout purposes.  **Willow-Page-Content** should only be used once per page and should be placed immediately after [willow-page-header](../page-header) and before the [willow-page-footer](../page-footer). This component should contain the main content of a page and page-related items such as secondary navigation. **Willow-Page-Content** should not contain the willow-page-header or willow-page-footer.

---

## HTML Snippet

```html
<main class="willow-page-content" id="" role="main">
    <h1 class="willow-page-content__heading">Heading for content</h1>
    <!-- insert components here -->
</main>
```

---

## Elements

### willow-page-content

- Required
- Restrictions
  - Should Contain: one or more components

#### _Notes_

- **willow-page-content** `id` attribute should be set and the [willow-skip-nav](../skip-nav) component should have an `href` equal to this value
- The use of `role="main"` with the `<main>` element ensures that **willow-page-content** is accessible for user agents that do not support HTML5. The use of both `<main>` and `<role="main">` together may create a warning in an [HTML validator](https://validator.w3.org/) but we left this pattern intact for now to cover all of our accessibility bases.

---

### willow-page-content__heading

- Required
- Restrictions
  - Should Contain: text

#### _Notes_

- **willow-page-content__heading** is visible by default, and even if it is hidden it is required to meet accessibility standards
- To hide the **willow-page-content__heading** add the `sr-only` utility class to the element
