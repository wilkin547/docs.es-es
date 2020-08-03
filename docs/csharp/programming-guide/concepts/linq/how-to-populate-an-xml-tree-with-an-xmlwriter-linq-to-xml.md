---
title: Procedimiento para rellenar un árbol XML con un objeto XmlWriter (LINQ to XML) (C#)
description: Aprenda a rellenar un árbol XML mediante CreateWriter para crear un objeto XmlWriter y, luego, escriba en él en LINQ to XML en C#.
ms.date: 07/20/2015
ms.assetid: cd5674d1-5c54-4efc-ba68-e23b2875295f
ms.openlocfilehash: 9639c5947583bccf4f8ba427fc8611e181ef1536
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2020
ms.locfileid: "87104796"
---
# <a name="how-to-populate-an-xml-tree-with-an-xmlwriter-linq-to-xml-c"></a><span data-ttu-id="99e78-103">Procedimiento para rellenar un árbol XML con un objeto XmlWriter (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="99e78-103">How to populate an XML tree with an XmlWriter (LINQ to XML) (C#)</span></span>
<span data-ttu-id="99e78-104">Una forma de rellenar un árbol XML consiste en utilizar <xref:System.Xml.Linq.XContainer.CreateWriter%2A> para crear <xref:System.Xml.XmlWriter> y después escribir en <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="99e78-104">One way to populate an XML tree is to use <xref:System.Xml.Linq.XContainer.CreateWriter%2A> to create an <xref:System.Xml.XmlWriter>, and then write to the <xref:System.Xml.XmlWriter>.</span></span> <span data-ttu-id="99e78-105">El árbol XML se rellena con todos los nodos que se escriben en <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="99e78-105">The XML tree is populated with all nodes that are written to the <xref:System.Xml.XmlWriter>.</span></span>  
  
 <span data-ttu-id="99e78-106">Normalmente se usa este método cuando se usa [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] con otra clase que espera escribir en un <xref:System.Xml.XmlWriter>, como <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="99e78-106">You would typically use this method when you use [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] with another class that expects to write to an <xref:System.Xml.XmlWriter>, such as <xref:System.Xml.Xsl.XslCompiledTransform>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="99e78-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="99e78-107">Example</span></span>  
 <span data-ttu-id="99e78-108">Un uso posible para <xref:System.Xml.Linq.XContainer.CreateWriter%2A> es la invocación de una transformación XSLT.</span><span class="sxs-lookup"><span data-stu-id="99e78-108">One possible use for <xref:System.Xml.Linq.XContainer.CreateWriter%2A> is when invoking an XSLT transformation.</span></span> <span data-ttu-id="99e78-109">Este ejemplo crea un árbol XML, crea un <xref:System.Xml.XmlReader> del árbol XML, crea un nuevo documento y después crea un <xref:System.Xml.XmlWriter> para escribir en el nuevo documento.</span><span class="sxs-lookup"><span data-stu-id="99e78-109">This example creates an XML tree, creates an <xref:System.Xml.XmlReader> from the XML tree, creates a new document, and then creates an <xref:System.Xml.XmlWriter> to write into the new document.</span></span> <span data-ttu-id="99e78-110">A continuación invoca la transformación XSLT, pasando <xref:System.Xml.XmlReader> y <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="99e78-110">It then invokes the XSLT transformation, passing in <xref:System.Xml.XmlReader> and <xref:System.Xml.XmlWriter>.</span></span> <span data-ttu-id="99e78-111">Después de que se complete correctamente la transformación, se rellenará el nuevo árbol XML con los resultados de la transformación.</span><span class="sxs-lookup"><span data-stu-id="99e78-111">After the transformation successfully completes, the new XML tree is populated with the results of the transformation.</span></span>  
  
```csharp  
string xslMarkup = @"<?xml version='1.0'?>  
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
</xsl:stylesheet>";  
  
XDocument xmlTree = new XDocument(  
    new XElement("Parent",  
        new XElement("Child1", "Child1 data"),  
        new XElement("Child2", "Child2 data")  
    )  
);  
  
XDocument newTree = new XDocument();  
using (XmlWriter writer = newTree.CreateWriter())  
{  
    // Load the style sheet.  
    XslCompiledTransform xslt = new XslCompiledTransform();  
    xslt.Load(XmlReader.Create(new StringReader(xslMarkup)));  
  
    // Execute the transformation and output the results to a writer.  
    xslt.Transform(xmlTree.CreateReader(), writer);  
}  
  
Console.WriteLine(newTree);  
```  
  
 <span data-ttu-id="99e78-112">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="99e78-112">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <C1>Child1 data</C1>  
  <C2>Child2 data</C2>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="99e78-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="99e78-113">See also</span></span>

- <xref:System.Xml.Linq.XContainer.CreateWriter%2A>
- <xref:System.Xml.XmlWriter>
- <xref:System.Xml.Xsl.XslCompiledTransform>
- [<span data-ttu-id="99e78-114">Crear árboles XML en C# </span><span class="sxs-lookup"><span data-stu-id="99e78-114">Creating XML Trees (C#)</span></span>](./linq-to-xml-overview.md)
