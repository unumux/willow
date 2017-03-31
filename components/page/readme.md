---
component: willow-page
collection: 
    - component
---
# **Willow-Page**

[Demo](http://codepen.io/team/UnumUX/pen/YZjwRK)

A layout component, the **willow-page** should be used to constrict all of the page's content to a maximum width.

---

## HTML Snippet

```html
<div class="willow-page">
    <!-- insert all other components and html here -->
</div>
```

---

## Elements

### willow-page

- Required
- Restrictions
  - Should Contain: all components and html content of the page

#### _Notes_

- **willow-page** will constrict the width of your page content, usually to 1170px.  This width can be overwritten by setting a new value for the `$content-max-width` variable in your project's `scss` files