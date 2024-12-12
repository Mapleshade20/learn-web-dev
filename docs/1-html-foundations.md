# HTML Foundations

## Elements & Tags

1. Opening tag, some text content, closing tag `<p>text</p>`

   [A vast list of predefined tags](https://developer.mozilla.org/en-US/docs/Web/HTML/Element). Using the correct tags can have a big impact on two aspects of your sites: how they are *ranked in search engines*; and how accessible they are to users who rely on assistive technologies, like *screen readers*. Using the correct elements for content is called *semantic HTML*.

2. Void elements `<br>` `<img>`

   Some elements do not have a closing tag because they don't wrap content inside.

> [!WARNING]
>
> You might also see usages like `<br />` or `<img />`, called "self-closing tags". They are used often for historical reasons. Browsers render them just fine, but the latest version of the HTML specification **discourages their use and considers them invalid**.



## HTML Boilerplate

- Web servers by default look for `index.html` page when users land on websites.
- Starts with a DOCTYPE declaration specifying HTML version. Latest HTML5 requires `<!DOCTYPE html>`.
- Needs a root element `<html>` `</html>`. Usually includes `lang="en"` attribute.
- Section 1: `<head>` element for meta-information about the webpage. Not for displaying content.
  - Meta `<meta>` element that has attribute `chatset="utf-8"`.
  - Title `<title>` element for browser tab title.

- Section 2: `<body>` element



> [!TIP]
>
> Three ways to view HTML: double click open file; drag file into browser; use terminal command `firefox ./index.html` or `google-chrome ./index.html`