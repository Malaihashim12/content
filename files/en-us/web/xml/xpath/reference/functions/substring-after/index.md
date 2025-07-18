---
title: substring-after
slug: Web/XML/XPath/Reference/Functions/substring-after
page-type: xpath-function
sidebar: xmlsidebar
---

The `substring-after` function returns a string that is the rest of a given string after a given substring.

## Syntax

```plain
substring-after( haystack, needle )
```

### Parameters

- `haystack`
  - : The string to be evaluated. Part of this string will be returned.
- `needle`
  - : The substring to search for. Everything after the first occurrence of `needle` in `haystack` will be returned.

### Return value

A string.

### Examples

| XPath Example                  | Output         |
| ------------------------------ | -------------- |
| `substring-after('aa-bb','-')` | `bb`           |
| `substring-after('aa-bb','a')` | `a-bb`         |
| `substring-after('aa-bb','b')` | `b`            |
| `substring-after('aa-bb','q')` | (empty string) |

## Specifications

[XPath 1.0 4.2](https://www.w3.org/TR/xpath-10/#function-substring-after)

## Gecko support

Supported.
