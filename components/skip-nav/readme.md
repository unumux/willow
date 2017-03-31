---
component: willow-skip-link
collection: 
    - component
    - navigation
---
# **Willow-Skip-Nav**

[Demo](http://codepen.io/team/UnumUX/pen/YZNWxM)

The Skip Navigation or Skip Link is an accessibility component that allows motor and sight impaired users to skip navigation and scroll to to content identified as the main content of the page. This is also useful for sighted users relying on the keyboard for navigation.

The **willow-skip-nav** is hidden visibly until a user navigates or focuses on the component with their keyboard, at which point it will be displayed.

---

## HTML Snippet

```html
<div class="willow-skip-nav">
    <a href="" class="willow-skip-nav__link" aria-label="skip to main content">Skip to Content</a>
</div>
```

---

## Elements

### willow-skip-nav

- Required
- Restrictions
  - Should Contain: **willow-skip-nav** elements

#### _Notes_

- **willow-skip-nav** component should be included only once on a site and be placed before the [willow-page-header](../page-header) component
- If the site has a global alert, the **willow-skip-nav** should be placed after the [willow-global-alert](../global-alert) component

---

### willow-skip-nav__link

- Required
- Restrictions
  - Should Contain: text

#### _Notes_

- Set the `href` value of **willow-skip-nav__link** equal to the `id` value of the [willow-page-content](../page-content) component
- **willow-skip-nav__link** needs an `aria-label` value if the text content of the link doesn't clearly represent where the user will go after clicking the link