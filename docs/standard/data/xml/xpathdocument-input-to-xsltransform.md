---
title: Entrada XPathDocument Input para XslTransform
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7d1bbe8b-ed43-4e62-a5ba-d602d244f4ae
ms.openlocfilehash: 29bb345c2654baec8fbd2adce3788a4b4f2d582d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720872"
---
# <a name="xpathdocument-input-to-xsltransform"></a>Entrada XPathDocument Input para XslTransform

<xref:System.Xml.XPath.XPathDocument>es una caché de solo lectura que se utiliza para procesar documentos con <xref:System.Xml.Xsl.XslTransform>. Es estructuralmente similar al modelo de documento de objeto XML (DOM), pero está más optimizado para el procesamiento Extensible Stylesheet Language for Transformations (XSLT) y el modelo de datos XML Path Language (XPath) mediante las funciones de optimización XPath en <xref:System.Xml.XPath.XPathNavigator>.  
  
> [!NOTE]
> La clase <xref:System.Xml.Xsl.XslTransform> está obsoleta en .NET Framework 2.0. Puede llevar a cabo Extensible Stylesheet Language for Transformations (XSLT) mediante la clase <xref:System.Xml.Xsl.XslCompiledTransform>. Consulte [Uso de la clase XslCompiledTransform](using-the-xslcompiledtransform-class.md) y [Migración desde la clase XslTransform](migrating-from-the-xsltransform-class.md) para obtener más información.  
  
 En el código de ejemplo siguiente se crea un <xref:System.Xml.XPath.XPathDocument> como entrada para una transformación.  
  
```vb  
Dim xslt as XslTransform = new XslTransform()  
Xslt.Load(someStylesheet)  
Dim doc as XPathDocument = New XPathDocument("books.xml")  
Dim fs as StringWriter = new StringWriter()  
Xslt.Transform(doc, Nothing, fs, Nothing);  
```  
  
```csharp  
XslTransform xslt = new XslTransform();  
Xslt.Load(someStylesheet);  
XPathDocument doc = XPathDocument("books.xml");  
StringWriter fs = new StringWriter();  
Xslt.Transform(doc, null, fs, null);  
```  
  
## <a name="see-also"></a>Vea también

- [La clase XslTransform implementa el procesador XSLT](xsltransform-class-implements-the-xslt-processor.md)
