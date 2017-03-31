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

- **willow-page-footer** has a `role="contentinfo"` for accessibility

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