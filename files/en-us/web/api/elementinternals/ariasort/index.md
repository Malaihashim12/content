---
title: "ElementInternals: ariaSort property"
short-title: ariaSort
slug: Web/API/ElementInternals/ariaSort
page-type: web-api-instance-property
browser-compat: api.ElementInternals.ariaSort
---

{{APIRef("Web Components")}}

The **`ariaSort`** property of the {{domxref("ElementInternals")}} interface reflects the value of the [`aria-sort`](/en-US/docs/Web/Accessibility/ARIA/Reference/Attributes/aria-sort) attribute, which indicates if items in a table or grid are sorted in ascending or descending order.

> [!NOTE]
> Setting aria attributes on `ElementInternals` allows default semantics to be defined on a custom element. These may be overwritten by author-defined attributes, but ensure that default semantics are retained should the author delete those attributes, or fail to add them at all. For more information see the [Accessibility Object Model explainer](https://wicg.github.io/aom/explainer.html#default-semantics-for-custom-elements-via-the-elementinternals-object).

## Value

A string with one of the following values:

- `"ascending"`
  - : Items are sorted in ascending order by this column.
- `"descending"`
  - : Items are sorted in descending order by this column.
- `"none"`
  - : There is no defined sort applied to the column.
- `"other"`
  - : A sort algorithm other than ascending or descending has been applied.

## Examples

In this example the value of `ariaSort` is set to "ascending".

```js
class CustomControl extends HTMLElement {
  constructor() {
    super();
    this.internals_ = this.attachInternals();
    this.internals_.ariaSort = "ascending";
  }
  // …
}
```

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- [ARIA: table role](/en-US/docs/Web/Accessibility/ARIA/Reference/Roles/table_role)
