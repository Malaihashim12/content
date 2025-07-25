---
title: place-items
slug: Web/CSS/place-items
page-type: css-shorthand-property
browser-compat: css.properties.place-items
sidebar: cssref
---

The [CSS](/en-US/docs/Web/CSS) **`place-items`** [shorthand property](/en-US/docs/Web/CSS/CSS_cascade/Shorthand_properties) aligns items along both the block and inline directions at once. It sets the values of the {{CSSxRef("align-items")}} and {{CSSxRef("justify-items")}} properties. If the second value is not set, the first value is also used for it.

{{InteractiveExample("CSS Demo: place-items")}}

```css interactive-example-choice
place-items: center stretch;
```

```css interactive-example-choice
place-items: center start;
```

```css interactive-example-choice
place-items: start end;
```

```css interactive-example-choice
place-items: end center;
```

```html interactive-example
<section class="default-example" id="default-example">
  <div class="example-container">
    <div class="transition-all" id="example-element">
      <div>One</div>
      <div>Two</div>
      <div>Three</div>
    </div>
  </div>
</section>
```

```css interactive-example
#example-element {
  border: 1px solid #c5c5c5;
  display: grid;
  grid-template-columns: 1fr 1fr;
  grid-auto-rows: 80px;
  grid-gap: 10px;
  width: 220px;
}

#example-element > div {
  background-color: rgb(0 0 255 / 0.2);
  border: 3px solid blue;
}
```

## Constituent properties

This property is a shorthand for the following CSS properties:

- [`align-items`](/en-US/docs/Web/CSS/align-items)
- [`justify-items`](/en-US/docs/Web/CSS/justify-items)

## Syntax

```css
/* Positional alignment */
place-items: center;
place-items: normal start;
place-items: center normal;
place-items: start legacy;
place-items: end normal;
place-items: self-start legacy;
place-items: self-end normal;
place-items: flex-start legacy;
place-items: flex-end normal;
place-items: anchor-center;

/* Baseline alignment */
place-items: baseline normal;
place-items: first baseline legacy;
place-items: last baseline normal;
place-items: stretch legacy;

/* Global values */
place-items: inherit;
place-items: initial;
place-items: revert;
place-items: revert-layer;
place-items: unset;
```

### Values

One of the following forms:

- A single {{cssxref("align-items")}} value, which is used to set alignment in both block and inline directions.
- An {{cssxref("align-items")}} value, which sets alignment in the block direction, followed by a {{cssxref("justify-items")}} value, which sets alignment in the inline direction.

## Formal definition

{{cssinfo}}

## Formal syntax

{{csssyntax}}

## Examples

### Placing items in a flex container

In flexbox {{cssxref("justify-self")}} or {{cssxref("justify-items")}} do not apply, as on the main axis items are treated as a group. Therefore, the second value will be ignored.

```css hidden
div > div {
  box-sizing: border-box;
  border: 2px solid #8c8c8c;
  width: 50px;
  display: flex;
  align-items: center;
  justify-content: center;
}

#item1 {
  background-color: #8cffa0;
  min-height: 30px;
  font-size: 2em;
}

#item2 {
  background-color: #a0c8ff;
  min-height: 50px;
}

#item3 {
  background-color: #ffa08c;
  min-height: 40px;
}

#item4 {
  background-color: #ffff8c;
  min-height: 60px;
}

#item5 {
  background-color: #ff8cff;
  min-height: 70px;
}

#item6 {
  background-color: #8cffff;
  min-height: 50px;
}

select {
  font-size: 16px;
}

.row {
  margin-top: 10px;
}
```

```html hidden
<div id="container">
  <div id="item1">1</div>
  <div id="item2">2</div>
  <div id="item3">3</div>
</div>

<div class="row">
  <label for="values">place-items: </label>
  <select id="values">
    <option value="stretch">stretch</option>
    <option value="start">start</option>
    <option value="center">center</option>
    <option value="end">end</option>
    <option value="left">left</option>
    <option value="right">right</option>
    <option value="auto center">auto center</option>
    <option value="normal start">normal start</option>
    <option value="center normal">center normal</option>
    <option value="start auto">start auto</option>
    <option value="end normal">end normal</option>
    <option value="self-start auto">self-start auto</option>
    <option value="self-end normal">self-end normal</option>
    <option value="flex-start auto">flex-start auto</option>
    <option value="flex-end normal">flex-end normal</option>
    <option value="left auto">left auto</option>
    <option value="right normal">right normal</option>
    <option value="baseline normal">baseline normal</option>
    <option value="first baseline auto">first baseline auto</option>
    <option value="last baseline normal">last baseline normal</option>
    <option value="stretch auto">stretch auto</option>
  </select>
</div>
```

