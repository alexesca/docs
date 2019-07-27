+++
title = "SVGs"
description = ""
weight = 29
alwaysopen = true
+++

{{% alert theme="warning" %}}Minimal version: **0.1.58**{{% /alert %}}

To enable SVG nodes install svg-to-pdfkit:
```
npm install svg-to-pdfkit --save
```

SVGs are much like [images](/docs/document-definition-object/images/) except it is not currently possible to refer to SVGs by file or re-use from a dictionary.

```js
var docDefinition = {
  content: [
    {
      // If no width/height/fit is used, then dimensions from the svg element is used.
      svg: '<svg width="300" height="200" viewBox="0 0 300 200">...</svg>'
    },
    {
      // if you specify width, svg will scale proportionally
      svg: '<svg width="300" height="200" viewBox="0 0 300 200">...</svg>',
      width: 150
    },
    {
      // if you specify both width and height - svg will be stretched
      svg: '<svg width="300" height="200" viewBox="0 0 300 200">...</svg>',
      width: 600,
      height: 400
    },
    {
      // you can also fit the svg inside a rectangle
      svg: '<svg width="300" height="200" viewBox="0 0 300 200">...</svg>',
      fit: [150, 100]
    }
};
```