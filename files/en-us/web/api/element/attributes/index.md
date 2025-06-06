---
title: "Element: attributes property"
short-title: attributes
slug: Web/API/Element/attributes
page-type: web-api-instance-property
browser-compat: api.Element.attributes
---

{{ APIRef("DOM") }}

The **`Element.attributes`** property returns a live collection
of all attribute nodes registered to the specified node. It is a
{{domxref("NamedNodeMap")}}, not an `Array`, so it has no {{jsxref("Array")}}
methods and the {{domxref("Attr")}} nodes' indexes may differ among browsers. To be more
specific, `attributes` is a key/value pair of strings that represents any
information regarding that attribute.

## Value

A {{domxref("NamedNodeMap")}} object.

## Examples

### Basic examples

```js
// Get the first <p> element in the document
const paragraph = document.querySelector("p");
const attributes = paragraph.attributes;
```

### Enumerating elements attributes

You can enumerate through an element's attributes using [`for...of`](/en-US/docs/Web/JavaScript/Reference/Statements/for...of).
The following example runs through the attribute nodes for the element in the document
with id "paragraph", and prints each attribute's value.

```html
<p id="paragraph" class="green" contenteditable>Sample Paragraph</p>
<input type="button" value="Show paragraph attribute name and value" />
<pre id="result"></pre>
```

```css
.green {
  color: green;
}
```

```js
const paragraph = document.getElementById("paragraph");
const result = document.getElementById("result");
const btn = document.querySelector("input[type='button']");

btn.addEventListener("click", () => {
  // First, let's verify that the paragraph has some attributes
  if (paragraph.hasAttributes()) {
    let output = "Attributes of first paragraph:\n";
    for (const attr of paragraph.attributes) {
      output += `${attr.name} -> ${attr.value}\n`;
    }
    result.textContent = output;
  } else {
    result.textContent = "No attributes to show";
  }
});
```

{{EmbedLiveSample('enumerating_elements_attributes', 100, 300)}}

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- {{domxref("NamedNodeMap")}}, the interface of the returned object
- Cross-browser compatibility considerations: on [quirksmode](https://quirksmode.org/dom/core/#attributes)
