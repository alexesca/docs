+++
title = "Styling"
description = ""
weight = 21
alwaysopen = true
+++

pdfmake makes it possible to style any paragraph or its part:

```js
var docDefinition = {
  content: [
    // if you don't need styles, you can use a simple string to define a paragraph
    'This is a standard paragraph, using default style',

    // using a { text: '...' } object lets you set styling properties
    { text: 'This paragraph will have a bigger font', fontSize: 15 },

    // if you set the value of text to an array instead of a string, you'll be able
    // to style any part individually
    {
      text: [
        'This paragraph is defined as an array of elements to make it possible to ',
        { text: 'restyle part of it and make it bigger ', fontSize: 15 },
        'than the rest.'
      ]
    }
  ]
};
```

#### Style dictionaries
It's also possible to define a dictionary of reusable styles:

```js
var docDefinition = {
  content: [
    { text: 'This is a header', style: 'header' },
    'No styling here, this is a standard paragraph',
    { text: 'Another text', style: 'anotherStyle' },
    { text: 'Multiple styles applied', style: [ 'header', 'anotherStyle' ] }
  ],

  styles: {
    header: {
      fontSize: 22,
      bold: true
    },
    anotherStyle: {
      italics: true,
      alignment: 'right'
    }
  }
};
```

To have a deeper understanding of styling in pdfmake, style inheritance and local-style-overrides check STYLES1, STYLES2 and STYLES3 examples in [playground](http://pdfmake.org/playground.html).

#### Default style

And is also possible define default style:

```js
var docDefinition = {
  content: [
    'Text styled by default style'
  ],

  defaultStyle: {
    fontSize: 15,
    bold: true
  }
};
```

#### Style properties

* `font: string`: name of the font
* `fontSize: number`: size of the font in pt
* `fontFeatures: `
* `lineHeight: int`: the line height (default: 1)
* `bold: boolean`: whether to use bold text (default: false)
* `italics: boolean`: whether to use italic text (default: false)
* `alignment: string`: ('left' or 'center' or 'right') the alignment of the text
* `color: string`: the color of the text (color name e.g., 'blue' or hexadecimal color e.g., '#ff5500')
* `background: string` the background color of the text
* `markerColor: string`: the color of the bullets in a buletted list
* `decoration: string`: the text decoration to applu ('underline' or 'lineThrough' or 'overline')
* `decorationStyle: string`: ('dashed' or 'dotted' or 'double' or 'wavy')
* `decorationColor: string`: the color of the text decoration, see color

##### Table-cell properties
* `fillColor: string`: the background color of a table cell
* `columnGap`
* `tableCellPadding`
* `cellBorder`
* `headerCellBorder`
* `oddRowCellBorder`
* `evenRowCellBorder`
* `tableBorder`
