---
title: Entrada XPathDocument Input para XslTransform
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 7d1bbe8b-ed43-4e62-a5ba-d602d244f4ae
author: mairaw
ms.author: mairaw
ms.openlocfilehash: beefaffa0365efbb808fd15c1253027e4d5b09a1
ms.sourcegitcommit: a8d3504f0eae1a40bda2b06bd441ba01f1631ef0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2019
ms.locfileid: "67170918"
---
# <a name="xpathdocument-input-to-xsltransform"></a><span data-ttu-id="34199-102">Entrada XPathDocument Input para XslTransform</span><span class="sxs-lookup"><span data-stu-id="34199-102">XPathDocument Input to XslTransform</span></span>
<span data-ttu-id="34199-103"><xref:System.Xml.XPath.XPathDocument>es una caché de solo lectura que se utiliza para procesar documentos con <xref:System.Xml.Xsl.XslTransform>.</span><span class="sxs-lookup"><span data-stu-id="34199-103">The <xref:System.Xml.XPath.XPathDocument> is a read-only cache, for processing documents with <xref:System.Xml.Xsl.XslTransform>.</span></span> <span data-ttu-id="34199-104">Es estructuralmente similar al modelo de documento de objeto XML (DOM), pero está más optimizado para el procesamiento Extensible Stylesheet Language for Transformations (XSLT) y el modelo de datos XML Path Language (XPath) mediante las funciones de optimización XPath en <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="34199-104">It is structurally similar to the XML Document Object Model (DOM), but it is highly optimized for Extensible Stylesheet Language for Transformations (XSLT) processing and the XML Path Language (XPath) data model using the XPath optimization functions on the <xref:System.Xml.XPath.XPathNavigator>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="34199-105">La clase <xref:System.Xml.Xsl.XslTransform> está obsoleta en .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="34199-105">The <xref:System.Xml.Xsl.XslTransform> class is obsolete in the .NET Framework 2.0.</span></span> <span data-ttu-id="34199-106">Puede llevar a cabo Extensible Stylesheet Language for Transformations (XSLT) mediante la clase <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="34199-106">You can perform Extensible Stylesheet Language for Transformations (XSLT) transformations using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="34199-107">Consulte [Uso de la clase XslCompiledTransform](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) y [Migración desde la clase XslTransform](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="34199-107">See [Using the XslCompiledTransform Class](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) and [Migrating From the XslTransform Class](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) for more information.</span></span>  
  
 <span data-ttu-id="34199-108">En el código de ejemplo siguiente se crea un <xref:System.Xml.XPath.XPathDocument> como entrada para una transformación.</span><span class="sxs-lookup"><span data-stu-id="34199-108">The following code sample creates an <xref:System.Xml.XPath.XPathDocument> as input to a transform.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="34199-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="34199-109">See also</span></span>

- [<span data-ttu-id="34199-110">La clase XslTransform implementa el procesador XSLT</span><span class="sxs-lookup"><span data-stu-id="34199-110">XslTransform Class Implements the XSLT Processor</span></span>](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)
