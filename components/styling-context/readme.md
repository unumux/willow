---
component: Styling Context
collection: 
    - component
    - misc
---
# **Willow-Styling-Context**

[Demo](http://codepen.io/team/UnumUX/pen/wJgWrM)

**Willow-Styling-Context** is a container that allows us to control the look of raw HTML by overriding the styles of base elements.  The raw HTML in this container can be added directly by a developer or may be inserted from a rich-text editor field in a content management system.

---

## HTML Snippet

```html
<div class="willow-styling-context">
    <!-- Insert raw HTML or Content Management System placeholders here -->
</div>
```

---

## Elements

### willow-styling-context

- Required
- Restrictions
  - Should Contain: raw HTML elements or placeholders for content from a rich-text editor in a Content Management System

#### _Notes_

- **willow-styling-context** should be used inside of any Willow component where you want to place HTML. _Example: You need to add a message to [willow-modal](../modal), so inside of **willow-modal__content** you would add **willow-styling-context** and then be able to add your message using raw HTML. 