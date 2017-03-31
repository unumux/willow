---
component: willow-grid
collection: 
    - component 
    - misc
---
# **Willow-Grid**

[Demo](http://codepen.io/team/UnumUX/pen/PpWzpY)

A layout component, the **willow-grid** should be used within other components such as [willow-page-content](../page-content) or [willow-summary](../summary) to present content in a multi-column evenly distributed grid.

---

## HTML Snippet

```html
<div class="willow-grid">
    <div class="willow-grid__item">
        <!-- insert components here -->
    </div>
</div>
```

---

## Elements

### willow-grid

- Required
- Restrictions
  - Should Contain: **willow-grid** elements

---

### willow-grid__item

- Required
- Repeatable
- Restrictions
  - Should Contain: one or more components