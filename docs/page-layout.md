[Back to Main Readme](../README.md) > [Docs](./readme.md) > Page Layout

# Page Layout

- [Basics](#basics)
- [Creating Page Columns](#creating-page-columns)
- [Customizing the Bootstrap Grid](#customizing-the-bootstrap-grid)

---

## Basics

**Willow** uses a combination of the [willow-page-container](./components/page-container) and [Bootstrap's fluid container](https://getbootstrap.com/docs/4.0/layout/overview/) to handle page layouts.

[willow-page-container](./components/page-container) makes the page a [flex column](https://css-tricks.com/snippets/css/a-guide-to-flexbox/) which gives the ability to apply the [`.flex-grow` utility class](utilities.md) to any component or row to make it fill extra page height. **willow-page-container** also allows a max-width for styling such as background-colors and images.

The [Bootstrap](https://getbootstrap.com/docs/4.0/layout/overview/) fluid container contains a page's content to a certain width and provides a [grid system](https://getbootstrap.com/docs/4.0/layout/grid/) for page columns.

To utilize these layout helpers, start your page with `<div class="willow-page-container"></div>` and place all of your content for the page inside of this component.

---

## Creating Page Columns

To create page columns, use the Bootstrap `<div class="container-fluid">` element and add `<div class="row"></div>` and `<div class="col"></div>` as needed. _Note: you will need to determine the correct `col` class name to use [Bootstrap documentation](https://getbootstrap.com/docs/4.0/layout/grid/#grid-options)._

A common example of a column layout would be a page section contains secondary navigation and content.  On a mobile device the secondary navigation needs to be above the content, and on desktop the pieces should be next to each other.

```html
<div class="willow-page-container">
  <main class="willow-page-content" id="" role="main">
    <div class="container-fluid">
      <h1 class="willow-page-content__heading">Heading for content</h1>
      <div class="row">
        <div class="col-lg-3">
          <!-- insert secondary nav -->
        </div>
        <div class="col-lg-9">
          <!-- insert willow-page-content component -->
        </div>
      </div>
    </div>
  </main>
</div>
```

---

## Customizing the Bootstrap Grid

Bootstrap provides documentation about [customizing the grid](https://getbootstrap.com/docs/4.0/layout/grid/#customizing-the-grid)

_Note: To update bootstrap grid variables, you have to do this before you import a Willow theme._

```scss
// file: my-project/styles/styles.scss
$grid-columns: 10;

//theme import
@import "node_modules/@unumux/[theme-name-here]/styles";
```

([Back to top](#page-layout))
