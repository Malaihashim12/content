---
title: "XRView: projectionMatrix property"
short-title: projectionMatrix
slug: Web/API/XRView/projectionMatrix
page-type: web-api-instance-property
status:
  - experimental
browser-compat: api.XRView.projectionMatrix
---

{{APIRef("WebXR Device API")}}{{SeeCompatTable}}{{SecureContext_Header}}

The {{domxref("XRView")}} interface's read-only
**`projectionMatrix`** property specifies the projection matrix
to apply to the underlying view. This should be used to integrate perspective to
everything in the scene, in order to ensure the result is consistent with what the eye
expects to see.

> [!NOTE]
> Failure to apply proper perspective, or inconsistencies
> in perspective, may result in possibly serious user discomfort or distress.

## Value

A {{jsxref("Float32Array")}} object representing the projection matrix for the view.
The projection matrix for each eye's view is used to ensure that the correct area of the
scene is presented to each eye in order to create a believable 3D scene without
introducing discomfort for the user.

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}
