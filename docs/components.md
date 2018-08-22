[Back to Main Readme](../README.md)

# Components

- [Component List](#component-list)
  - [Component Modifiers](./component-modifiers.md)
- [Starter HTML](#starter-html)
- [Page Layout Explained](#page-layout-explained)
- [Creating Page Columns](#creating-page-columns)
  - [Customizing the Bootstrap Grid](#customizing-the-bootstrap-grid)

---

## Component List

<details>
  <summary>For component or page layout</summary>

- [Page Container](./components/page-container)
- [Page Header](./components/page-header)
- [Page Content](./components/page-content)
- [Page Footer](./components/page-footer)
- [Grid](./components/grid)

</details>
<details>
  <summary>For navigation</summary>

- [Breadcrumbs](./components/breadcrumbs)
- [Logo Link](./components/logo-link)
- [Footer Navigation](./components/footer-nav)
- [Primary Navigation](./components/primary-nav)
- [Secondary Navigation](./components/secondary-nav)
- [Skip Link](./components/skip-nav)

</details>
<details>
  <summary>For calls to action or alerts</summary>

- [Banner](./components/banner)
- [Button](./components/button)
- [Cards](./components/card)
- [Dialog](./components/dialog)
- [Global Alerts](./components/global-alert)
- [Inline Alerts](./components/inline-alert)
- [Modal](./components/modal)

</details>
<details>
  <summary>Other</summary>

- [Icons](./components/icons)
- [Styling Context](./components/styling-context)

</details>

- [Component Modifiers](./component-modifiers.md)

---

## Starter HTML

After [installing and importing](./getting-started.md#installation-and-usage) Willow and an optional theme you're ready to start using Willow HTML.

A page outline boils down to:

- willow-page-container : contains everything
  - willow-page-header
  - willow-page-content
  - willow-page-footer

Here is an example of starter HTML with Willow page/layout components:

```HTML
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0">
    <title><!-- Insert your page title here --></title>

    <!-- update this stylesheet href value to your main stylesheet's path -->
    <link id="stylesheet" rel="stylesheet" href="../styles/styles.min.css">
</head>

<body>
    <!-- PAGE COMPONENT -->
    <div class="willow-page-container">

        <!-- SKIP NAV COMPONENT -->
        <div class="willow-skip-nav">
            <a href="#main" class="willow-skip-nav__link" aria-label="skip to main content">Skip to main content</a>
        </div>

        <!-- PAGE HEADER COMPONENT -->
        <header class="willow-page-header" role="banner">
          <div class="container-fluid">
            <div class="willow-page-header__container">
              <div class="willow-page-header__branding"><!-- insert Willow-Logo-Link Component Here --></div>
              <div class="willow-page-header__content-controls">
                  <a class="willow-page-header__content-open" aria-label="Open Menu" href="#">menu</a>
                  <a class="willow-page-header__content-close" aria-label="Close Menu" href="#">close</a>
              </div>
              <div class="willow-page-header__content">
                  <div class="willow-page-header__navigation"><!-- insert Willow-Primary-Nav Component Here --></div>
              </div>
            </div>
          </div>
        </header>

        <!-- PAGE CONTENT COMPONENT -->
        <!-- flex-grow utility class added to allow content to grow vertically -->
        <main class="willow-page-content flex-grow" id="main" role="main">
            <!-- Insert components here if they are a part of your page's main content but need to be full width -->

            <div class="container-fluid">
              <!-- Insert components, HTML or the Bootstrap row (and then columns) here -->
            </div>

        </main>

        <!-- PAGE FOOTER COMPONENT -->
        <footer class="willow-page-footer" role="contentinfo">
          <div class="container-fluid">
            <div class="willow-page-footer__container">
              <div class="willow-page-footer__branding"><!-- insert Willow-Logo-Link Component --></div>
              <div class="willow-page-footer__navigation"><!-- insert Willow-Footer-Nav Component Here --></div>
              <small class="willow-page-footer__copyright"><!-- insert copyright text here --></small>
            </div>
          </div>
        </footer>
    </div>
</body>
</html>
```

Check out the [example site](https://unumux.github.io/willow-testing-site/example-pages.html) for more page examples with Willow and custom components.

---

## Page Layout Explained

**Willow** uses a combination of the [willow-page-container](./components/page-container) and [Bootstrap's fluid container](https://getbootstrap.com/docs/4.0/layout/overview/) to handle page layouts.

[willow-page-container](./components/page-container) makes the page a [flex column](https://css-tricks.com/snippets/css/a-guide-to-flexbox/) which gives the ability to apply the [`.flex-grow` utility class](utilities.md) to any component or row to make it fill extra page height. **willow-page-container** also allows a max-width for styling such as background-colors and images.

[willow-page-content](./components/page-content) is a `<main>` element, should only be used once per page, should be placed immediately after willow-page-header and before the willow-page-footer and should contain the main content of a page and page-related items such as secondary navigation.

The [Bootstrap](https://getbootstrap.com/docs/4.0/layout/overview/) `.container-fluid` element contains a page's content to a certain width and provides a [grid system](https://getbootstrap.com/docs/4.0/layout/grid/) for page columns.

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

### Customizing the Bootstrap Grid

Bootstrap provides documentation about [customizing the grid](https://getbootstrap.com/docs/4.0/layout/grid/#customizing-the-grid)

_Note: To update bootstrap grid variables, the code will need to be before you import a Willow theme. See `$grid-columns` below._

```scss
// file: my-project/styles/styles.scss
$grid-columns: 10;

//theme import
@import "node_modules/@unumux/theme-name-here/styles";
```
