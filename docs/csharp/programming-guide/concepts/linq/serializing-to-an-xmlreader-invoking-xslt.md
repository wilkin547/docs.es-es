---
title: Serializar en un objeto XmlReader (invocando XSLT) (C#) | Microsoft Docs
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
ms.assetid: 4cc3ee03-ef4c-429b-a408-fedd10b728cd
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 96fed09349264710dc8f0591a0022939e9a4181a
ms.lasthandoff: 03/13/2017

---
# <a name="serializing-to-an-xmlreader-invoking-xslt-c"></a>Serializar en un objeto XmlReader (invocando XSLT) (C#)
Cuando use las funciones de interoperabilidad <xref:System.Xml?displayProperty=fullName> de [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], puede usar <xref:System.Xml.Linq.XNode.CreateReader%2A> para crear un objeto <xref:System.Xml.XmlReader>. El módulo que lee desde el objeto <xref:System.Xml.XmlReader> lee los nodos del árbol XML y los procesa.  
  
## <a name="invoking-an-xslt-transformation"></a>Invocar una transformación XSLT  
 Un uso posible para este método es la invocación de una transformación XSLT. Puede crear un árbol XML, crear un objeto <xref:System.Xml.XmlReader> desde el árbol XML, crear un documento y, después, crear un objeto <xref:System.Xml.XmlWriter> para escribir en el nuevo documento. Después, puede invocar la transformación XSLT y pasarla en <xref:System.Xml.XmlReader> y <xref:System.Xml.XmlWriter>. Después de que se complete correctamente la transformación, se rellenará el nuevo árbol XML con los resultados de la transformación.  
  
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
using (XmlWriter writer = newTree.CreateWriter()) {  
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
 [Serializar árboles XML (C#)](../../../../csharp/programming-guide/concepts/linq/serializing-xml-trees.md)
