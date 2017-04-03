---
title: "Información general sobre los ejes de LINQ to XML (C#) | Microsoft Docs"
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
ms.assetid: 516792fb-461d-40a8-8a50-9993a51258fc
caps.latest.revision: 4
author: BillWagner
ms.author: wiwagn
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: b43d3cb5cc7154c1133c5fa17e5bdacca97a38c9
ms.lasthandoff: 03/13/2017


---
# <a name="linq-to-xml-axes-overview-c"></a>Información general sobre los ejes de LINQ to XML (C#)
Tras crear un árbol XML o haber cargado un documento XML en un árbol XML, puede realizar consultas sobre él para encontrar elementos y atributos, así como para recuperar sus valores. Las colecciones se recuperan mediante los *métodos de eje*, también denominados *ejes*. Algunos de los ejes son métodos de las clases <xref:System.Xml.Linq.XElement> y <xref:System.Xml.Linq.XDocument> que devuelven colecciones <xref:System.Collections.Generic.IEnumerable%601>. Algunos de los ejes son métodos de extensión de la clase <xref:System.Xml.Linq.Extensions>. Los ejes que se han implementado como métodos de extensión trabajan colecciones y devuelven colecciones.  
  
 Como se describe en [Información general acerca de la clase XElement](http://msdn.microsoft.com/library/d35180fe-7016-4895-9bfc-ba1e3f7875ec), un objeto <xref:System.Xml.Linq.XElement> representa un nodo de elemento único. El contenido de un elemento puede ser complejo (a veces conocido como contenido estructurado) o puede ser un elemento simple. Un elemento simple puede estar vacío o contener un valor. Si el nodo incluye contenido estructurado, puede utilizar diferentes métodos del eje para recuperar enumeraciones con los elementos descendientes. Los métodos de ejes que más se usan son <xref:System.Xml.Linq.XContainer.Elements%2A> y <xref:System.Xml.Linq.XContainer.Descendants%2A>.  
  
 Además de los métodos de eje, que devuelven colecciones, existen otros dos métodos que usará con regularidad en consultas [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]. El método <xref:System.Xml.Linq.XContainer.Element%2A> devuelve un único <xref:System.Xml.Linq.XElement>. El método <xref:System.Xml.Linq.XElement.Attribute%2A> devuelve un único <xref:System.Xml.Linq.XAttribute>.  
  
 Por diversas razones, las consultas de [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] ofrecen el mecanismo más potente para examinar árboles, extraer datos de ellos y para transformarlos. Las consultas [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] funcionan en objetos que implementan <xref:System.Collections.Generic.IEnumerable%601>, y los ejes [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] devuelven <xref:System.Collections.Generic.IEnumerable%601> de colecciones <xref:System.Xml.Linq.XElement>, así como <xref:System.Collections.Generic.IEnumerable%601> de colecciones <xref:System.Xml.Linq.XAttribute>. Para poder realizar las consultas, necesitará estas colecciones.  
  
 A parte de los métodos de ejes que permiten recuperar colecciones de elementos y atributos, existen métodos de ejes que le permiten iterar por un árbol con gran detalle. Por ejemplo, en vez de tratar directamente con los elementos y los atributos, podría trabajar con los nodos del árbol. Los nodos tienen un nivel de granularidad mayor que los elementos y atributos. Si trabaja con nodos, podrá examinar comentarios XML, nodos de texto, instrucciones de procesamiento, etc. Esta funcionalidad resultaría interesante, por ejemplo, para una persona que estuviese escribiendo un procesador de textos y quisiera guardar los documentos en formato XML. No obstante, la mayoría de programadores en XML se centran más en los elementos, los atributos y sus valores.  
  
## <a name="methods-for-retrieving-a-collection-of-elements"></a>Métodos para recuperar una colección de elementos  
 A continuación encontrará un resumen de los métodos de la clase <xref:System.Xml.Linq.XElement> (o de sus clases base) a los que podrá llamar en un <xref:System.Xml.Linq.XElement> para devolver una colección de elementos.  
  
|Método|Descripción|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XNode.Ancestors%2A?displayProperty=fullName>|Devuelve un <xref:System.Collections.Generic.IEnumerable%601> de <xref:System.Xml.Linq.XElement> de los antecesores de este elemento. Una sobrecarga devuelve un <xref:System.Collections.Generic.IEnumerable%601> de <xref:System.Xml.Linq.XElement> de los antecesores que tengan especificado <xref:System.Xml.Linq.XName>.|  
|<xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=fullName>|Devuelve un <xref:System.Collections.Generic.IEnumerable%601> de <xref:System.Xml.Linq.XElement> de los descendientes de este elemento. Una sobrecarga devuelve un <xref:System.Collections.Generic.IEnumerable%601> de <xref:System.Xml.Linq.XElement> de los descendientes que tengan especificado <xref:System.Xml.Linq.XName>.|  
|<xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName>|Devuelve un <xref:System.Collections.Generic.IEnumerable%601> de <xref:System.Xml.Linq.XElement> de los elementos secundarios de este elemento. Una sobrecarga devuelve un <xref:System.Collections.Generic.IEnumerable%601> de <xref:System.Xml.Linq.XElement> de los elementos secundarios que tengan especificado <xref:System.Xml.Linq.XName>.|  
|<xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A?displayProperty=fullName>|Devuelve un <xref:System.Collections.Generic.IEnumerable%601> de <xref:System.Xml.Linq.XElement> de los elementos que se encuentran después de este elemento. Una sobrecarga devuelve un <xref:System.Collections.Generic.IEnumerable%601> de <xref:System.Xml.Linq.XElement> de los elementos que se encuentran después de este elemento y que tengan especificado <xref:System.Xml.Linq.XName>.|  
|<xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=fullName>|Devuelve un <xref:System.Collections.Generic.IEnumerable%601> de <xref:System.Xml.Linq.XElement> de los elementos que se encuentran antes de este elemento. Una sobrecarga devuelve un <xref:System.Collections.Generic.IEnumerable%601> de <xref:System.Xml.Linq.XElement> de los elementos que se encuentran antes de este elemento y que tengan especificado <xref:System.Xml.Linq.XName>.|  
|<xref:System.Xml.Linq.XElement.AncestorsAndSelf%2A?displayProperty=fullName>|Devuelve un <xref:System.Collections.Generic.IEnumerable%601> de <xref:System.Xml.Linq.XElement> de este elemento y sus antecesores. Una sobrecarga devuelve un <xref:System.Collections.Generic.IEnumerable%601> de <xref:System.Xml.Linq.XElement> de los elementos que tengan especificado <xref:System.Xml.Linq.XName>.|  
|<xref:System.Xml.Linq.XElement.DescendantsAndSelf%2A?displayProperty=fullName>|Devuelve un <xref:System.Collections.Generic.IEnumerable%601> de <xref:System.Xml.Linq.XElement> de este elemento y sus descendientes. Una sobrecarga devuelve un <xref:System.Collections.Generic.IEnumerable%601> de <xref:System.Xml.Linq.XElement> de los elementos que tengan especificado <xref:System.Xml.Linq.XName>.|  
  
## <a name="method-for-retrieving-a-single-element"></a>Método para recuperar un único elemento  
 El siguiente método recupera un único elemento secundario a partir de un objeto <xref:System.Xml.Linq.XElement>.  
  
|Método|Descripción|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XContainer.Element%2A?displayProperty=fullName>|Devuelve el objeto del primer <xref:System.Xml.Linq.XElement> secundario que tenga el <xref:System.Xml.Linq.XName> especificado.|  
  
## <a name="method-for-retrieving-a-collection-of-attributes"></a>Método para recuperar una colección de atributos  
 El siguiente método recupera atributos a partir de un objeto <xref:System.Xml.Linq.XElement>.  
  
|Método|Descripción|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XElement.Attributes%2A?displayProperty=fullName>|Devuelve un <xref:System.Collections.Generic.IEnumerable%601> de <xref:System.Xml.Linq.XAttribute> de todos los atributos.|  
  
## <a name="method-for-retrieving-a-single-attribute"></a>Método para recuperar un único atributo  
 El siguiente método recupera un único atributo a partir de un objeto <xref:System.Xml.Linq.XElement>.  
  
|Método|Descripción|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=fullName>|Devuelve el <xref:System.Xml.Linq.XAttribute> que tenga el <xref:System.Xml.Linq.XName> especificado.|  
  
## <a name="see-also"></a>Vea también  
 [Ejes de LINQ to XML (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes.md)
