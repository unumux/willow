# **Willow-Page-Container**

A component for positioning/layout purposes.  **Willow-Page-Container** should only be used once per page and should be placed immediately after the opening `<body>` tag. This component should contain the entire page including willow-page-header and willow-page-footer.

---

## HTML Snippet

```html
<div class="willow-page-container">
    <!-- insert components here -->
</div>
```

---

## Elements

### willow-page-container

- Required
- Restrictions
  - Should Contain: one or more components

#### _Notes_

- **willow-page-container** provides a flex column layout allowing the use of the [`.flex-grow`](../../utilities.md) utility class on a child element to make it fill extra page height. For example, adding the `flex-grow` class to the [willow-page-content](../components/page-content) component will cause willow-page-content to grow vertically which will place the footer is at the bottom of the viewport.

  ```HTML
  <main class="willow-page-content flex-grow">
  ```

- The width of **willow-page-container** is controlled by the `$component-page-container-max-width` variable. This variable is set to none in **Willow** but can be updated in themes or in your project SCSS.
