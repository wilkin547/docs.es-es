---
title: "Cómo: Rellenar un árbol XML con XmlWriter (LINQ to XML) (C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: cd5674d1-5c54-4efc-ba68-e23b2875295f
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 9d74e6bd3d8454f5ed37fa8d190beb0c44399fa7
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-populate-an-xml-tree-with-an-xmlwriter-linq-to-xml-c"></a>Cómo: Rellenar un árbol XML con XmlWriter (LINQ to XML) (C#)
Una forma de rellenar un árbol XML consiste en utilizar <xref:System.Xml.Linq.XContainer.CreateWriter%2A> para crear <xref:System.Xml.XmlWriter> y después escribir en <xref:System.Xml.XmlWriter>. El árbol XML se rellena con todos los nodos que se escriben en <xref:System.Xml.XmlWriter>.  
  
 Normalmente se usa este método cuando se usa [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] con otra clase que espera escribir en un <xref:System.Xml.XmlWriter>, como <xref:System.Xml.Xsl.XslCompiledTransform>.  
  
## <a name="example"></a>Ejemplo  
 Un uso posible para <xref:System.Xml.Linq.XContainer.CreateWriter%2A> es la invocación de una transformación XSLT. Este ejemplo crea un árbol XML, crea un <xref:System.Xml.XmlReader> del árbol XML, crea un nuevo documento y después crea un <xref:System.Xml.XmlWriter> para escribir en el nuevo documento. A continuación invoca la transformación XSLT, pasando <xref:System.Xml.XmlReader> y <xref:System.Xml.XmlWriter>. Después de que se complete correctamente la transformación, se rellenará el nuevo árbol XML con los resultados de la transformación.  
  
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
  
 Este ejemplo produce el siguiente resultado:  
  
```xml  
<Root>  
  <C1>Child1 data</C1>  
  <C2>Child2 data</C2>  
</Root>  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Xml.Linq.XContainer.CreateWriter%2A>   
 <xref:System.Xml.XmlWriter>   
 <xref:System.Xml.Xsl.XslCompiledTransform>   
 [Creating XML Trees (C#)](../../../../csharp/programming-guide/concepts/linq/creating-xml-trees.md) (Crear árboles XML (C#))

