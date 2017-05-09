---
component: willow-page-header
collection: 
    - component
    - misc
---
# **Willow-Page-Header**

[Demo](http://codepen.io/team/UnumUX/pen/qrRNjM)

A component for positioning/layout purposes.  **Willow-Page-Header** should only be used once per page and should be placed before [willow-page-content](../page-content). This component should appear on every page of your site and contain the main header content for the site such as [willow-logo-link](../logo-link) and [willow-primary-nav](../primary-nav). The header can also contain contextually related components that display content to a user based on their location, such as [willow-breadcrumbs](../breadcrumbs).

---

## HTML Snippet

```html
<header class="willow-page-header" role="banner">
    <div class="willow-page-header__branding"><!-- insert Willow-Logo-Link Component Here --></div>
    <div class="willow-page-header__content-controls">
        <a class="willow-page-header__content-open" aria-label="Open Menu" href="">menu</a>
        <a class="willow-page-header__content-close" aria-label="Close Menu"href="">close</a>
    </div>
    <div class="willow-page-header__content">
        <div class="willow-page-header__navigation"><!-- insert Willow-Primary-Nav Component Here --></div>
    </div>
</header>
```

---

## Elements

### willow-page-header

- Required
- Restrictions
  - Should Contain: **willow-page-header** elements

#### _States_

`<header class="willow-page-header" data-content-open="true">` : opens page-header__content

`<header class="willow-page-header" data-content-open="false">` : closes page-header__content

#### _Notes_

- **willow-page-header** has a `role="banner"` for accessibility

---

### willow-page-header__branding

- Required
- Restrictions
  - Should Contain: one [willow-logo-link](../logo-link) component

---

### willow-page-header__content-controls

- Required
- Restrictions
  - Should Contain: **willow-page-header_open** and **willow-page-header__close**

---

### willow-page-header__content-open

- Required
- Restrictions
  - Should Contain: text and/or a [willow-icon](../icons) component

#### _Notes_

- clicking **willow-page-header__content-open** should set **willow-page-header** `data-content-open` state attribute to `true`
- **willow-page-header__content-open** needs an `aria-label` attribute to define what the link does
  - This is required for low or no sight users or if the key word "Menu" is removed from the link

---

### willow-page-header__content-close

- Required
- Restrictions
  - Should Contain: text and/or a [willow-icon](../icons) component

#### _Notes_

- clicking **willow-page-header__content-close** should set **willow-page-header** `data-content-open` state attribute to `false`
- **willow-page-header__content-close** needs an `aria-label` attribute to define what the link does
  - This is required for low or no sight users or if the key word "Close" is removed from the link

---

### willow-page-header__content

- Required
- Restrictions
  - Should Contain: one **willow-page-header__navigation** element

---

### willow-page-header__navigation

- Required
- Restrictions
  - Should Contain: one [willow-primary-nav](../primary-nav) component