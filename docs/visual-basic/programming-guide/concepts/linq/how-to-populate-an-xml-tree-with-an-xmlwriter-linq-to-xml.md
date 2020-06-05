---
title: Procedimiento para rellenar un árbol XML con un objeto XmlWriter (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: 5792a0eb-94ee-440d-b601-58cca8c0ee0b
ms.openlocfilehash: b3a36326175eeba8cd692a2c71f1f9b0fde24b5f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397978"
---
# <a name="how-to-populate-an-xml-tree-with-an-xmlwriter-linq-to-xml-visual-basic"></a><span data-ttu-id="cba2a-102">Cómo: rellenar un árbol XML con XmlWriter (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cba2a-102">How to: Populate an XML Tree with an XmlWriter (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="cba2a-103">Una forma de rellenar un árbol XML consiste en utilizar <xref:System.Xml.Linq.XContainer.CreateWriter%2A> para crear <xref:System.Xml.XmlWriter> y después escribir en <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="cba2a-103">One way to populate an XML tree is to use <xref:System.Xml.Linq.XContainer.CreateWriter%2A> to create an <xref:System.Xml.XmlWriter>, and then write to the <xref:System.Xml.XmlWriter>.</span></span> <span data-ttu-id="cba2a-104">El árbol XML se rellena con todos los nodos que se escriben en <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="cba2a-104">The XML tree is populated with all nodes that are written to the <xref:System.Xml.XmlWriter>.</span></span>  
  
 <span data-ttu-id="cba2a-105">Normalmente se usa este método cuando se usa [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] con otra clase que espera escribir en un <xref:System.Xml.XmlWriter>, como <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="cba2a-105">You would typically use this method when you use [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] with another class that expects to write to an <xref:System.Xml.XmlWriter>, such as <xref:System.Xml.Xsl.XslCompiledTransform>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cba2a-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cba2a-106">Example</span></span>  
 <span data-ttu-id="cba2a-107">Un uso posible para <xref:System.Xml.Linq.XContainer.CreateWriter%2A> es la invocación de una transformación XSLT.</span><span class="sxs-lookup"><span data-stu-id="cba2a-107">One possible use for <xref:System.Xml.Linq.XContainer.CreateWriter%2A> is when invoking an XSLT transformation.</span></span> <span data-ttu-id="cba2a-108">Este ejemplo crea un árbol XML, crea un <xref:System.Xml.XmlReader> del árbol XML, crea un nuevo documento y después crea un <xref:System.Xml.XmlWriter> para escribir en el nuevo documento.</span><span class="sxs-lookup"><span data-stu-id="cba2a-108">This example creates an XML tree, creates an <xref:System.Xml.XmlReader> from the XML tree, creates a new document, and then creates an <xref:System.Xml.XmlWriter> to write into the new document.</span></span> <span data-ttu-id="cba2a-109">A continuación invoca la transformación XSLT, pasando <xref:System.Xml.XmlReader> y <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="cba2a-109">It then invokes the XSLT transformation, passing in <xref:System.Xml.XmlReader> and <xref:System.Xml.XmlWriter>.</span></span> <span data-ttu-id="cba2a-110">Después de que se complete correctamente la transformación, se rellenará el nuevo árbol XML con los resultados de la transformación.</span><span class="sxs-lookup"><span data-stu-id="cba2a-110">After the transformation successfully completes, the new XML tree is populated with the results of the transformation.</span></span>  
  
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
  
 <span data-ttu-id="cba2a-111">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="cba2a-111">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <C1>Child1 data</C1>  
  <C2>Child2 data</C2>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="cba2a-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="cba2a-112">See also</span></span>

- <xref:System.Xml.Linq.XContainer.CreateWriter%2A>
- <xref:System.Xml.XmlWriter>
- <xref:System.Xml.Xsl.XslCompiledTransform>
- [<span data-ttu-id="cba2a-113">Crear árboles XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cba2a-113">Creating XML Trees (Visual Basic)</span></span>](creating-xml-trees.md)
