---
title: "Comparación de XPath y LINQ to XML1 | Documentos de Microsoft"
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
ms.assetid: c3fd07c1-6761-4e4b-8eb1-ddd780ed8d44
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: e9601c51468fdf5adab8e521f8f89ee7f2e12869
ms.lasthandoff: 03/13/2017


---
# <a name="comparison-of-xpath-and-linq-to-xml"></a>Comparación de XPath y LINQ to XML
XPath y [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] ofrecen una funcionalidad similar. Ambos se pueden usar para consultar un árbol XML, devolviendo resultados como recopilación de elementos, recopilación de nodos o el valor de un elemento o atributo. Sin embargo, también hay algunas diferencias.  
  
## <a name="differences-between-xpath-and-linq-to-xml"></a>Diferencias entre XPath y LINQ to XML  
 XPath no permite la proyección de nuevos tipos. Solo puede devolver recopilaciones de nodos del árbol, mientras que [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] puede ejecutar una consulta y proyectar un gráfico de objetos o un árbol XML en una nueva forma. Las consultas de [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] abarcan una funcionalidad mucho mayor y son mucho más eficaces que las expresiones XPath.  
  
 Las expresiones XPath existen de forma aislada en una cadena. El compilador de Visual Basic no puede ayudar a analizar la expresión XPath en tiempo de compilación. Por el contrario, [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] consultas se analiza y compila theVisual Basic compiler. El compilador puede detectar muchos errores de consulta.  
  
 Los resultados de XPath no están fuertemente tipados. En varias circunstancias, el resultado de evaluar una expresión XPath es un objeto, y depende del desarrollador determinar el tipo adecuado y convertir el resultado según sea necesario. Por el contrario, las proyecciones de una consulta de [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] están fuertemente tipadas.  
  
## <a name="result-ordering"></a>Ordenación de resultados  
 La recomendación XPath 1.0 indica que una recopilación que es el resultado de evaluar una expresión XPath está desordenada.  
  
 No obstante, cuando se recorre en iteración una recopilación devuelta por un método de eje XPath de [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], los nodos de la recopilación se devuelven en el orden del documento. Esto es aplicable incluso cuando se tiene acceso a los ejes XPath donde se expresan los predicados en términos de orden de documento inverso, como `preceding` y `preceding-sibling`.  
  
 Por el contrario, la mayoría de los [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] ejes devuelven colecciones en orden del documento, pero dos de ellos, <xref:System.Xml.Linq.XNode.Ancestors%2A>y <xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A>, devuelven recopilaciones en el orden del documento inverso.</xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A> </xref:System.Xml.Linq.XNode.Ancestors%2A> En la siguiente tabla se enumeran los ejes y se indica el orden de la recopilación para cada uno:  
  
|Eje LINQ to XML|Ordenación|  
|----------------------|--------------|  
|XContainer.DescendantNodes|Orden del documento|  
|XContainer.Descendants|Orden del documento|  
|XContainer.Elements|Orden del documento|  
|XContainer.Nodes|Orden del documento|  
|XContainer.NodesAfterSelf|Orden del documento|  
|XContainer.NodesBeforeSelf|Orden del documento|  
|XElement.AncestorsAndSelf|Orden del documento inverso|  
|XElement.Attributes|Orden del documento|  
|XElement.DescendantNodesAndSelf|Orden del documento|  
|XElement.DescendantsAndSelf|Orden del documento|  
|XNode.Ancestors|Orden del documento inverso|  
|XNode.ElementsAfterSelf|Orden del documento|  
|XNode.ElementsBeforeSelf|Orden del documento|  
|XNode.NodesAfterSelf|Orden del documento|  
|XNode.NodesBeforeSelf|Orden del documento|  
  
