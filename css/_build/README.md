# Build

This directory houses components built entirely out of context of their page.
There are two classes of component:

* **Integrated:** These are components that inherit styles from the rest of the
  CSS project, and cannot be properly rendered without other files being present
  (e.g. reset, Normalize.css, global `box-sizing`, etc.). They cannot be
  compiled into their own corresponding CSS files without errors; they tend to
  be integrated into our `main.css` file. The [Calendar
  component](https://github.com/csswizardry/discovr/blob/master/css/components/_components.calendar.scss)
  is an example of an Integrated component.
* **Isolated:** These are components that can be built without needing any other
  CSS files to be present; they do not lean on any kind of reset or other
  existing styles. These components are fully encapsulated and can be moved
  between projects pretty easily, and can usually be compiled into their own
  corresponding CSS files. The only dependencies they might have are our
  settings and components. The [Pagination
  component](https://github.com/csswizardry/discovr/blob/master/css/components/components.pagination.scss)
  is an example of an Isolated component.

## `view.html`

The
[`view.html`](https://github.com/csswizardry/discovr/blob/master/css/_build/view.html)
file contains several randomly sized `iframe`s through which we view our
components as we’re building them. This gives us a simultaneous view of several
different responsive variations of our components in one page, meaning we can
develop and compare components without having to constantly resize our browser
window. Simply point your `iframe`s at the HTML file for the component you’re
currently building.
