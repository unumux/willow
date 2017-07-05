---
component: willow-secondary-nav
collection: 		
    - component 		
    - navigation
---
# **Willow-Secondary-Nav**

[Demo](http://codepen.io/team/UnumUX/pen/MpJevo)


Secondary Navigation provides navigational links that are separate from links provided by primary and footer navigation. Secondary navigation will appear on some pages of a site but not necessarily all pages. This navigation is meant for links a user may need in relation to their current page and they can link to content on their own page or to different pages. Secondary navigation can also be made up of common helpful links such as _Contact, About, News, Legal, FAQ, etc._

---

## HTML Snippet

```html
<nav class="willow-secondary-nav" role="navigation" aria-label="secondary">
    <h1 class="willow-secondary-nav__heading sr-only">Page Secondary Menu</h1>
    <ul class="willow-secondary-nav__list">
        <li class="willow-secondary-nav__item"><a class="willow-secondary-nav__link" href="" aria-label="">Menu Item 1</a></li>
        <li class="willow-secondary-nav__item"><a class="willow-secondary-nav__link" href="" aria-label="">Menu Item 2</a></li>
        <li class="willow-secondary-nav__item"><a class="willow-secondary-nav__link" href="" aria-label="">Menu Item 3</a></li>
    </ul>
</nav>
```

---

## Elements

### willow-secondary-nav

- Required
- Restrictions
  - Should Contain: **willow-secondary-nav** elements

#### _Notes_

- **willow-secondary-nav** should be located within the **willow-page-header__contextual-content** element (a sub-element of the **willow-page-header** component)
- If using more than one **willow-secondary-nav** on a page update the **willow-secondary-nav** elements aria-label attribute to be more descriptive such as "account" or "products"
- The use of `role="navigation"` with the `<nav>` element ensures that **willow-secondary-nav** is accessible for user agents that do not support HTML5. The use of both `<nav>` and `<role="navigation">` together may create a warning in an [HTML validator](https://validator.w3.org/) but we left this pattern intact for now to cover all of our accessibility bases.

---

### willow-secondary-nav__heading

- Required
- Restrictions
  - Should Contain: text

#### _Notes_

- **willow-secondary-nav__heading** is hidden by default with the `sr-only` utility class, and is required to meet accessibility standards
- Replace the text in this element with text that helps a user understand the context of this menu. _e.g. "Product Page Menu, About Page Menu"_

---

### willow-secondary-nav__list

- Required
- Restrictions
  - Should Contain: one or more **willow-secondary-nav__item**

#### _Notes_

- This order of the items in **willow-secondary-nav__list** does not matter greatly so the list will be marked up as a `<ul>` element

---

### willow-secondary-nav__item

- Required
- Repeatable
- Restrictions
  - Should Contain: one **willow-secondary-nav__link** element

---

### willow-secondary-nav__link

- Required
- Restrictions
  - Should Contain: text

#### _Notes_

- **willow-secondary-nav__link** elements require an `href` that links to the page it references
- **willow-secondary-nav__link** elements need an `aria-label` attribute value if the text content of the link doesn't clearly represent where the user will go after clicking the link