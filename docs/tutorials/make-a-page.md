[Back to Main Readme](../../README.md) > [Tutorials](./readme.md) > Make a Page

# Make a Page

In this tutorial we'll create a simple HTML page.

- [Setup](#setup)
- [Adding common components](#add-common-components)
- [Adding more components](#add-more-components)
- Maybe more sections here ....

---

## Setup

We'll start by setting up a basic page

1. Create your HTML file in your project
2. In the `<head>` include a link to your primary stylesheet
3. The first component to include within `<body>` is **willow-page-container**
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

1. Add **willow-page-header** - [copy the HTML](../../components/page-header/readme.md#html-snippet)
2. Add **willow-page-content** - [copy the HTML](../../components/page-content/readme.md#html-snippet)
    - Set the `id` value on this component for later use with willow-skip-nav
3. Add **willow-page-footer** - [copy the HTML](../../components/page-footer/readme.md#html-snippet)
4. Add **willow-skip-nav** above the willow-page-header - [copy HTML](../../components/skip-nav/readme.md#html-snippet)
    - Update the `href` attribute to match the `id` of willow-page-content

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
        <!-- SKIP NAV COMPONENT -->
        <div class="willow-skip-nav">
            <a href="#mainContent" class="willow-skip-nav__link" aria-label="skip to main content">Skip to Content</a>
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
        <main class="willow-page-content" id="mainContent" role="main">
            <!-- insert components here -->
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
            <a class="willow-logo-link" href="/" aria-label="go to home page"><img class="willow-logo-link__image" src="https://via.placeholder.com/350x150" alt="Company Logo"></a>
        </div>
        <div class="willow-page-header__content-controls">
            <a class="willow-page-header__content-open" aria-label="Open Menu" href="#">menu</a>
            <a class="willow-page-header__content-close" aria-label="Close Menu" href="#">close</a>
        </div>
        <div class="willow-page-header__content">
            <div class="willow-page-header__navigation">
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

### Let's add some page content

To Be Continued...

[Back to top](#make-a-page)
