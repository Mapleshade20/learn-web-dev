# HTML Foundations

## Elements & Tags

1. Opening tag, some text content, closing tag `<p>text</p>`

   [A vast list of predefined tags](https://developer.mozilla.org/en-US/docs/Web/HTML/Element). Using the correct tags can have a big impact on two aspects of your sites: how they are *ranked in search engines*; and how accessible they are to users who rely on assistive technologies, like *screen readers*. Using the correct elements for content is called *semantic HTML*.

2. Void elements `<br>` `<img>` **do not have a closing tag** because they don't wrap content inside.


> [!WARNING]
>
> You might also see usages like `<br />` or `<img />`, called "self-closing tags". They are used often for historical reasons (compatibility with xhtml). Browsers render them just fine, but the latest version of the HTML specification **discourages their use and considers them invalid**.



## HTML Boilerplate

- Web servers by default look for `index.html` page when users land on websites.
- Starts with a DOCTYPE declaration specifying HTML version. Latest HTML5 requires `<!DOCTYPE html>`.
- Needs a root element `<html>` `</html>`. Usually includes `lang="en"` attribute.
- Section 1: `<head>` element for meta-information about the webpage. Not for displaying content.
  - Meta `<meta>` element that has attribute `chatset="utf-8"`.
  - Title `<title>` element for browser tab title.

- Section 2: `<body>` element.



> [!TIP]
>
> Three ways to view HTML: double click open file; drag file into browser; use terminal command `firefox ./index.html` or `google-chrome ./index.html`



## Text Styles

1. Paragraphs are not declared with new line. Instead, use `<p>` `</p>`.
2. Headings from `<h1>` to `<h6>`. An `<h1>` heading should always be used for the heading of the overall page.
3. Bold: `<strong>`. Italic emphasis: `<em>`. Italic but no emphasis: `<i>` (often for foreign words, technical terms, thoughts, etc.)
4. Comments are not visible to the browser: `<!-- I am an html comment -->`

### Lists

1. Unordered lists:

   ```html
   <ul>
       <li>Item 1</li>
       <li>Item 2</li>
   </ul>
   ```

2. Ordered lists:

   ```html
   <ol>
       <li>Item 1</li>
       <li>Item 2</li>
   </ol>
   ```

### Links and Images

- Links use `<a>`, and require a `href` **HTML attribute**. Attributes are `name=value` pairs that go into the tag.
  - If the `href` attribute is present, the browser will give the text a blue color and underline it to signify it is a link.
  - By default `target="_self"` attribute is set, and the opened link will replace current webpage. Use `target="_blank"` attribute to open it in a new page, and always attach a `rel="noopener noreferrer"` attribute (the first is included in the second) to prevent *plishing attacks*.
  - Allow absolute links and relative links.

- Images use `<img>` (void element), and require a `src` attribute.
  - Besides the `src` attribute, every image element must also have an `alt` (alternative text) attribute to describe an image.
  - It is a good habit to always specify `height="xxx"` and `width="xxx"` attributes on every image, even when the image is the correct size or you are using CSS to modify  it.