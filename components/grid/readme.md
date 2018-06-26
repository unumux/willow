# **Willow-Grid**

[Demo](https://unumux.github.io/willow-testing-site/components/grid.html)

_Willow-grid_ is a component for laying out other components in rows and columns to form a grid.  _Willow-Grid_ controls the width of its children (_willow-grid__item_) without having to apply a width to each child.  The grid also controls the number of children that will be displayed in each row.

---

## HTML Snippet

```html
<div class="willow-grid">
    <div class="willow-grid__item">
        <!-- insert components here -->
    </div>
</div>

<!-- modified example -->
<div class="willow-grid willow-grid--md-4 willow-grid--lg-6">
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
  - Should Contain: one or more **willow-grid__item** elements

#### _Modifiers_

`--sm-[1-12]`: sets the number of columns to display per row on **small** screen sizes

`--md-[1-12]`: sets the number of columns to display per row on **medium** screen sizes

`--lg-[1-12]`: sets the number of columns to display per row on **large** screen sizes

`--xl-[1-12]`: sets the number of columns to display per row on **extra large** screen sizes

#### _Notes_

- The grid adjusts based on the `$grid-breakpoints` from [Bootstrap](https://getbootstrap.com/docs/4.0/layout/grid/#variables)
- Modifiers are not required
- If no modifiers are used, the grid will default to the following:
  - **one (1)** column per row on **small** screen sizes
  - **two (2)** columns per row on **medium** screen sizes
  - **three (3)** columns per row on **large** screen sizes
  - **four (4)** columns per row on **extra large** screen sizes

---

### willow-grid__item

- Required
- Repeatable
- Restrictions
  - Should Contain: one or more components