## <a name="positional-predicates"></a>Predicados de posición  
 En una expresión XPath, los predicados de posición se expresan en términos de orden del documento para muchos ejes, pero se expresan en el orden del documento inverso para los ejes inversos, que son `preceding`, `preceding-sibling`, `ancestor` y `ancestor-or-self`. Por ejemplo, la expresión de XPath `preceding-sibling::*[1]` devuelve el elemento del mismo nivel inmediatamente anterior. Esto es aplicable aunque el conjunto de resultados finales se presenta en el orden del documento.  
  
 Por el contrario, todos los predicados de posición de LINQ to XML siempre se expresan en términos del orden del eje. Por ejemplo, `anElement.ElementsBeforeSelf().ToList()[0]` devuelve el primer elemento secundario del elemento primario del elemento consultado, no el elemento del mismo nivel inmediatamente anterior. Otro ejemplo: `anElement.Ancestors().ToList()[0]` devuelve el elemento primario.  
  
 Tenga en cuenta que el enfoque anterior materializa toda la recopilación. Ésta no es la forma más eficiente de escribir esa consulta. Se ha escrito de esa forma para demostrar el comportamiento de los predicados de posición. Una forma más adecuada de escribir la misma consulta es usar el <xref:System.Linq.Enumerable.First%2A>método como sigue: `anElement.ElementsBeforeSelf().First()`.</xref:System.Linq.Enumerable.First%2A>  
  
 Si deseara buscar el elemento inmediatamente precedente de [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] escribiría la siguiente expresión:  
  
 `ElementsBeforeSelf().Last()`  
  
## <a name="performance-differences"></a>Diferencias de rendimiento  
 Consultas XPath que usan la funcionalidad en XPath [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] no llevará a cabo, así como [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] consultas.  
  
## <a name="comparison-of-composition"></a>Comparación de la composición  
 La composición de una consulta de [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] es en cierta medida paralela a la composición de una expresión XPath, aunque tiene una sintaxis muy diferente.  
  
 Por ejemplo, si tiene un elemento de una variable con el nombre `customers` y desea buscar un elemento inferior con el nombre `CompanyName` bajo todos los elementos secundarios con el nombre `Customer`, debe escribir una expresión XPath de la siguiente manera:  
  
```vb  
customers.XPathSelectElements("./Customer/CompanyName")  
```  
  
 La consulta de [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] equivalente es:  
  
```vb  
customers.Element("Customer").Elements("CompanyName")  
```  
  
 Existen elementos similares para cada uno de los ejes XPath.  
  
|Eje XPath|Eje LINQ to XML|  
|----------------|----------------------|  
|secundario (el eje predeterminado)|<xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName></xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName>|  
|Primario (..)|<xref:System.Xml.Linq.XObject.Parent%2A?displayProperty=fullName></xref:System.Xml.Linq.XObject.Parent%2A?displayProperty=fullName>|  
|eje de atributo (@)|<xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=fullName><br /><br /> o<br /><br /> <xref:System.Xml.Linq.XElement.Attributes%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Attributes%2A?displayProperty=fullName>|  
|eje antecesor|<xref:System.Xml.Linq.XNode.Ancestors%2A?displayProperty=fullName></xref:System.Xml.Linq.XNode.Ancestors%2A?displayProperty=fullName>|  
|eje antecesor o propio|<xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A?displayProperty=fullName>|  
|eje descendiente (//)|<xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=fullName></xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=fullName><br /><br /> o<br /><br /> <xref:System.Xml.Linq.XContainer.DescendantNodes%2A?displayProperty=fullName></xref:System.Xml.Linq.XContainer.DescendantNodes%2A?displayProperty=fullName>|  
|descendiente o propio|<xref:System.Xml.Linq.XElement.DescendantsAndSelf%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.DescendantsAndSelf%2A?displayProperty=fullName><br /><br /> o<br /><br /> <xref:System.Xml.Linq.XElement.DescendantNodesAndSelf%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.DescendantNodesAndSelf%2A?displayProperty=fullName>|  
|siguientes-relacionados|<xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A?displayProperty=fullName></xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A?displayProperty=fullName><br /><br /> o<br /><br /> <xref:System.Xml.Linq.XNode.NodesAfterSelf%2A?displayProperty=fullName></xref:System.Xml.Linq.XNode.NodesAfterSelf%2A?displayProperty=fullName>|  
|precedentes-relacionados|<xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=fullName></xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=fullName><br /><br /> o<br /><br /> <xref:System.Xml.Linq.XNode.NodesBeforeSelf%2A?displayProperty=fullName></xref:System.Xml.Linq.XNode.NodesBeforeSelf%2A?displayProperty=fullName>|  
|siguientes|No hay equivalente directo.|  
|precedentes|No hay equivalente directo.|  
  
## <a name="see-also"></a>Vea también  
 [LINQ to XML para usuarios de XPath (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
