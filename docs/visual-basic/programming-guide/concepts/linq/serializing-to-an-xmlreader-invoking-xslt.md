---
title: Serializar en un objeto XmlReader (invocando XSLT)
ms.date: 07/20/2015
ms.assetid: 8b64f95a-e8f6-40f7-99f9-a8002c63af96
ms.openlocfilehash: e51bfc031ad6d5d0eb98718f5d547fb18eb45295
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84357379"
---
# <a name="serializing-to-an-xmlreader-invoking-xslt-visual-basic"></a><span data-ttu-id="18e88-102">Serializar en un objeto XmlReader (invocando XSLT) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="18e88-102">Serializing to an XmlReader (Invoking XSLT) (Visual Basic)</span></span>
<span data-ttu-id="18e88-103">Cuando use las funciones de interoperabilidad <xref:System.Xml?displayProperty=nameWithType> de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], puede usar <xref:System.Xml.Linq.XNode.CreateReader%2A> para crear un objeto <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="18e88-103">When you use the <xref:System.Xml?displayProperty=nameWithType> interoperability capabilities of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you can use <xref:System.Xml.Linq.XNode.CreateReader%2A> to create an <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="18e88-104">El módulo que lee desde el objeto <xref:System.Xml.XmlReader> lee los nodos desde el árbol XML y los procesa.</span><span class="sxs-lookup"><span data-stu-id="18e88-104">The module that reads from this <xref:System.Xml.XmlReader> reads the nodes from the XML tree and processes them accordingly.</span></span>  
  
## <a name="invoking-an-xslt-transformation"></a><span data-ttu-id="18e88-105">Invocar una transformación XSLT</span><span class="sxs-lookup"><span data-stu-id="18e88-105">Invoking an XSLT Transformation</span></span>  
 <span data-ttu-id="18e88-106">Un uso posible para este método es la invocación de una transformación XSLT.</span><span class="sxs-lookup"><span data-stu-id="18e88-106">One possible use for this method is when invoking an XSLT transformation.</span></span> <span data-ttu-id="18e88-107">Puede crear un árbol XML, crear un objeto <xref:System.Xml.XmlReader> desde el árbol XML, crear un nuevo documento y crear un objeto <xref:System.Xml.XmlWriter> que escribirá en el nuevo documento.</span><span class="sxs-lookup"><span data-stu-id="18e88-107">You can create an XML tree, create an <xref:System.Xml.XmlReader> from the XML tree, create a new document, and then create an <xref:System.Xml.XmlWriter> to write into the new document.</span></span> <span data-ttu-id="18e88-108">A continuación, puede invocar la transformación XSLT, pasando <xref:System.Xml.XmlReader> y <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="18e88-108">Then, you can invoke the XSLT transformation, passing in <xref:System.Xml.XmlReader> and <xref:System.Xml.XmlWriter>.</span></span> <span data-ttu-id="18e88-109">Después de que se complete correctamente la transformación, se rellenará el nuevo árbol XML con los resultados de la transformación.</span><span class="sxs-lookup"><span data-stu-id="18e88-109">After the transformation successfully completes, the new XML tree is populated with the results of the transformation.</span></span>  
  
```vb  
Dim xslMarkup As XDocument = _  
    <?xml version='1.0'?>  
    <xsl:stylesheet xmlns:xsl='http://www.w3.org/1999/XSL/Transform' version='1.0'>  
        <xsl:template match='/Parent'>  
            <Root>  
                <C1>  
                    <xsl:value-of select='Child1'/>  
                </C1>  
                <C2>  
                    <xsl:value-of select='Child2'/>  
                </C2>  
            </Root>  
        </xsl:template>  
    </xsl:stylesheet>  
  
Dim xmlTree As XDocument = _  
    <?xml version='1.0'?>  
    <Parent>  
        <Child1>Child1 data</Child1>  
        <Child2>Child2 data</Child2>  
    </Parent>  
  
Dim newTree As XDocument = New XDocument()  
Using writer As XmlWriter = newTree.CreateWriter()  
    ' Load the style sheet.  
    Dim xslt As XslCompiledTransform = New XslCompiledTransform()  
    xslt.Load(xslMarkup.CreateReader())  
  
    ' Execute the transformation and output the results to a writer.  
    xslt.Transform(xmlTree.CreateReader(), writer)  
End Using  
  
Console.WriteLine(newTree)  
```  
  
 <span data-ttu-id="18e88-110">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="18e88-110">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <C1>Child1 data</C1>  
  <C2>Child2 data</C2>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="18e88-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="18e88-111">See also</span></span>

- [<span data-ttu-id="18e88-112">Serializar árboles XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="18e88-112">Serializing XML Trees (Visual Basic)</span></span>](serializing-xml-trees.md)
