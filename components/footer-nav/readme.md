---
component: willow-footer-nav
collection: 
    - component
    - navigation
---
# **Willow-Footer-Nav**

[Demo](http://codepen.io/team/UnumUX/pen/VpPjmq)

Footer navigation is typically a combination of the links in the site's primary navigation plus links to items that users commonly search for or use. Footer navigation should be located within the [willow-page-footer](../page-footer) component and the links in this navigation should be consistent on every page of the site.

_Example Page Links: Sitemap, Frequently Asked Questions, Legal, Privacy Policy, Terms & Conditions, and Print Page._

---

## HTML Snippet

```html
<nav class="willow-footer-nav" role="navigation" aria-label="footer">
    <h1 class="willow-footer-nav__heading sr-only">Site Footer Menu</h1>
    <ul class="willow-footer-nav__list">
        <li class="willow-footer-nav__item"><a class="willow-footer-nav__link" href="" aria-label="">Menu Item 1</a></li>
        <li class="willow-footer-nav__item"><a class="willow-footer-nav__link" href="" aria-label="">Menu Item 2</a></li>
    </ul>
</nav>
```

---

## Elements

### willow-footer-nav

- Required
- Restrictions
  - Should Contain: **willow-footer-nav** elements

#### _Notes_

- The use of `role="navigation"` with the `<nav>` element ensures that **willow-footer-nav** is accessible for user agents that do not support HTML5. The use of both `<nav>` and `<role="navigation">` together may create a warning in an [HTML validator](https://validator.w3.org/) but we left this pattern intact for now to cover all of our accessibility bases.

---

### willow-footer-nav__heading

- Required
- Restrictions
  - Should Contain: text

#### _Notes_

- **willow-footer-nav__heading** is hidden by default with the `sr-only` utility class, and is required to meet accessibility standards

---

### willow-footer-nav__list

- Required
- Restrictions
  - Should Contain: one or more **willow-footer-nav__item** elements

#### _Notes_

- the order items in **willow-footer-nav__list** does not matter greatly, so the list is marked up as a `<ul>` element

---

### willow-footer-nav__item

- Required
- Repeatable
- Restrictions
  - Should Contain: one **willow-footer-nav__link** element

---

### willow-footer-nav__link

- Required
- Restrictions
  - Should Contain: text

#### _Notes_

- **willow-footer-nav__link** requires an `href` value that links to the pages they reference
- **willow-footer-nav__link** elements need `aria-label` value if the text content of the link doesn't clearly represent where the user will go after clicking the link