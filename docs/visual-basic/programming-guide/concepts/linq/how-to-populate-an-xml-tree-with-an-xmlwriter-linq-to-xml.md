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
# <a name="how-to-populate-an-xml-tree-with-an-xmlwriter-linq-to-xml-visual-basic"></a>Cómo: rellenar un árbol XML con XmlWriter (LINQ to XML) (Visual Basic)
Una forma de rellenar un árbol XML consiste en utilizar <xref:System.Xml.Linq.XContainer.CreateWriter%2A> para crear <xref:System.Xml.XmlWriter> y después escribir en <xref:System.Xml.XmlWriter>. El árbol XML se rellena con todos los nodos que se escriben en <xref:System.Xml.XmlWriter>.  
  
 Normalmente se usa este método cuando se usa [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] con otra clase que espera escribir en un <xref:System.Xml.XmlWriter>, como <xref:System.Xml.Xsl.XslCompiledTransform>.  
  
## <a name="example"></a>Ejemplo  
 Un uso posible para <xref:System.Xml.Linq.XContainer.CreateWriter%2A> es la invocación de una transformación XSLT. Este ejemplo crea un árbol XML, crea un <xref:System.Xml.XmlReader> del árbol XML, crea un nuevo documento y después crea un <xref:System.Xml.XmlWriter> para escribir en el nuevo documento. A continuación invoca la transformación XSLT, pasando <xref:System.Xml.XmlReader> y <xref:System.Xml.XmlWriter>. Después de que se complete correctamente la transformación, se rellenará el nuevo árbol XML con los resultados de la transformación.  
  
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
  
 Este ejemplo produce el siguiente resultado:  
  
```xml  
<Root>  
  <C1>Child1 data</C1>  
  <C2>Child2 data</C2>  
</Root>  
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.Xml.Linq.XContainer.CreateWriter%2A>
- <xref:System.Xml.XmlWriter>
- <xref:System.Xml.Xsl.XslCompiledTransform>
- [Crear árboles XML (Visual Basic)](creating-xml-trees.md)
