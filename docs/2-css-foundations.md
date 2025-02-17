## CSS Foundations

### Basic Syntax

![Basic CSS syntax](./attachments/1-html-foundations.jpg)

### Selectors

1. Universal selector `*`

2. Type selectors (`div`, `p`, `h1`, etc.)

3. Class selectors

   Select all elements with the given _class_, which is _an attribute you place on an HTML element_. For example:

   ```html
   <div class="alert-text severe-alert">
     Please agree to our terms of service.
   </div>
   ```

   ```css
   .alert-text {
     color: red;
   }
   ```

   - Syntax: **a period before the class name**.
   - It's valid to add **multiple** classes to a single element, as a space-separated list.

4. ID selectors

   Select all elements with the given ID. ID **cannot be repeated** on a single page, and each element can **only have one** ID.

   ```html
   <div id="title">My Awesome 90's Page</div>
   ```

   ```css
   #title {
     background-color: red;
   }
   ```

   - Syntax: **a hashtag before the ID**

> [!NOTE]
>
> A common pitfall is people overusing the ID attribute when classes will suffice. While there are cases where using an ID makes sense or is needed, such as taking advantage of specificity or having links redirect to a section on the current page, you should use IDs **sparingly** (if at all).

#### Grouping Selector

Two or more groups of elements share some styles.

```css
.read,
.unread {
  color: white;
  background-color: black;
}
```

#### Chaining Selector

Apply on an element that has both A and B classes, or class+ID.

```css
.subsection.header {
  color: red;
}
.subsection#preview {
  color: blue;
}
```

#### Descendant Combinator

```css
.ancestor .contents {
  /* some declarations */
}
```

Children will only be selected if it is nested inside `ancestor`, **regardless of how deep that nesting is**.

### Properties

1. Setting colors and background colors

   ```css
   p {
     color: #1100ff; /* HEX */
     background-color: #33ffaa8b; /* with transparency 00-ff */
     color: rgba(100, 0, 127, 0.3);
     color: rgb(100, 0, 127);
     color: hsl(15, 82%, 56%);
   }
   ```

2. Font-related: `font-family`, `font-size: 22px`, `font-weight: 200 (1-1000)`

   - `font-family` can be a comma-separated list of values. Values can be **specific font family** names **quoted**, OR **generic family** names like `serif` **unquoted**. Browser will match them by a descending order.
   - Best practice: **Start with the best font and end with a generic font family as a fallback.**

3. Text alignment: `text-align: center`

4. Image size

   ```css
   img {
     height: auto; /* use auto to preserve proportions */
     width: 500px;
   }
   ```

   - Best practice: include these properties both in HTML and CSS for image elements. (When these values aren’t included, if an image takes longer to load than the rest of the page contents, it won’t take up any space on the page at first but will suddenly cause a drastic shift of the other page contents once it does load in. Explicitly stating a `height` and `width` prevents this from happening, as space will be “reserved” on the page and appear blank until the image loads.)

### Adding CSS to HTML

#### Most common: external

Embed in HTML head section using `<link>` void element.

```html
<head>
  <link rel="stylesheet" href="styles.css">
</head>
```

- The `rel` attribute is required, and it specifies the relationship between the HTML file and the linked file.

#### Sometimes: internal

Embed in HTML head section using `<style>` tag directly.

```html
<head>
  <style>
    div {
      color: white;
      background-color: black;
    }
    p {
      color: red;
    }
  </style>
</head>
```

- The style syntax is same as external CSS.
- This method can be useful for adding unique styles to a _single page_ of a website, but it doesn’t keep things separate like the external method.

#### Rare: inline

Directly apply on an HTML element.

```html
<body>
  <div style="color: white; background-color: black;">...</div>
</body>
```

- Any inline CSS will override the other two methods.

### Cascading Rules

**Specificity** is what determines the order.

1. <u>Which selector</u> we're using matters the most.
   1. ID selectors (most specific selector)
   2. Class selectors
   3. Type selectors
2. When there is no declaration with a selector of higher specificity, a rule with <u>a greater number of selectors</u> will take precedence over another rule with fewer selectors of the same type. Note that special symbols for the universal selector (`*`) as well as combinators (`+`, `~`, `>`, and an empty space) do NOT add any specificity in themselves.
3. Inheritance then applies, even if we don’t explicitly write a rule for those descendants. Typography-based properties (`color`, `font-size`, `font-family`, etc.) are usually inherited, while most other properties aren’t. The exception to this is when directly targeting an element, as this always beats inheritance.
4. The last resort is the order. Whichever rule was the _last_ defined is the winner.

### The Box Model

padding（内容和边框之间的填充）, border（边框）, margin（boxes间距）

- Adjacent margins are **shared**; padding is not shared with margin

- `margin` and `padding` 的多参数语法

  1. `margin: 8px` 全部方向
  2. `margin: 16px 8px` 上下、左右
  3. `margin: 16px 8px 16px 8px` 上、右、下、左（顺时针）

- trick: 如何右对齐/居中？使用 auto 自动占满可用空间

  ```css
  width: 200px;
  margin-left: auto;
  ```

  ```css
  margin: 0 auto;
  ```

- box 的布局模式， `box-sizing` : `content-box`/`border-box`. 区别是：`width` `height`规定的是 content 还是 content+padding+border. 一般用后者（也称为alternative CSS box model），因为所见即所得

- box 的外部显示属性，`display`: `block`/`inline`/`inline-block`

  - If a box has a display value of `block`, then:

    - Does break onto new line.
    - The `width` and `height` properties are respected.
    - Padding, margin and border will cause other elements to be pushed away from the box.
    - If `width` is not specified, the box will extend in the inline direction to fill the space available in its container. In most cases, the box will become as wide as its container, filling up 100% of the space available.
    - Some HTML elements, such as `<h1>` and `<p>`, use `block` as their outer display type by default.

  - If a box has a display type of `inline`, then:

    - Does not break onto a new line.
    - The `width` and `height` properties will not apply.
    - Top and bottom padding, margins, and borders will apply but will not cause other inline boxes to move away from the box.
    - Left and right padding, margins, and borders will apply and will cause other inline boxes to move away from the box.
    - Some HTML elements, such as `<a>`, `<span>`, `<em>` and `<strong>` use `inline` as their outer display type by default.

- `div` 是常用的 block 通用块，`span` 是常用的 inline 通用块，无语义而是用于划分 class/ID
