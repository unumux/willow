# **Willow-Page-Footer**

[Demo](https://unumux.github.io/willow-testing-site/components/page-footer.html)

A component for positioning/layout purposes. **Willow-Page-Footer** should only be used once per page and should be placed immediately after [willow-page-content](../page-content). This component should contain footer content such as copyright, legal information and footer navigation.

---

## HTML Snippet

```html
<footer class="willow-page-footer" role="contentinfo">
  <div class="container-fluid">
    <div class="willow-page-footer__container">
      <div class="willow-page-footer__branding"><!-- insert Willow-Logo-Link Component --></div>
      <div class="willow-page-footer__navigation"><!-- insert Willow-Footer-Nav Component Here --></div>
      <small class="willow-page-footer__copyright"><!-- insert copyright text here --></small>
    </div>
  </div>
</footer>
```

---

## Elements

### willow-page-footer

- Required
- Restrictions
  - Should Contain: the Bootstrap `.container-fluid` element

#### _Notes_

- The use of `role="contentinfo"` with the `<footer>` element ensures that **willow-page-footer** is accessible for user agents that do not support HTML5. The use of both `<footer>` and `<role="contentinfo">` together may create a warning in an [HTML validator](https://validator.w3.org/) but we left this pattern intact for now to cover all of our accessibility bases.

---

### container-fluid

- Required
- Restrictions
  - Should Contain: **willow-page-footer__container**

#### _Notes_

- The `container-fluid` class from Bootstrap is used within **willow-page-footer** to restrict the width of the component's content while allowing styles applied to the main **willow-page-footer** block to span the full-width of the [willow-page-container](../page-container) component.

---

### willow-page-footer__container

  - Required
  - Restrictions
    - Should Contain: **willow-page-footer** elements

#### _Notes_

- The **willow-page-footer__container** is for positioning the footer children.

---

### willow-page-footer__branding

- Required
- Restrictions
  - Should Contain: one [willow-logo-link](../logo-link) component

---

### willow-page-footer__navigation

- Required
- Restrictions
  - Should Contain: one [willow-footer-nav](../footer-nav) component

---

### willow-page-footer__copyright

- Optional
- Restrictions
  - Should Contain: text
