---
title: Ejes LINQ to XML (Visual Basic) | Documentos de Microsoft
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
ms.assetid: ecd3bd00-28e5-4517-a59f-53bff39fd478
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
ms.openlocfilehash: 4d6466a78c3a8e9d21e30f2d3cf8a49ed89dafbf
ms.lasthandoff: 03/13/2017

---
# <a name="linq-to-xml-axes-visual-basic"></a>Ejes LINQ to XML (Visual Basic)
Tras crear un árbol XML o haber cargado un documento XML en un árbol XML, puede realizar consultas sobre él para encontrar elementos y atributos, así como para recuperar sus valores.  
  
 Antes de poder escribir consultas, debe entender los ejes [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]. Hay dos tipos de métodos de eje: primero, existen los métodos que llaman en un único <xref:System.Xml.Linq.XElement>objeto, <xref:System.Xml.Linq.XDocument>objeto, o <xref:System.Xml.Linq.XNode>objeto.</xref:System.Xml.Linq.XNode> </xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> Estos métodos funcionan en un objeto único y devuelven una colección de <xref:System.Xml.Linq.XElement>, <xref:System.Xml.Linq.XAttribute>, o <xref:System.Xml.Linq.XNode>objetos.</xref:System.Xml.Linq.XNode> </xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement> En segundo lugar, existen métodos de extensión que funcionan en colecciones y devuelven colecciones. Los métodos de extensión enumeran la colección de origen, llaman al método de eje adecuado en cada elemento de la colección y concatenan los resultados.  
  
## <a name="in-this-section"></a>En esta sección  
  
|Tema|Descripción|  
|-----------|-----------------|  
|[LINQ to XML ejes Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes-overview.md)|Define ejes y explica cómo se usan en el contexto de las consultas [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].|  
|[Cómo: recuperar una colección de elementos (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-a-collection-of-elements-linq-to-xml.md)|Presenta el <xref:System.Xml.Linq.XContainer.Elements%2A>método.</xref:System.Xml.Linq.XContainer.Elements%2A> Este método recupera una colección de elementos secundarios de un elemento.|  
|[Cómo: recuperar el valor de un elemento (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-the-value-of-an-element-linq-to-xml.md)|Muestra cómo obtener los valores de los elementos.|  
|[Cómo: filtrar nombres de elemento (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-filter-on-element-names-linq-to-xml.md)|Muestra cómo filtrar por nombres de elemento al usar los ejes.|  
|[Cómo: encadenar llamadas de método de eje (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-chain-axis-method-calls-linq-to-xml.md)|Muestra cómo encadenar llamadas a métodos de eje.|  
|[Cómo: recuperar un único elemento secundario (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-a-single-child-element-linq-to-xml.md)|Muestra cómo recuperar un elemento secundario de un elemento, con el nombre de etiqueta de dicho elemento secundario.|  
|[Cómo: recuperar una colección de atributos (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-a-collection-of-attributes-linq-to-xml.md)|Presenta el <xref:System.Xml.Linq.XElement.Attributes%2A>método.</xref:System.Xml.Linq.XElement.Attributes%2A> Este método recupera los atributos de un elemento.|  
|[Cómo: recuperar un solo atributo (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-a-single-attribute-linq-to-xml.md)|Muestra cómo recuperar un atributo de un elemento, con el nombre del atributo.|  
|[Cómo: recuperar el valor de un atributo (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-the-value-of-an-attribute-linq-to-xml.md)|Muestra cómo obtener los valores de los atributos.|  
|[Cómo: recuperar el valor superficial de un elemento (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-the-shallow-value-of-an-element.md)|Muestra cómo recuperar el valor superficial de un elemento.|  
|[Ejes integrados de lenguaje en Visual Basic (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/language-integrated-axes.md)|Resume la [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] ejes integrados.|  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)
