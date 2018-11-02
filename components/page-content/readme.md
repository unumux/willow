# **Willow-Page-Content**

A component for positioning and identifing a page's main content for accessibility.  **Willow-Page-Content** should only be used only once per page and should be placed immediately after [willow-page-header](../page-header) and before the [willow-page-footer](../page-footer). This component should contain the main content of a page and page-related items such as secondary navigation. **Willow-Page-Content** should not contain the willow-page-header or willow-page-footer.

---

## HTML Snippet

```html
<main class="willow-page-content" id="" role="main">
    <div class="container-fluid">
        <!-- insert components here (their width will be restricted by container-fluid) -->
    </div>
    <!-- insert components here (their width will not be contained) -->
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
- The `flex-grow` class can be added to this element to make it grow vertically to fill a browser. A related side effect of doing this is that the footer of your page will be at the bottom of the browser window.
- The use of `role="main"` with the `<main>` element ensures that **willow-page-content** is accessible for user agents that do not support HTML5. The use of both `<main>` and `<role="main">` together may create a warning in an [HTML validator](https://validator.w3.org/) but we left this pattern intact for now to cover all of our accessibility bases.

---

### container-fluid

- Required
- Restrictions
  - Can Contain: **willow-page-content** elements

#### _Notes_

- The `container-fluid` class from Bootstrap is used in **willow-page-content** to restrict the width of child components. Any components in the `container-fluid` element will have a restricted width.  If a component is added to **willow-page-content** but not in the `container-fluid` element the width will not be restricted. Example: You want to add a **willow-banner** to a page and you want the banner's background to be full-width. You can put **willow-banner** inside **willow-page-content** but not inside `container-fluid` and it would go full-width.  Why not put the banner outside of **willow-page-content** you ask - Including the banner in **willow-page-content** insures the banner's content will be a part of the page's main content by accessibility users. If your banner is not main content then it can be added outside of the **willow-page-content** component, it will go full-width and be outlined outside of the page's main content.

---

## [Variables](./styles/_default-variables.scss)

`$component-page-content-container-padding-bottom` : sets `` property on **willow-page-content__container**

`$component-page-content-container-padding-top` : sets `` property on **willow-page-content__container**
