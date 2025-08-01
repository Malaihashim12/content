---
title: "WebGLRenderingContext: copyTexSubImage2D() method"
short-title: copyTexSubImage2D()
slug: Web/API/WebGLRenderingContext/copyTexSubImage2D
page-type: web-api-instance-method
browser-compat: api.WebGLRenderingContext.copyTexSubImage2D
---

{{APIRef("WebGL")}}{{AvailableInWorkers}}

The **`WebGLRenderingContext.copyTexSubImage2D()`** method of
the [WebGL API](/en-US/docs/Web/API/WebGL_API) copies pixels from the current
{{domxref("WebGLFramebuffer")}} into an existing 2D texture sub-image.

## Syntax

```js-nolint
copyTexSubImage2D(target, level, xoffset, yoffset, x, y, width, height)
```

### Parameters

- `target`
  - : A {{domxref("WebGL_API/Types", "GLenum")}} specifying the binding point (target) of the active texture.
    Possible values:
    - `gl.TEXTURE_2D`: A two-dimensional texture.
    - `gl.TEXTURE_CUBE_MAP_POSITIVE_X`: Positive X face for a cube-mapped
      texture.
    - `gl.TEXTURE_CUBE_MAP_NEGATIVE_X`: Negative X face for a cube-mapped
      texture.
    - `gl.TEXTURE_CUBE_MAP_POSITIVE_Y`: Positive Y face for a cube-mapped
      texture.
    - `gl.TEXTURE_CUBE_MAP_NEGATIVE_Y`: Negative Y face for a cube-mapped
      texture.
    - `gl.TEXTURE_CUBE_MAP_POSITIVE_Z`: Positive Z face for a cube-mapped
      texture.
    - `gl.TEXTURE_CUBE_MAP_NEGATIVE_Z`: Negative Z face for a cube-mapped
      texture.

- `level`
  - : A {{domxref("WebGL_API/Types", "GLint")}} specifying the level of detail. Level 0 is the base image
    level and level _n_ is the n-th mipmap reduction level.
- `xoffset`
  - : A {{domxref("WebGL_API/Types", "GLint")}} specifying the horizontal offset within the texture image.
- `yoffset`
  - : A {{domxref("WebGL_API/Types", "GLint")}} specifying the vertical offset within the texture image.
- `x`
  - : A {{domxref("WebGL_API/Types", "GLint")}} specifying the x coordinate of the lower left corner where to
    start copying.
- `y`
  - : A {{domxref("WebGL_API/Types", "GLint")}} specifying the y coordinate of the lower left corner where to
    start copying.
- `width`
  - : A {{domxref("WebGL_API/Types", "GLsizei")}} specifying the width of the texture.
- `height`
  - : A {{domxref("WebGL_API/Types", "GLsizei")}} specifying the height of the texture.

### Return value

None ({{jsxref("undefined")}}).

## Examples

```js
gl.copyTexSubImage2D(gl.TEXTURE_2D, 0, 0, 0, 0, 0, 16, 16);
```

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- {{domxref("WebGLRenderingContext.copyTexImage2D()")}}
- {{domxref("WebGLRenderingContext.texImage2D()")}}
- {{domxref("WebGLRenderingContext.texSubImage2D()")}}
- {{domxref("WebGLRenderingContext.compressedTexImage2D()")}}
