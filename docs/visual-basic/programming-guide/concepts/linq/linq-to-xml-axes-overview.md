---
title: "Introducción (Visual Basic) de ejes de LINQ to XML | Documentos de Microsoft"
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
ms.assetid: 9161f151-cfa8-4408-94ba-08a9ba3a486d
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: b127aa6b443e865c76831d886f110550ec785e9b
ms.lasthandoff: 03/13/2017


---
# <a name="linq-to-xml-axes-overview-visual-basic"></a>LINQ to XML ejes Overview (Visual Basic)
Tras crear un árbol XML o haber cargado un documento XML en un árbol XML, puede realizar consultas sobre él para encontrar elementos y atributos, así como para recuperar sus valores. Recuperar colecciones a través de la *métodos de eje*, también denominados *ejes*. Algunos de los ejes son métodos de la <xref:System.Xml.Linq.XElement>y <xref:System.Xml.Linq.XDocument>clases que devuelven <xref:System.Collections.Generic.IEnumerable%601>colecciones.</xref:System.Collections.Generic.IEnumerable%601> </xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> Algunos de los ejes son métodos de extensión en la <xref:System.Xml.Linq.Extensions>clase.</xref:System.Xml.Linq.Extensions> Los ejes que se han implementado como métodos de extensión trabajan colecciones y devuelven colecciones.  
  
 Como se describe en [general sobre la clase XElement](http://msdn.microsoft.com/library/d35180fe-7016-4895-9bfc-ba1e3f7875ec), un <xref:System.Xml.Linq.XElement>objeto representa un nodo de elemento único.</xref:System.Xml.Linq.XElement> El contenido de un elemento puede ser complejo (a veces conocido como contenido estructurado) o puede ser un elemento simple. Un elemento simple puede estar vacío o contener un valor. Si el nodo incluye contenido estructurado, puede utilizar diferentes métodos del eje para recuperar enumeraciones con los elementos descendientes. Los métodos de ejes que se utilizan normalmente son <xref:System.Xml.Linq.XContainer.Elements%2A>y <xref:System.Xml.Linq.XContainer.Descendants%2A>.</xref:System.Xml.Linq.XContainer.Descendants%2A> </xref:System.Xml.Linq.XContainer.Elements%2A>  
  
 Además de los métodos de ejes que devuelven colecciones, existen dos métodos más que normalmente se utilizan en [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] consultas. El <xref:System.Xml.Linq.XContainer.Element%2A>método devuelve un único <xref:System.Xml.Linq.XElement>.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XContainer.Element%2A> El <xref:System.Xml.Linq.XElement.Attribute%2A>método devuelve un único <xref:System.Xml.Linq.XAttribute>.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement.Attribute%2A>  
  
 Por diversas razones, las consultas de [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] ofrecen el mecanismo más potente para examinar árboles, extraer datos de ellos y para transformarlos. [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]las consultas funcionan en objetos que implementan <xref:System.Collections.Generic.IEnumerable%601>y el [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] ejes retorno <xref:System.Collections.Generic.IEnumerable%601>de <xref:System.Xml.Linq.XElement>colecciones, y <xref:System.Collections.Generic.IEnumerable%601>de <xref:System.Xml.Linq.XAttribute>colecciones.</xref:System.Xml.Linq.XAttribute> </xref:System.Collections.Generic.IEnumerable%601> </xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601> </xref:System.Collections.Generic.IEnumerable%601> Para poder realizar las consultas, necesitará estas colecciones.  
  
 A parte de los métodos de ejes que permiten recuperar colecciones de elementos y atributos, existen métodos de ejes que le permiten iterar por un árbol con gran detalle. Por ejemplo, en vez de tratar directamente con los elementos y los atributos, podría trabajar con los nodos del árbol. Los nodos tienen un nivel de granularidad mayor que los elementos y atributos. Si trabaja con nodos, podrá examinar comentarios XML, nodos de texto, instrucciones de procesamiento, etc. Esta funcionalidad resultaría interesante, por ejemplo, para una persona que estuviese escribiendo un procesador de textos y quisiera guardar los documentos en formato XML. No obstante, la mayoría de programadores en XML se centran más en los elementos, los atributos y sus valores.  
  
## <a name="methods-for-retrieving-a-collection-of-elements"></a>Métodos para recuperar una colección de elementos  
 El siguiente es un resumen de los métodos de la <xref:System.Xml.Linq.XElement>clase (o sus clases base) que se llama en un <xref:System.Xml.Linq.XElement>para devolver una colección de elementos.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XElement>  
  
|Método|Descripción|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XNode.Ancestors%2A?displayProperty=fullName></xref:System.Xml.Linq.XNode.Ancestors%2A?displayProperty=fullName>|Devuelve un <xref:System.Collections.Generic.IEnumerable%601>de <xref:System.Xml.Linq.XElement>de los antecesores de este elemento.</xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601> Una sobrecarga devuelve un <xref:System.Collections.Generic.IEnumerable%601>de <xref:System.Xml.Linq.XElement>los antecesores que tengan especificada <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName> </xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601>|  
|<xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=fullName></xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=fullName>|Devuelve un <xref:System.Collections.Generic.IEnumerable%601>de <xref:System.Xml.Linq.XElement>de los descendientes de este elemento.</xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601> Una sobrecarga devuelve un <xref:System.Collections.Generic.IEnumerable%601>de <xref:System.Xml.Linq.XElement>los descendientes que tienen especificada <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName> </xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601>|  
|<xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName></xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName>|Devuelve un <xref:System.Collections.Generic.IEnumerable%601>de <xref:System.Xml.Linq.XElement>de los elementos secundarios de este elemento.</xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601> Una sobrecarga devuelve un <xref:System.Collections.Generic.IEnumerable%601>de <xref:System.Xml.Linq.XElement>los elementos secundarios que tienen especificada <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName> </xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601>|  
|<xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A?displayProperty=fullName></xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A?displayProperty=fullName>|Devuelve un <xref:System.Collections.Generic.IEnumerable%601>de <xref:System.Xml.Linq.XElement>de los elementos que siguen a este elemento.</xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601> Una sobrecarga devuelve un <xref:System.Collections.Generic.IEnumerable%601>de <xref:System.Xml.Linq.XElement>los elementos después de este elemento que tienen especificada <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName> </xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601>|  
|<xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=fullName></xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=fullName>|Devuelve un <xref:System.Collections.Generic.IEnumerable%601>de <xref:System.Xml.Linq.XElement>de los elementos que se encuentran antes que este elemento.</xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601> Una sobrecarga devuelve un <xref:System.Collections.Generic.IEnumerable%601>de <xref:System.Xml.Linq.XElement>los elementos antes de este elemento que tienen especificada <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName> </xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601>|  
|<xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A?displayProperty=fullName>|Devuelve un <xref:System.Collections.Generic.IEnumerable%601>de <xref:System.Xml.Linq.XElement>de este elemento y sus antecesores.</xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601> Una sobrecarga devuelve un <xref:System.Collections.Generic.IEnumerable%601>de <xref:System.Xml.Linq.XElement>los elementos que tienen especificada <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName> </xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601>|  
|<xref:System.Xml.Linq.XElement.DescendantsAndSelf%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.DescendantsAndSelf%2A?displayProperty=fullName>|Devuelve un <xref:System.Collections.Generic.IEnumerable%601>de <xref:System.Xml.Linq.XElement>de este elemento y sus descendientes.</xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601> Una sobrecarga devuelve un <xref:System.Collections.Generic.IEnumerable%601>de <xref:System.Xml.Linq.XElement>los elementos que tienen especificada <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName> </xref:System.Xml.Linq.XElement> </xref:System.Collections.Generic.IEnumerable%601>|  
  
## <a name="method-for-retrieving-a-single-element"></a>Método para recuperar un único elemento  
 El siguiente método recupera un único elemento secundario de un <xref:System.Xml.Linq.XElement>objeto.</xref:System.Xml.Linq.XElement>  
  
|Método|Descripción|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XContainer.Element%2A?displayProperty=fullName></xref:System.Xml.Linq.XContainer.Element%2A?displayProperty=fullName>|Devuelve el primer <xref:System.Xml.Linq.XElement>objeto que tiene especificada <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName> </xref:System.Xml.Linq.XElement> de secundarios|  
  
## <a name="method-for-retrieving-a-collection-of-attributes"></a>Método para recuperar una colección de atributos  
 El siguiente método recupera atributos a partir un <xref:System.Xml.Linq.XElement>objeto.</xref:System.Xml.Linq.XElement>  
  
|Método|Descripción|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XElement.Attributes%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Attributes%2A?displayProperty=fullName>|Devuelve un <xref:System.Collections.Generic.IEnumerable%601>de <xref:System.Xml.Linq.XAttribute>de todos los atributos.</xref:System.Xml.Linq.XAttribute> </xref:System.Collections.Generic.IEnumerable%601>|  
  
## <a name="method-for-retrieving-a-single-attribute"></a>Método para recuperar un único atributo  
 El siguiente método recupera un único atributo de un <xref:System.Xml.Linq.XElement>objeto.</xref:System.Xml.Linq.XElement>  
  
|Método|Descripción|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=fullName>|Devuelve la <xref:System.Xml.Linq.XAttribute>que tenga especificada <xref:System.Xml.Linq.XName>.</xref:System.Xml.Linq.XName> </xref:System.Xml.Linq.XAttribute>|  
  
## <a name="see-also"></a>Vea también  
 [Ejes LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
