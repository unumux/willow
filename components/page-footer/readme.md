---
component: willow-page-footer
collection: 
    - component
    - misc
---
# **Willow-Page-Footer**

[Demo](http://codepen.io/team/UnumUX/pen/yMgJXb)

A component for positioning/layout purposes. **Willow-Page-Footer** should only be used once per page and should be placed immediately after [willow-page-content](../page-content). This component should contain footer content such as copyright, legal information and footer navigation.

---

## HTML Snippet

```html
<footer class="willow-page-footer" role="contentinfo">
    <div class="willow-page-footer__branding"><!-- insert Willow-Logo-Link Component --></div>
    <div class="willow-page-footer__navigation"><!-- insert Willow-Footer-Nav Component Here --></div>
    <small class="willow-page-footer__copyright"><!-- insert copyright text here --></small>
</footer>
```

---

## Elements

### willow-page-footer

- Required
- Restrictions
  - Should Contain: **willow-page-footer** elements

#### _Notes_

- The use of `role="contentinfo"` with the `<footer>` element ensures that **willow-page-footer** is accessible for user agents that do not support HTML5. The use of both `<footer>` and `<role="contentinfo">` together may create a warning in an [HTML validator](https://validator.w3.org/) but we left this pattern intact for now to cover all of our accessibility bases.

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