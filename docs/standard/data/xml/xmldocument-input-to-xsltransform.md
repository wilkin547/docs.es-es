---
title: Entrada de XmlDocument en XslTransform
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 97115892-410a-4657-ab47-1e14dfba73f8
ms.openlocfilehash: 1c7aa1a9d5c02aaac5a78603bd2397f012d4640d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721938"
---
# <a name="xmldocument-input-to-xsltransform"></a><span data-ttu-id="9e1bf-102">Entrada de XmlDocument en XslTransform</span><span class="sxs-lookup"><span data-stu-id="9e1bf-102">XmlDocument Input to XslTransform</span></span>

<span data-ttu-id="9e1bf-103">La clase <xref:System.Xml.XmlDocument> permite modificar un documento XML.</span><span class="sxs-lookup"><span data-stu-id="9e1bf-103">The <xref:System.Xml.XmlDocument> class provides editing capabilities for an XML document.</span></span> <span data-ttu-id="9e1bf-104">Si el XML necesita editarse o modificarse antes de ser enviado al método <xref:System.Xml.Xsl.XslTransform.Transform%2A>, cargue el XML en <xref:System.Xml.XmlDocument>, edítelo y envíelo a <xref:System.Xml.Xsl.XslTransform>.</span><span class="sxs-lookup"><span data-stu-id="9e1bf-104">If the XML needs to be edited or modified before being sent to the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method, load the XML into an <xref:System.Xml.XmlDocument>, edit it, and send it in to the <xref:System.Xml.Xsl.XslTransform>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9e1bf-105">La clase <xref:System.Xml.Xsl.XslTransform> está obsoleta en .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="9e1bf-105">The <xref:System.Xml.Xsl.XslTransform> class is obsolete in the .NET Framework 2.0.</span></span> <span data-ttu-id="9e1bf-106">Puede llevar a cabo Extensible Stylesheet Language for Transformations (XSLT) mediante la clase <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="9e1bf-106">You can perform Extensible Stylesheet Language for Transformations (XSLT) transformations using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="9e1bf-107">Consulte [Uso de la clase XslCompiledTransform](using-the-xslcompiledtransform-class.md) y [Migración desde la clase XslTransform](migrating-from-the-xsltransform-class.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="9e1bf-107">See [Using the XslCompiledTransform Class](using-the-xslcompiledtransform-class.md) and [Migrating From the XslTransform Class](migrating-from-the-xsltransform-class.md) for more information.</span></span>  
  
 <span data-ttu-id="9e1bf-108"><xref:System.Xml.XmlDocument> implementa la interfaz <xref:System.Xml.XPath.IXPathNavigable>, de forma que el documento puede pasarse al método <xref:System.Xml.Xsl.XslTransform.Transform%2A> después de la edición.</span><span class="sxs-lookup"><span data-stu-id="9e1bf-108">The <xref:System.Xml.XmlDocument> implements the <xref:System.Xml.XPath.IXPathNavigable> interface, so the document can be passed to the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method after editing.</span></span>  
  
 <span data-ttu-id="9e1bf-109">Debido a la capacidad de edición de <xref:System.Xml.XmlDocument>, utilizar la clase <xref:System.Xml.XmlDocument> como entrada a una transformación es más lento que usar <xref:System.Xml.XPath.XPathDocument> para las transformaciones Extensible Stylesheet Language for Transformations (XSLT), ya que <xref:System.Xml.XPath.XPathDocument> se optimiza para las consultas XML Path Language (XPath) debido al almacenamiento interno.</span><span class="sxs-lookup"><span data-stu-id="9e1bf-109">Due to the editing capability of the <xref:System.Xml.XmlDocument>, using the <xref:System.Xml.XmlDocument> class as input to a transformation is slower than using an <xref:System.Xml.XPath.XPathDocument> for the Extensible Stylesheet Language for Transformations (XSLT) transformations, as the <xref:System.Xml.XPath.XPathDocument> is optimized for XML Path Language (XPath) queries due to the internal storage.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9e1bf-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9e1bf-110">Example</span></span>  

 <span data-ttu-id="9e1bf-111">El siguiente ejemplo de código muestra cómo <xref:System.Xml.XmlDocument> puede suministrarse a <xref:System.Xml.Xsl.XslTransform>, con el resultado enviado a <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="9e1bf-111">The following code example shows how an <xref:System.Xml.XmlDocument> can be supplied to the <xref:System.Xml.Xsl.XslTransform>, with the output sent to an <xref:System.Xml.XmlReader>.</span></span>  
  
```vb  
Dim doc as XmlDocument = new XmlDocument()  
doc.Load("books.xml")  
Dim trans As XslTransform = new XslTransform()  
trans.Load("book.xsl")  
Dim rdr As XmlReader = trans.Transform(doc, Nothing, Nothing)  
while (rdr.Read())  
end while  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
doc.Load("books.xml");  
XslTransform trans = new XslTransform();  
trans.Load("book.xsl");  
XmlReader rdr = trans.Transform(doc, null, null);  
while (rdr.Read()) {}  
```  
  
## <a name="see-also"></a><span data-ttu-id="9e1bf-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="9e1bf-112">See also</span></span>

- <xref:System.Xml.XmlDocument>
- [<span data-ttu-id="9e1bf-113">Transformaciones XSLT con la clase XslTransform</span><span class="sxs-lookup"><span data-stu-id="9e1bf-113">XSLT Transformations with the XslTransform Class</span></span>](xslt-transformations-with-the-xsltransform-class.md)
- [<span data-ttu-id="9e1bf-114">La clase XslTransform implementa el procesador XSLT</span><span class="sxs-lookup"><span data-stu-id="9e1bf-114">XslTransform Class Implements the XSLT Processor</span></span>](xsltransform-class-implements-the-xslt-processor.md)
- [<span data-ttu-id="9e1bf-115">XPathNavigator en transformaciones</span><span class="sxs-lookup"><span data-stu-id="9e1bf-115">XPathNavigator in Transformations</span></span>](xpathnavigator-in-transformations.md)
- [<span data-ttu-id="9e1bf-116">XPathNodeIterator en transformaciones</span><span class="sxs-lookup"><span data-stu-id="9e1bf-116">XPathNodeIterator in Transformations</span></span>](xpathnodeiterator-in-transformations.md)
- [<span data-ttu-id="9e1bf-117">Entrada XPathDocument en XslTransform</span><span class="sxs-lookup"><span data-stu-id="9e1bf-117">XPathDocument Input to XslTransform</span></span>](xpathdocument-input-to-xsltransform.md)
- [<span data-ttu-id="9e1bf-118">Entrada de XmlDataDocument en XslTransform</span><span class="sxs-lookup"><span data-stu-id="9e1bf-118">XmlDataDocument Input to XslTransform</span></span>](xmldatadocument-input-to-xsltransform.md)
