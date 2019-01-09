[Back to Main Readme](../../README.md) > [Tutorials](./readme.md) > Make a Page

# Make a Page

In this tutorial we'll create a simple HTML page.

- [Setup](#setup)
- [Adding common components](#add-common-components)
- [Adding more components](#add-more-components)

---

## Setup

We'll start by setting up a basic page

1. Create your HTML file in your project
2. In the `<head>` include a link to your primary stylesheet
3. The first component to include within `<body>` is **willow-page-container**. This helps us with the vertical layout of our page
    - [willow-page-container details](../../components/page-container/readme.md)
4. Below the `<body>` include a link to your primary script file

```HTML
<!-- 1. index.html -->
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0">
    <title>Demo Website</title>
    <!-- 2. PRIMARY STYLESHEET -->
    <link id="stylesheet" rel="stylesheet" href="../styles/styles.min.css">
</head>

<body>
    <!-- 3. PAGE COMPONENT -->
    <div class="willow-page-container">


    </div>
    <!-- 4. PRIMARY SCRIPT FILE -->
    <script src="../scripts/site.min.js"></script>
</body>

</html>
```

## Add Common Components

Pages usually have a header and footer so now we'll add those components. We will also add an area for our page's content, and the Skip Nav component to make our website accesible.

1. Add **willow-skip-nav** - [copy HTML](../../components/skip-nav/readme.md#html-snippet)
    - Update the `href` attribute to match the `id` of willow-page-content
    - Note this component should always be the first thing in the **willow-page-container**
2. Add **willow-page-header** - [copy the HTML](../../components/page-header/readme.md#html-snippet)
3. Add **willow-page-content** - [copy the HTML](../../components/page-content/readme.md#html-snippet)
    - Set the `id` value on this component for later use with willow-skip-nav
4. Add **willow-page-footer** - [copy the HTML](../../components/page-footer/readme.md#html-snippet)

```HTML
<!-- index.html -->
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0">
    <title>Demo Website</title>
    <!-- PRIMARY STYLESHEET -->
    <link id="stylesheet" rel="stylesheet" href="../styles/styles.min.css">
</head>

<body>
    <!-- PAGE COMPONENT -->
    <div class="willow-page-container">
        <!-- 1. SKIP NAV COMPONENT -->
        <div class="willow-skip-nav">
            <a href="#mainContent" class="willow-skip-nav__link" aria-label="skip to main content">Skip to Content</a>
        </div>
        <!-- 2. PAGE HEADER COMPONENT -->
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

        <!-- 3. PAGE CONTENT COMPONENT -->
        <main class="willow-page-content" id="mainContent" role="main">
            <!-- insert components here -->
        </main>

        <!-- 4. PAGE FOOTER COMPONENT -->
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
    <!-- PRIMARY SCRIPT FILE -->
    <script src="../scripts/site.min.js"></script>
</body>

</html>
```

## Add More Components

So now you have a page with some basic components in place.  Now we'll add some components within the ones you already have.  

### Let's improve the header

1. Let's add a logo to our page header. Add **willow-logo-link** within the page header's branding container - [copy the HTML](../../components/logo-link/readme.md#html-snippet)
2. Review and update willow-logo-link's attributes as needed
3. Now we want to add navigation to our header. Add **willow-primary-nav** within the page header's navgiation element - [copy the HTML](../../components/primary-nav/readme.md#html-snippet)
4. Review and update willow-primary-nav's attributes and content as needed

```HTML
<!-- PAGE HEADER COMPONENT -->
<header class="willow-page-header" role="banner">
    <div class="container-fluid">
        <div class="willow-page-header__container">
        <div class="willow-page-header__branding">
            <!-- 1. and 2. LOGO LINK COMPONENT -->
            <a class="willow-logo-link" href="/" aria-label="go to home page"><img class="willow-logo-link__image" src="https://via.placeholder.com/350x150" alt="Company Logo"></a>
        </div>
        <div class="willow-page-header__content-controls">
            <a class="willow-page-header__content-open" aria-label="Open Menu" href="#">menu</a>
            <a class="willow-page-header__content-close" aria-label="Close Menu" href="#">close</a>
        </div>
        <div class="willow-page-header__content">
            <div class="willow-page-header__navigation">
                <!-- 3. AND 4. PRIMARY NAV COMPONENT -->
                <nav class="willow-primary-nav" role="navigation" aria-label="primary">
                    <h1 class="willow-primary-nav__heading sr-only">Site Primary Menu</h1>
                    <ul class="willow-primary-nav__list">
                        <li class="willow-primary-nav__item">
                            <a class="willow-primary-nav__link" href="/">Home</a>
                        </li>
                        <li class="willow-primary-nav__item">
                            <a class="willow-primary-nav__link" href="/components.html" aria-label="See available components">Components</a>
                        </li>
                        <li class="willow-primary-nav__item">
                            <a class="willow-primary-nav__link" href="/example-pages.html">Example Pages</a>
                        </li>
                    </ul>
                </nav>
            </div>
        </div>
        </div>
    </div>
</header>
```

### Let's add page content

Our page needs to have 2 columns. The left column will be smaller and contain a secondary menu. The right column will contain our page's content (text/images etc).

1. Add a Bootstrap container-fluid to make sure our content doesn't break our max-width for the page
2. Now add a Bootstrap row
3. Inside of the row use the Bootstrap columns to create the small left column
4. Let's put the **willow-secondary-nav** in this column
5. Review and update willow-secondary-nav's attributes and content as needed
6. Inside of the row use the Bootstrap columns to create the larger right column
7. Let's put the some basic content in this column

```HTML
<!-- PAGE CONTENT COMPONENT -->
<main class="willow-page-content" id="mainContent" role="main">
    <!-- 1. BOOTSTRAP CONTAINER-FLUID -->
    <div class="container-fluid">
        <!-- 2. BOOTSTRAP ROW -->
        <div class="row">
            <!-- 3. BOOTSTRAP COLUMN -->
            <div class="col-md-3">
                <!-- 4. and 5. SECONDARY NAV COMPONENT -->
                <nav class="willow-secondary-nav" role="navigation" aria-label="secondary">
                    <h1 class="willow-secondary-nav__heading">Content Item Examples</h1>
                    <ul class="willow-secondary-nav__list">
                        <li class="willow-secondary-nav__item"><a class="willow-secondary-nav__link" href="#headings">Headings</a></li>
                        <li class="willow-secondary-nav__item"><a class="willow-secondary-nav__link" href="#text">Text</a></li>
                        <li class="willow-secondary-nav__item"><a class="willow-secondary-nav__link" href="#tables">Tables</a></li>
                    </ul>
                </nav>
            </div>
            <!-- 6. BOOTSTRAP COLUMN -->
            <div class="col-md-9">
                <!-- 7. CONTENT -->
                <section id="headings">
                    <h1>Here's how headings will look</h1>
                    <h1>Heading made from an h1 element</h1>
                    <h2>Heading made from an h2 element</h2>
                    <h3>Heading made from an h3 element</h3>
                    <h4>Heading made from an h4 element</h4>
                    <h5>Heading made from an h5 element</h5>
                    <h6>Heading made from an h6 element</h6>
                </section>
                <section id="text">
                    <h1>Here's how all kinds of inline text elements will look</h1>
                    <p><code>a, mark, small</code>: Lorem ipsum dolor sit amet consectetur adipisicing elit. <a href="#">Doloribus fugiat ex quibusdam</a> nesciunt voluptatibus quam odio, nisi officiis nobis minima quis repellat qui recusandae incidunt architecto eos vero tempora minus accusantiu suscipit exercitationem excepturi doloremque nemo! <mark>Dolor reiciendis recusandae tempore explicabo corporis</mark> doloribus vel sapiente officiis inventore? Fugit nihil veniam porro placeat enim obcaecati beatae. Lorem ipsum, <small>dolor sit amet consectetur adipisicing elit. Expedita quas unde porro exercitationem dolore</small> libero modi, omnis quis mollitia perferendis atque a laborum placeat fugit!</p>

                    <p><code>blockquote</code>:</p>
                    <blockquote><p>Iure voluptates quia, vel quis repellendus quo veritatis vero maiores dolore consequatur doloremque commodi expedita, eaque sint! Ipsa inventore adipisci, iusto, iure quod laboriosam autem voluptas dolor.</p></blockquote>

                    <p><code>ul, ol</code>:</p>
                    <ul>
                        <li>List Item</li>
                        <li><a href="#">Link Item</a></li>
                        <li>List item with sub items (ordered)
                            <ol>
                                <li>Sub item</li>
                                <li><a href="#">Sub Link Item</a></li>
                                <li>Sub item</li>
                            </ol>
                        </li>
                        <li>List item with sub items (unordered)
                            <ul>
                                <li>Sub item</li>
                                <li><a href="#">Sub Link Item</a></li>
                                <li>Sub item</li>
                            </ul>
                        </li>
                    </ul>

                    <ol>
                        <li>List item</li>
                        <li><a href="#">Link item</a></li>
                        <li>List item with sub items (ordered)
                            <ol>
                                <li>Sub item</li>
                                <li><a href="#">Link item</a></li>
                                <li>Sub item</li>
                            </ol>
                        </li>
                        <li>List item with sub items (unordered)
                            <ul>
                                <li>Sub item</li>
                                <li><a href="#">Link item</a></li>
                                <li>Sub item</li>
                            </ul>
                        </li>
                    </ol>
                </section>
                <section id="tables">
                    <h1>Here's how tables will look</h1>
                    <table>
                        <thead>
                            <tr>
                                <th scope="col">Column Heading 1</th>
                                <th scope="col">Column Heading 2</th>
                                <th scope="col">Column Heading 3</th>
                                <th scope="col">Column Heading 4</th>
                                <th scope="col">Column Heading 5</th>
                                <th scope="col">Column Heading 6</th>
                                <th scope="col">Column Heading 7</th>
                            </tr>
                        </thead>
                        <tbody>
                            <tr>
                                <td>Item 1</td>
                                <td>Item 2</td>
                                <td>Item 3</td>
                                <td>Item 4</td>
                                <td>Item 5</td>
                                <td>Item 6</td>
                                <td>Item 7</td>
                            </tr>
                            <tr>
                                <td>Item 1</td>
                                <td>Item 2</td>
                                <td>Item 3</td>
                                <td>Item 4</td>
                                <td>Item 5</td>
                                <td>Item 6</td>
                                <td>Item 7</td>
                            </tr>
                            <tr>
                                <td>Item 1</td>
                                <td>Item 2</td>
                                <td>Item 3</td>
                                <td>Item 4</td>
                                <td>Item 5</td>
                                <td>Item 6</td>
                                <td>Item 7</td>
                            </tr>
                        </tbody>
                    </table>
                </section>
            </div>
        </div>
    </div>
</main>

```

### Let's improve the footer

1. Let's add a logo to our page footer. Add **willow-logo-link** within the page footers's branding container - [copy the HTML](../../components/logo-link/readme.md#html-snippet)
2. Review and update willow-logo-link's attributes as needed
3. Now we want to add navigation to our footer. Add **willow-footer-nav** within the page footers's navgiation element - [copy the HTML](../../components/footer-nav/readme.md#html-snippet)
4. Review and update willow-footer-nav's attributes and content as needed
5. add content to the page-footer's copyright element

```HTML
<!-- PAGE FOOTER COMPONENT -->
<footer class="willow-page-footer" role="contentinfo">
    <div class="container-fluid">
        <div class="willow-page-footer__container">
            <div class="willow-page-footer__branding">
                <a class="willow-logo-link" href="/" aria-label="go to home page"><img class="willow-logo-link__image" src="https://via.placeholder.com/350x150" alt="Company Logo"></a>
            </div>
            <div class="willow-page-footer__navigation">
                <nav class="willow-footer-nav" role="navigation" aria-label="footer">
                    <h1 class="willow-footer-nav__heading sr-only">Site Footer Menu</h1>
                    <ul class="willow-footer-nav__list">
                        <li class="willow-footer-nav__item"><a class="willow-footer-nav__link" href="/">Home</a></li>
                        <li class="willow-footer-nav__item"><a class="willow-footer-nav__link" href="/components.html" aria-label="See available components">Components</a></li>
                        <li class="willow-footer-nav__item"><a class="willow-footer-nav__link" href="/example-pages.html">Example Pages</a></li>
                    </ul>
                </nav>
            </div>
            <small class="willow-page-footer__copyright">Here is an example of a copyright. 2018.</small>
        </div>
    </div>
</footer>
```

[Back to top](#make-a-page)
