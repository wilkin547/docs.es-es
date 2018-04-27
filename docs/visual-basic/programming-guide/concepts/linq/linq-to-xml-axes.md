---
title: Ejes LINQ to XML (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ecd3bd00-28e5-4517-a59f-53bff39fd478
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 404ddcc89e6549d7575761e10c23413d9688a38f
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="linq-to-xml-axes-visual-basic"></a>Ejes LINQ to XML (Visual Basic)
Tras crear un árbol XML o haber cargado un documento XML en un árbol XML, puede realizar consultas sobre él para encontrar elementos y atributos, así como para recuperar sus valores.  
  
 Antes de poder escribir consultas, debe entender los ejes [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]. Hay dos clases de métodos de eje. En primer lugar, hay métodos a los que se llama en un solo objeto <xref:System.Xml.Linq.XElement>, un objeto <xref:System.Xml.Linq.XDocument> o un objeto <xref:System.Xml.Linq.XNode>. Estos métodos funcionan en un objeto único y devuelven una colección de objetos <xref:System.Xml.Linq.XElement>, <xref:System.Xml.Linq.XAttribute> o <xref:System.Xml.Linq.XNode>. En segundo lugar, existen métodos de extensión que funcionan en colecciones y devuelven colecciones. Los métodos de extensión enumeran la colección de origen, llaman al método de eje adecuado en cada elemento de la colección y concatenan los resultados.  
  
## <a name="in-this-section"></a>En esta sección  
  
|Tema|Descripción|  
|-----------|-----------------|  
|[LINQ to XML ejes Introducción (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes-overview.md)|Define ejes y explica cómo se usan en el contexto de las consultas [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].|  
|[Cómo: recuperar una colección de elementos (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-a-collection-of-elements-linq-to-xml.md)|Presenta el método <xref:System.Xml.Linq.XContainer.Elements%2A>. Este método recupera una colección de elementos secundarios de un elemento.|  
|[Cómo: recuperar el valor de un elemento (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-the-value-of-an-element-linq-to-xml.md)|Muestra cómo obtener los valores de los elementos.|  
|[Cómo: filtrar por nombres de elemento (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-filter-on-element-names-linq-to-xml.md)|Muestra cómo filtrar por nombres de elemento al usar los ejes.|  
|[Cómo: encadenar llamadas de método de eje (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-chain-axis-method-calls-linq-to-xml.md)|Muestra cómo encadenar llamadas a métodos de eje.|  
|[Cómo: recuperar un único elemento secundario (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-a-single-child-element-linq-to-xml.md)|Muestra cómo recuperar un elemento secundario de un elemento, con el nombre de etiqueta de dicho elemento secundario.|  
|[Cómo: recuperar una colección de atributos (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-a-collection-of-attributes-linq-to-xml.md)|Presenta el método <xref:System.Xml.Linq.XElement.Attributes%2A>. Este método recupera los atributos de un elemento.|  
|[Cómo: recuperar un solo atributo (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-a-single-attribute-linq-to-xml.md)|Muestra cómo recuperar un atributo de un elemento, con el nombre del atributo.|  
|[Cómo: recuperar el valor de un atributo (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-the-value-of-an-attribute-linq-to-xml.md)|Muestra cómo obtener los valores de los atributos.|  
|[Cómo: recuperar el valor superficial de un elemento (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-the-shallow-value-of-an-element.md)|Muestra cómo recuperar el valor superficial de un elemento.|  
|[Ejes integrados de lenguaje en Visual Basic (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/language-integrated-axes.md)|Resume los ejes integrado de Visual Basic.|  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)
