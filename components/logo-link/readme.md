---
component: willow-logo-link
collection: 
    - component
    - navigation
---
# **Willow-Logo-Link**

[Demo](http://codepen.io/team/UnumUX/pen/RpKRpm)

**Willow-Logo-Link** is a component for displaying a logo and makes the entire logo into a link to the site's home page.

---

## HTML Snippet

```html
<a class="willow-logo-link" href="/" aria-label="go to home page"><img class="willow-logo-link__image" src="" alt=""></a>
```

---

## Elements

### willow-logo-link

- Required
- Restrictions
  - Should Contain: **willow-logo-link** elements

#### _Notes_

- **willow-logo-link** has `aria-label` set for accessibility

---

### willow-logo-link__image

- Required
- Restrictions
  - Should Contain: a path to the logo image

#### _Notes_

- **willow-logo-link__image** requires a `src` attribute value that is the path or url to the desired image
- In order to be accessible, **willow-logo-link__image** requires an `alt` attribute value that describes the image