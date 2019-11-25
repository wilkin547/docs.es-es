---
title: Información general de LINQ to XML
ms.date: 07/20/2015
ms.assetid: 502661e0-bc5d-438d-94c2-7efb63bb6fbd
ms.openlocfilehash: ef3fca844dc98440eb4816110a5a78482cfa4f4e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346789"
---
# <a name="linq-to-xml-overview-visual-basic"></a>LINQ to XML Overview (Visual Basic)
XML se ha adoptado ampliamente como un modo de dar formato a datos en diversos contextos. Por ejemplo, puede encontrar XML en la web, en archivos de configuración, en archivos de Microsoft Office Word y en bases de datos.  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] es un método actualizado y rediseñado para la programación con XML. Proporciona capacidades de modificación de documento en memoria de Document Object Model (DOM), y es compatible con expresiones de consulta [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]. Aunque estas expresiones de consulta difieren sintácticamente de XPath, proporcionan una funcionalidad similar.  
  
## <a name="linq-to-xml-developers"></a>Desarrolladores de LINQ to XML  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] se dirige a diversos desarrolladores. Para el desarrollador medio que solo desea completar una tarea, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] simplifica el código XML al proporcionar una experiencia de consulta similar a SQL. Con un poco de estudio, los programadores pueden aprender a escribir consultas sucintas y eficaces en el lenguaje de programación que prefieran.  
  
 Los desarrolladores profesionales pueden usar [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] para aumentar considerablemente su productividad. Con [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], pueden escribir menos código, que a su vez resulte más expresivo, compacto y eficaz. Pueden usar expresiones de consulta de distintos dominios de datos simultáneamente.  
  
## <a name="what-is-linq-to-xml"></a>¿Qué es LINQ to XML?  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] es una interfaz de programación XML en memoria y habilitada para LINQ que permite trabajar con XML desde los lenguajes de programación de .NET Framework.  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] se parece a Document Object Model (DOM) en lo que respecta a la inserción del documento XML en la memoria. Puede consultar y modificar el documento; una vez modificado, puede guardarlo en un archivo o serializarlo y enviarlo a través de Internet. However, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] differs from DOM: It provides a new object model that is lighter weight and easier to work with, and that takes advantage of language features in Visual Basic.  
  
 La ventaja más importante de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] radica en su integración con [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]. Esta integración permite escribir consultas en el documento XML en memoria para recuperar colecciones de elementos y atributos. La capacidad de consulta de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] es comparable en cuanto a funcionalidad (aunque no cuanto a sintaxis) a XPath y XQuery. The integration of [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] in Visual Basic provides stronger typing, compile-time checking, and improved debugger support.  
  
 Otra ventaja de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] es la capacidad de usar los resultados de la consulta como parámetros en constructores de objetos <xref:System.Xml.Linq.XElement> y <xref:System.Xml.Linq.XAttribute>, que habilita un método eficaz para crear árboles XML. Este método, denominado *construcción funcional*, permite que los desarrolladores transformen fácilmente árboles XML de una forma a otra.  
  
 Por ejemplo, podría tener un pedido de compra XML común, como el que se describe en [Sample XML File: Typical Purchase Order (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md) (Archivo XML de ejemplo: pedido de compra común [LINQ to XML]). Mediante [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], podría ejecutar la siguiente consulta para obtener el valor del atributo de número de pieza relativo a cada elemento del pedido de compra:  
  
```vb  
Dim partNos = _  
    From item In purchaseOrder...<Item> _  
    Select item.@PartNumber  
```  
  
 A modo de ejemplo, imagine que necesita una lista, ordenada por números de pieza, de los elementos con un valor superior a 100 $. Para obtener esta información, podría ejecutar la siguiente consulta:  
  
```vb  
Dim partNos = _  
From item In purchaseOrder...<Item> _  
Where (item.<Quantity>.Value * _  
       item.<USPrice>.Value) > 100 _  
Order By item.<PartNumber>.Value _  
Select item  
```  
  
 Además de estas capacidades de [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] proporciona una interfaz de programación XML mejorada. Con [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], se puede:  
  
- Cargar XML a partir de archivos o secuencias.  
  
- Serializar XML a archivos o secuencias.  
  
- Crear árboles XML desde cero mediante la construcción funcional.  
  
- Realizar consultas de XML con ejes de tipo XPath.  
  
- Manipular el árbol XML en memoria con métodos como <xref:System.Xml.Linq.XContainer.Add%2A>, <xref:System.Xml.Linq.XNode.Remove%2A>, <xref:System.Xml.Linq.XNode.ReplaceWith%2A> y <xref:System.Xml.Linq.XElement.SetValue%2A>.  
  
- Validar árboles XML mediante XSD.  
  
- Usar una combinación de estas características para transformar las formas de los árboles XML.  
  
## <a name="creating-xml-trees"></a>Crear árboles XML  
 Una de la ventajas más significativas de la programación con [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] es la facilidad con que se pueden crear árboles XML. For example, to create a small XML tree, you can write  code as follows:  
  
```vb  
Dim contacts = _  
<Contacts>  
    <Contact>  
        <Name>Patrick Hines</Name>  
        <Phone Type="Home">206-555-0144</Phone>  
        <Phone Type="Work">425-555-0145</Phone>  
        <Address>  
            <Street1>123 Main St</Street1>  
            <City>Mercer Island</City>  
            <State>WA</State>  
            <Postal>68042</Postal>  
        </Address>  
    </Contact>  
</Contacts>  
```  
  
 The Visual Basic compiler translates XML literals into [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] method calls.  
  
 For more information, see [Creating XML Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Xml.Linq>
- [Introducción (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/getting-started-linq-to-xml.md)
- [Información general sobre LINQ to XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)
- [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)
