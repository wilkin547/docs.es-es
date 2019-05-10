---
title: Información general de la clase XElement (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 52331fcd-6023-4d19-b423-7b24f2d86ded
ms.openlocfilehash: d5ae3feae632c3bc3ce927a6d376e9ec4911e9fd
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64647397"
---
# <a name="xelement-class-overview-visual-basic"></a>Información general de la clase XElement (Visual Basic)
La clase <xref:System.Xml.Linq.XElement> es una de las clases fundamentales de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]. Representa a un elemento XML. Puede utilizar esta clase para crear elementos; cambiar el contenido del elemento; agregar, modificar o eliminar elementos secundarios; agregar atributos a un elemento; o serializar el contenido de un elemento en forma de texto. También puede operar con otras clases de <xref:System.Xml?displayProperty=nameWithType>, como son <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter> y <xref:System.Xml.Xsl.XslCompiledTransform>.  
  
## <a name="xelement-functionality"></a>Funcionalidad de XElement  
 Este tema describe la funcionalidad que ofrece la clase <xref:System.Xml.Linq.XElement>.  
  
### <a name="constructing-xml-trees"></a>Construir árboles XML  
 Es posible construir árboles XML de diferentes formas, entre las que se incluyen las siguientes:  
  
- Puede construir un árbol XML mediante código. Para obtener más información, consulte [crear árboles XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md).  
  
- Puede analizar XML a partir de diferentes orígenes, incluyendo un <xref:System.IO.TextReader>, archivos de texto o direcciones web (URL). Para obtener más información, consulte [Parsing XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md).  
  
- También puede utilizar un <xref:System.Xml.XmlReader> para rellenar el árbol. Para obtener más información, consulta <xref:System.Xml.Linq.XNode.ReadFrom%2A>.  
  
- Si dispone de un módulo que pueda escribir contenidos en un <xref:System.Xml.XmlWriter>, puede utilizar el método <xref:System.Xml.Linq.XContainer.CreateWriter%2A> para crear un sistema de escritura, para pasar éste al módulo y para utilizar después el contenido que se haya escrito en <xref:System.Xml.XmlWriter> para rellenar el árbol XML.  
  
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
  
 Otra técnica usada con frecuencia para crear un árbol XML implica el uso de los resultados de una consulta [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] para rellenar el árbol XML, tal y como se muestra en el ejemplo siguiente:  
  
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
 Puede serializar un árbol XML en un <xref:System.IO.File>, un <xref:System.IO.TextWriter> o en un <xref:System.Xml.XmlWriter>.  
  
 Para obtener más información, consulte [serializar árboles XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/serializing-xml-trees.md).  
  
### <a name="retrieving-xml-data-via-axis-methods"></a>Recuperar datos XML mediante los métodos de los ejes  
 Puede utilizar los métodos de los ejes para recuperar atributos, elementos secundarios, elementos descendientes y elementos antecesores. Las consultas [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] utilizan los métodos de los ejes y proporcionan numerosos mecanismos, flexibles y potentes, para recorrer y procesar árboles XML.  
  
 Para obtener más información, consulte [ejes LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md).  
  
### <a name="querying-xml-trees"></a>Consultar árboles XML  
 Puede escribir consultas [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] que extraigan datos de un árbol XML.  
  
 Para obtener más información, consulte [consultar árboles XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/querying-xml-trees.md).  
  
### <a name="modifying-xml-trees"></a>Modificar árboles XML  
 Puede modificar un elemento de diferentes maneras, incluyendo el cambiar su contenido o sus atributos. También puede eliminar un elemento dependiente de un elemento primario.  
  
 Para obtener más información, consulte [Modificar árboles XML (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md).  
  
## <a name="see-also"></a>Vea también

- [LINQ to XML de información general de programación (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
