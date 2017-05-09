---
component: willow-layout
collection: 
    - component
---
# **Willow-Layout**

[Demo](http://codepen.io/team/UnumUX/pen/YZjwRK)

A layout component, **willow-layout** should be used to constrict the page's content to a maximum width and to layout a page's content in a grid with rows and columns.

---

## HTML Snippet

```html
<div class="willow-layout">
    <div class="willow-layout__row">
        <div class="willow-layout__column--3">
            <!-- Insert Column Content Here -->
        </div>
        <div class="willow-layout__column--9">
            <!-- Insert Column Content Here -->
        </div>
    </div>
</div>
```

---

## Elements

### willow-layout

- Required
- Restrictions
  - Should Contain: **willow-layout** elements

#### _Notes_

- **willow-layout** will constrict the width of your page content, usually to 1170px.  This width comes from the theme and can be overwritten by setting a new value for the `$content-max-width` variable in your project's `scss` files

---

### willow-layout__row

- Required
- Repeatable
- Restrictions
  - Should Contain: **willow-layout__column** elements

#### _Modifiers_

`--remove-margin-bottom`: Removes the margin beneath a row

`--grow`: Expands a row to fill the browser's remaining vertical space

#### _Notes_

- **willow-layout__row** can hold between 1 and 12 columns
- Use the `--grow` modifier on the row that contains a site's main content. This will expand this row vertically and cause the footer to go to the bottom of the viewport

---

### willow-layout__column

- Required
- Repeatable
- Restrictions
  - Should Contain: one or more components

#### _Modifiers_

`--1`: Column width will span 1 column

`--2`: Column width will span 2 columns

`--3`: Column width will span 3 columns

`--4`: Column width will span 4 columns

`--5`: Column width will span 5 columns

`--6`: Column width will span 6 columns

`--7`: Column width will span 7 columns

`--8`: Column width will span 8 columns

`--9`: Column width will span 9 columns

`--10`: Column width will span 10 columns

`--11`: Column width will span 11 columns

`--12`: Column width will span 12 columns