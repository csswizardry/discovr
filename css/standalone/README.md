# Standalone Components

If we ever need to compile UI components who are completely self-sufficient
(e.g. we can get a fully-formed pagination encapsulated in just one file) we

* create a new `_components.<file>.scss` in the components directory;
* `@import` all of our settings and tools into that file right at the beginning;
* do not `@import` any other files, particularly ones that produce CSS.

This means that we can create a UI component that has zero dependency on any
other CSS; it is completely encapsulated and deployable outside of the wider CSS
project (and/or within it). We still have all of our project’s setting and tools
available to us for building this component.

That file might look like this:

```
/*------------------------------------*\
  #<FILE>
\*------------------------------------*/

// The <file> component needs to be usable outside of the larger ITCSS project.
// As such, we import all of our Sass settings and tools (note, we are not
// allowed to import any CSS here, only Sass) so that we have useful config
// available to us before building out the <file>.
//
// This means that we end up with a compiled `components.<file>.css` file
// that can be included into a project without the need for any further
// dependencies or extraneous CSS.

@import "../setup";





.c-<file> {
  ...
}
```
