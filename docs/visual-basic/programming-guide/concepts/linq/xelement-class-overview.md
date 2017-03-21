---
title: "Información general de la clase XElement (Visual Basic) | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 52331fcd-6023-4d19-b423-7b24f2d86ded
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 4b46f3cb5e0d59105fbc31424a0408c3421d9cac
ms.lasthandoff: 03/13/2017

---
# <a name="xelement-class-overview-visual-basic"></a>Información general de la clase XElement (Visual Basic)
La <xref:System.Xml.Linq.XElement>clase es una de las clases fundamentales en [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].</xref:System.Xml.Linq.XElement> Representa a un elemento XML. Puede utilizar esta clase para crear elementos; cambiar el contenido del elemento; agregar, modificar o eliminar elementos secundarios; agregar atributos a un elemento; o serializar el contenido de un elemento en forma de texto. También puede operar con otras clases de <xref:System.Xml?displayProperty=fullName>, como <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>y <xref:System.Xml.Xsl.XslCompiledTransform>.</xref:System.Xml.Xsl.XslCompiledTransform> </xref:System.Xml.XmlWriter> </xref:System.Xml.XmlReader> </xref:System.Xml?displayProperty=fullName>  
  
## <a name="xelement-functionality"></a>Funcionalidad de XElement  
 Este tema describe la funcionalidad proporcionada por la <xref:System.Xml.Linq.XElement>clase.</xref:System.Xml.Linq.XElement>  
  
### <a name="constructing-xml-trees"></a>Construir árboles XML  
 Es posible construir árboles XML de diferentes formas, entre las que se incluyen las siguientes:  
  
-   Puede construir un árbol XML mediante código. Para obtener más información, consulte [crear árboles XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md).  
  
-   Puede analizar XML desde diversos orígenes, incluidos un <xref:System.IO.TextReader>, archivos de texto o una dirección Web (URL).</xref:System.IO.TextReader> Para obtener más información, consulte [analizar XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md).  
  
-   Puede utilizar un <xref:System.Xml.XmlReader>para rellenar el árbol.</xref:System.Xml.XmlReader> Para obtener más información, consulte <xref:System.Xml.Linq.XNode.ReadFrom%2A>.</xref:System.Xml.Linq.XNode.ReadFrom%2A>  
  
-   Si dispone de un módulo que pueda escribir contenidos en un <xref:System.Xml.XmlWriter>, puede usar el <xref:System.Xml.Linq.XContainer.CreateWriter%2A>para crear un sistema de escritura, pasar éste al módulo y, a continuación, utilizar el contenido que se escribe en el <xref:System.Xml.XmlWriter>para rellenar el árbol XML.</xref:System.Xml.XmlWriter> </xref:System.Xml.Linq.XContainer.CreateWriter%2A> </xref:System.Xml.XmlWriter>  
  
 No obstante, la forma más habitual de crear un árbol XML es la siguiente:  
  
```vb  
Dim contacts As XElement = _  
    <Contacts>  
        <Contact>  
            <Name>Patrick Hines</Name>  
            <Phone>206-555-0144</Phone>  
            <Address>  
                <Street1>123 Main St</Street1>  
                <City>Mercer Island</City>  
                <State>WA</State>  
                <Postal>68042</Postal>  
            </Address>  
        </Contact>  
    </Contacts>  
```  
  
 Otra técnica muy común para crear un árbol XML implica el uso de los resultados de una [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] consulta para rellenar un árbol XML, tal como se muestra en el ejemplo siguiente:  
  
```vb  
Dim srcTree As XElement = _  
    <Root>  
        <Element>1</Element>  
        <Element>2</Element>  
        <Element>3</Element>  
        <Element>4</Element>  
        <Element>5</Element>  
    </Root>  
Dim xmlTree As XElement = _  
    <Root>  
        <Child>1</Child>  
        <Child>2</Child>  
        <%= From el In srcTree.Elements() _  
            Where el.Value > 2 _  
            Select el %>  
    </Root>  
Console.WriteLine(xmlTree)  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```xml  
<Root>  
  <Child>1</Child>  
  <Child>2</Child>  
  <Element>3</Element>  
  <Element>4</Element>  
  <Element>5</Element>  
</Root>  
```  
  
### <a name="serializing-xml-trees"></a>Serializar árboles XML  
 Puede serializar un árbol XML en un <xref:System.IO.File>, un <xref:System.IO.TextWriter>, o un <xref:System.Xml.XmlWriter>.</xref:System.Xml.XmlWriter> </xref:System.IO.TextWriter> </xref:System.IO.File>  
  
 Para obtener más información, consulte [serializar árboles XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/serializing-xml-trees.md).  
  
### <a name="retrieving-xml-data-via-axis-methods"></a>Recuperar datos XML mediante los métodos de los ejes  
 Puede utilizar los métodos de los ejes para recuperar atributos, elementos secundarios, elementos descendientes y elementos antecesores. Las consultas [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] utilizan los métodos de los ejes y proporcionan numerosos mecanismos, flexibles y potentes, para recorrer y procesar árboles XML.  
  
 Para obtener más información, consulte [ejes LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md).  
  
### <a name="querying-xml-trees"></a>Consultar árboles XML  
 Puede escribir [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] consultas que extraigan datos de un árbol XML.  
  
 Para obtener más información, consulte [consultar árboles XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/querying-xml-trees.md).  
  
### <a name="modifying-xml-trees"></a>Modificar árboles XML  
 Puede modificar un elemento de diferentes maneras, incluyendo el cambiar su contenido o sus atributos. También puede eliminar un elemento dependiente de un elemento primario.  
  
 Para obtener más información, consulte [Modificar árboles XML (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md).  
  
## <a name="see-also"></a>Vea también  
 [LINQ to XML de información general de programación (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
