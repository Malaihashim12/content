---
title: "HTMLElement: contentEditable property"
short-title: contentEditable
slug: Web/API/HTMLElement/contentEditable
page-type: web-api-instance-property
browser-compat: api.HTMLElement.contentEditable
---

{{APIRef("HTML DOM")}}

The **`contentEditable`** property of
the {{domxref("HTMLElement")}} interface specifies whether or not the element is
editable.

This enumerated attribute can have the following values:

- `"true"` indicates that the element is `contenteditable`.
- `"false"` indicates that the element cannot be edited.
- `"plaintext-only"` indicates that the element's raw text is editable, but rich text formatting is disabled.

You can use the {{domxref("HTMLElement.isContentEditable")}} property to test the
computed boolean value of this property.

If the attribute is missing or its value is invalid, its value is inherited from its parent element: so the element
is editable (or not) based on the parent element.

## Value

A string.

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- {{domxref("HTMLElement.isContentEditable")}}
- The [`contenteditable`](/en-US/docs/Web/HTML/Reference/Global_attributes/contenteditable) global attribute.