```js hidden
const values = document.getElementById("values");
const container = document.getElementById("container");

values.addEventListener("change", (evt) => {
  container.style.placeItems = evt.target.value;
});
```

#### CSS

```css
#container {
  height: 200px;
  width: 240px;
  place-items: stretch; /* You can change this value by selecting another option in the list */
  background-color: #8c8c8c;
  display: flex;
}
```

#### Result

{{EmbedLiveSample("Placing_items_in_a_flex_container", 260, 290)}}

### Placing items in a grid container

The following grid container has items which are smaller than the grid areas they are placed in, therefore `place-items` will move them in the block and inline dimensions.

```css hidden
div > div {
  box-sizing: border-box;
  border: 2px solid #8c8c8c;
}

#item1 {
  background-color: #8cffa0;
  min-height: 30px;
  font-size: 2em;
}

#item2 {
  background-color: #a0c8ff;
  min-height: 50px;
}

#item3 {
  background-color: #ffa08c;
  min-height: 40px;
}

#item4 {
  background-color: #ffff8c;
  min-height: 60px;
}

#item5 {
  background-color: #ff8cff;
  min-height: 70px;
}

#item6 {
  background-color: #8cffff;
  min-height: 50px;
}

select {
  font-size: 16px;
}

.row {
  margin-top: 10px;
}
```

```html hidden
<div id="grid-container">
  <div id="item1">1</div>
  <div id="item2">2</div>
  <div id="item3">3</div>
  <div id="item4">4</div>
  <div id="item5">5</div>
</div>

<div class="row">
  <label for="grid-values">place-items: </label>
  <select id="grid-values">
    <option value="stretch">stretch</option>
    <option value="start">start</option>
    <option value="center">center</option>
    <option value="end">end</option>
    <option value="left">left</option>
    <option value="right">right</option>
    <option value="auto center">auto center</option>
    <option value="normal start">normal start</option>
    <option value="center normal">center normal</option>
    <option value="start auto">start auto</option>
    <option value="end normal">end normal</option>
    <option value="self-start auto">self-start auto</option>
    <option value="self-end normal">self-end normal</option>
    <option value="flex-start auto">flex-start auto</option>
    <option value="flex-end normal">flex-end normal</option>
    <option value="left auto">left auto</option>
    <option value="right normal">right normal</option>
    <option value="baseline normal">baseline normal</option>
    <option value="first baseline auto">first baseline auto</option>
    <option value="last baseline normal">last baseline normal</option>
    <option value="stretch auto">stretch auto</option>
  </select>
</div>
```

```js hidden
const values = document.getElementById("grid-values");
const container = document.getElementById("grid-container");

values.addEventListener("change", (evt) => {
  container.style.placeItems = evt.target.value;
});
```

#### CSS

```css
#grid-container {
  height: 200px;
  width: 240px;
  place-items: stretch; /* You can change this value by selecting another option in the list */
  background-color: #8c8c8c;
  display: grid;
  grid-template-columns: repeat(3, 1fr);
}

#grid-container > div {
  width: 50px;
}
```

#### Result

{{EmbedLiveSample("Placing_items_in_a_grid_container", 260, 290)}}

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- {{CSSxRef("align-items")}}
- {{CSSxRef("align-self")}}
- {{CSSxRef("justify-items")}}
- {{CSSxRef("justify-self")}}
- [Basic concepts of flexbox](/en-US/docs/Web/CSS/CSS_flexible_box_layout/Basic_concepts_of_flexbox)
- [Aligning items in a flex container](/en-US/docs/Web/CSS/CSS_flexible_box_layout/Aligning_items_in_a_flex_container)
- [Box alignment in grid layout](/en-US/docs/Web/CSS/CSS_box_alignment/Box_alignment_in_grid_layout)
- [CSS box alignment](/en-US/docs/Web/CSS/CSS_box_alignment) module
