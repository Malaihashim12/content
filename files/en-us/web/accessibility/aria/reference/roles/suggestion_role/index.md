---
title: "ARIA: suggestion role"
short-title: suggestion
slug: Web/Accessibility/ARIA/Reference/Roles/suggestion_role
page-type: aria-role
sidebar: accessibilitysidebar
---

The `suggestion` role semantically denotes a single proposed change to an editable document. This should be used on an element that wraps an element with an `insertion` role, and one with a `deletion` role.

## Examples

When you've got a content change that involves an insertion _and_ a deletion, there is no way for a screen reader user to work out if the two are related or not. This is the job of `role="suggestion"`, which should be set on an element wrapping both of them like so:

```html
<p>
  Freida's pet is a
  <span role="suggestion">
    <span role="deletion">black Cat called Luna</span>
    <span role="insertion">purple T. Rex called Tiny</span></span
  >.
</p>
```

We could even provide an information box saying who made the suggestion and when, and associate it with the suggestion via [`aria-details`](/en-US/docs/Web/Accessibility/ARIA/Reference/Attributes/aria-details):

```html
<p>
  Freida's pet is a
  <span role="suggestion" aria-details="comment-source">
    <span role="deletion">black Cat called Luna</span>
    <span role="insertion">purple T. Rex called Tiny</span></span
  >.
</p>

<div id="comment-source">
  Suggested by Chris,
  <time datetime="2019-03-30T19:29">March 30 2019, 19:29</time>
</div>
```

Browsers tend to provide a default black strikethrough for deletions, and a black underline for insertions when using the HTML elements that implicitly expose these roles. But when using explicit ARIA roles to modify HTML elements, such as divs, you'll need to use CSS to customize the visual styling for such deletions and insertions.

## Best practices

### Prefer HTML

Using the [`<ins>`](/en-US/docs/Web/HTML/Reference/Elements/ins) and [`<del>`](/en-US/docs/Web/HTML/Reference/Elements/del) element will automatically communicate a section has a role of `insertion` or `deletion`. If at all possible, prefer using the HTML elements.

## Specifications

Will be part of WAI-ARIA 1.3, which is still being drafted.
