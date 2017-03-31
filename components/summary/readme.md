---
component: Summary Container
collection: 
    - component
    - misc
---
# **Willow-Summary**

[Demo](http://codepen.io/team/UnumUX/pen/zZNBEW)

**Willow-Summary** is a container that allows you to use the [willow-grid](../grid) to repeat similar pieces of content. It contains a group of things that have equal weight to each other. They need to be viewed as a group and none should stand out over the others. These items can be a portion of a larger group/series of items - such as “latest blogs” from a full list of blogs.

---

## HTML Snippet

```html
<section class="willow-summary" role="region">
    <h1 class="willow-summary__heading">Heading Text</h1>
    <div class="willow-summary__content">
        <!-- insert Willow-Grid -->
    </div>
    <ul class="willow-summary__actions">
        <li class="willow-summary__action"><!-- insert action component here --></li>
    </ul>
</section>
```

---

## Elements

### willow-summary

- Required
- Restrictions
  - Should Contain: **willow-summary** elements

#### _Notes_

- **willow-summary** has a `role="region"` for accessibility

---

### willow-summary__heading

- Required
- Restrictions
  - Should Contain: text

#### _Modifiers_

`--sr`: hides **willow-summary__heading**

#### _Notes_

- **willow-summary__heading** is visible by default and even if it is hidden, it is required to meet accessibility standards

---

### willow-summary__content

- Required
- Restrictions
  - Should Contain: one [willow-grid](../grid) component

---

### willow-summary__actions

- Required
- Restrictions
  - Should Contain: one or more **willow-summary__Action** components

---

### willow-summary__action

- Required
- Restrictions
  - Should Contain: one _actionable_ component