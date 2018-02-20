# **Willow-Page-Header**

[Demo](http://codepen.io/team/UnumUX/pen/qrRNjM)

The **Willow-Page-Header** component should be used on every page of your site (no more than once) and contain the main header content for the site such as [willow-logo-link](../logo-link) and [willow-primary-nav](../primary-nav).

---

## HTML Snippet

```html
<header class="willow-page-header" role="banner">
  <div class="container willow-page-header__container">
    <div class="willow-page-header__branding"><!-- insert Willow-Logo-Link Component Here --></div>
    <div class="willow-page-header__content-controls">
        <a class="willow-page-header__content-open" aria-label="Open Menu" href="">menu</a>
        <a class="willow-page-header__content-close" aria-label="Close Menu" href="">close</a>
    </div>
    <div class="willow-page-header__content">
        <div class="willow-page-header__navigation"><!-- insert Willow-Primary-Nav Component Here --></div>
    </div>
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

- The use of `role="banner"` with the `<header>` element ensures that **willow-page-header** is accessible for user agents that do not support HTML5. The use of both `<header>` and `<role="banner">` together may create a warning in an [HTML validator](https://validator.w3.org/) but we left this pattern intact for now to cover all of our accessibility bases.

---

### container with willow-page-header__container class

- Required
- Restrictions
  - Should Contain: **willow-page-header** elements

#### _Notes_

- The `container` class from Bootstrap is used within **willow-page-header** to restrict the width of the component's content while allowing styles applied to the main **willow-page-header** block to span the full-width of the [willow-page-container](../page-container) component.
- The **willow-page-header__container** class is for positioning the footer children. By adding this class the positioning can be controlled without adding overriding styling to the Bootstrap `container` class.

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