---
title: "Pretty-printing XML with JS"
date: 2021-10-24T02:50:28+03:00
description: "Prettify XML strings with JS and XSLT transformations"
tags: ["Javscript", "XML", "XLST"]
author: "kzmkrksc"
showToc: true
TocOpen: false
draft: false
hidemeta: false
comments: false
disableHLJS: true # to disable highlightjs
disableShare: false
searchHidden: false
cover:
    image: "" # image path/url
    alt: "" # alt text
    caption: "" # display caption under cover
    relative: false # when using page bundles set this to true
    hidden: true # only hide on current single page
---

# Pretty-printing XML with JS

With Javascript it is possible to prettify/beutify XML strings. Only thing is that XSLT should be properly formed and XML strings should be properly written.


XSLT identity transform code is given below. 

```xml
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform">
  <xsl:output omit-xml-declaration="yes" indent="yes"/>
  <!-- Identity Transform -->
    <xsl:template match="node()|@*">
      <xsl:copy>
        <xsl:apply-templates select="node()|@*"/>
      </xsl:copy>
    </xsl:template>
  <!-- apply normalize-space to text nodes-->
    <xsl:template match="text()">               
        <xsl:value-of select="normalize-space(.)"/>    
  </xsl:template>
</xsl:stylesheet>
```

Add XSLT transformation code inside a ```<script></script>``` tag and then read it inside JS. The XML string should be processed with this XSLT processor.

JS Code:
```js
var prettifyXml = function (source) {
  let xmlDoc = new DOMParser().parseFromString(source, "application/xml");
  let err = xmlDoc.documentElement.getElementsByTagName("parsererror").length;
  if (!err) {
    let xsltText = document.getElementById("xslt").innerText;
    let xsltDoc = new DOMParser().parseFromString(xsltText, "text/xml");
    let xsltProcessor = new XSLTProcessor();
    xsltProcessor.importStylesheet(xsltDoc);
    let resultDoc = xsltProcessor.transformToDocument(xmlDoc);
    let resultXml = new XMLSerializer().serializeToString(resultDoc);
    return resultXml;
  } else {
    return false;
  }
};
```

[Live Codepen Demo](https://codepen.io/kzmkrksc/pen/YzyBBON?editors=1111)