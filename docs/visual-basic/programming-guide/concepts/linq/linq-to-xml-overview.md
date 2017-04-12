---
title: LINQ to XML Overview (Visual Basic) | Documentos de Microsoft
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
ms.assetid: 502661e0-bc5d-438d-94c2-7efb63bb6fbd
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 05d756bc5cd7655a5220c3564d120f90a59ce901
ms.lasthandoff: 03/13/2017

---
# <a name="linq-to-xml-overview-visual-basic"></a>LINQ to XML Overview (Visual Basic)
XML se ha adoptado ampliamente como un modo de dar formato a datos en diversos contextos. Por ejemplo, puede encontrar XML en la web, en archivos de configuración, en archivos de Microsoft Office Word y en bases de datos.  
  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] es un método actualizado y rediseñado para la programación con XML. Proporciona capacidades de modificación de documento en memoria de Document Object Model (DOM), y es compatible con expresiones de consulta [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]. Aunque estas expresiones de consulta difieren sintácticamente de XPath, proporcionan una funcionalidad similar.  
  
## <a name="linq-to-xml-developers"></a>Desarrolladores de LINQ to XML  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] se dirige a diversos desarrolladores. Para el desarrollador medio que solo desea completar una tarea, [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] simplifica el código XML al proporcionar una experiencia de consulta similar a SQL. Con un poco de estudio, los programadores pueden aprender a escribir consultas sucintas y eficaces en el lenguaje de programación que prefieran.  
  
 Los desarrolladores profesionales pueden usar [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] para aumentar considerablemente su productividad. Con [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], pueden escribir menos código, que a su vez resulte más expresivo, compacto y eficaz. Pueden usar expresiones de consulta de distintos dominios de datos simultáneamente.  
  
## <a name="what-is-linq-to-xml"></a>¿Qué es LINQ to XML?  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] es una interfaz de programación XML en memoria y habilitada para LINQ que permite trabajar con XML desde los lenguajes de programación de [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)].  
  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]es como el modelo de objetos de documento (DOM) que pone el documento XML en memoria. Puede consultar y modificar el documento; una vez modificado, puede guardarlo en un archivo o serializarlo y enviarlo a través de Internet. Sin embargo, [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] difiere de DOM: proporciona un nuevo modelo de objeto ligero y fáciles de usar, y que aprovecha las características de lenguaje en Visual Basic.  
  
 La ventaja más importante de [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] radica en su integración con [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)]. Esta integración permite escribir consultas en el documento XML en memoria para recuperar colecciones de elementos y atributos. La capacidad de consulta de [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] es comparable en cuanto a funcionalidad (aunque no cuanto a sintaxis) a XPath y XQuery. La integración de [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] en Visual Basic, proporciona más fuerte escritura, tiempo de compilación la comprobación y compatibilidad del depurador mejorada.  
  
 Otra ventaja de [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] es la capacidad de usar los resultados de la consulta como parámetros en <xref:System.Xml.Linq.XElement>y <xref:System.Xml.Linq.XAttribute>constructores de objetos habilita un método eficaz para crear árboles XML.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement> Este método, denominado *construcción funcional*, permite a los desarrolladores transformen fácilmente árboles XML de una forma a otra.  
  
 Por ejemplo, podría tener un archivo XML típico de pedido de compra, como se describe en [archivo XML de ejemplo: pedido de compra típico (LINQ to XML)](http://msdn.microsoft.com/library/0606c09f-6e43-4f8d-95c8-e8e2e08d2348). Mediante [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], podría ejecutar la siguiente consulta para obtener el valor del atributo de número de pieza relativo a cada elemento del pedido de compra:  
  
```vb  
Dim partNos = _  
    From item In purchaseOrder...<Item> _  
    Select item.@PartNumber  
```  
  
 A modo de ejemplo, imagine que necesita una lista, ordenada por números de pieza, de los elementos con un valor superior a&100; $. Para obtener esta información, podría ejecutar la siguiente consulta:  
  
```vb  
Dim partNos = _  
From item In purchaseOrder...<Item> _  
Where (item.<Quantity>.Value * _  
       item.<USPrice>.Value) > 100 _  
Order By item.<PartNumber>.Value _  
Select item  
```  
  
 Además de estas [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] capacidades, [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] proporciona una interfaz de programación XML mejorada. Con [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], se puede:  
  
-   Cargar XML a partir de archivos o secuencias.  
  
-   Serializar XML a archivos o secuencias.  
  
-   Crear árboles XML desde cero mediante la construcción funcional.  
  
-   Realizar consultas de XML con ejes de tipo XPath.  
  
-   Manipular el árbol XML en memoria con métodos como <xref:System.Xml.Linq.XContainer.Add%2A>, <xref:System.Xml.Linq.XNode.Remove%2A>, <xref:System.Xml.Linq.XNode.ReplaceWith%2A>y <xref:System.Xml.Linq.XElement.SetValue%2A>.</xref:System.Xml.Linq.XElement.SetValue%2A> </xref:System.Xml.Linq.XNode.ReplaceWith%2A> </xref:System.Xml.Linq.XNode.Remove%2A> </xref:System.Xml.Linq.XContainer.Add%2A>  
  
-   Validar árboles XML mediante XSD.  
  
-   Usar una combinación de estas características para transformar las formas de los árboles XML.  
  
## <a name="creating-xml-trees"></a>Crear árboles XML  
 Una de la ventajas más significativas de la programación con [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] es la facilidad con que se pueden crear árboles XML. Por ejemplo, para crear un árbol XML pequeño, puede escribir código como sigue:  
  
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
  
 El [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compilador traduce los literales XML en [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] llamadas al método.  
  
 Para obtener más información, consulte [crear árboles XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Xml.Linq>   
 [Introducción (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/getting-started-linq-to-xml.md)   
 [Información general de LINQ to XML en Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)   
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)
