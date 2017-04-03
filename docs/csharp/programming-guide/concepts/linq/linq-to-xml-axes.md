---
title: Ejes de LINQ to XML (C#) | Microsoft Docs
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
ms.assetid: 3f7d54ff-b608-43a1-9e2d-e70668b72df8
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
ms.openlocfilehash: 696a9057d5eb9d2a8c3a263c02571a0913af89f3
ms.lasthandoff: 03/13/2017

---
# <a name="linq-to-xml-axes-c"></a>Ejes de LINQ to XML (C#)
Tras crear un árbol XML o haber cargado un documento XML en un árbol XML, puede realizar consultas sobre él para encontrar elementos y atributos, así como para recuperar sus valores.  
  
 Antes de poder escribir consultas, debe entender los ejes [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]. Hay dos tipos de métodos de eje. En primer lugar, están los métodos que se llaman en un único objeto <xref:System.Xml.Linq.XElement>, objeto <xref:System.Xml.Linq.XDocument> u objeto <xref:System.Xml.Linq.XNode>. Estos métodos actúan en un único objeto y devuelven una colección de objetos <xref:System.Xml.Linq.XElement>, <xref:System.Xml.Linq.XAttribute> o <xref:System.Xml.Linq.XNode>. En segundo lugar, existen métodos de extensión que funcionan en colecciones y devuelven colecciones. Los métodos de extensión enumeran la colección de origen, llaman al método de eje adecuado en cada elemento de la colección y concatenan los resultados.  
  
## <a name="in-this-section"></a>En esta sección  
  
|Tema|Descripción|  
|-----------|-----------------|  
|[Información general sobre los ejes de LINQ to XML (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes-overview.md)|Define ejes y explica cómo se usan en el contexto de las consultas [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].|  
|[Cómo: Recuperar una colección de elementos (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-retrieve-a-collection-of-elements-linq-to-xml.md)|Presenta el método <xref:System.Xml.Linq.XContainer.Elements%2A>. Este método recupera una colección de elementos secundarios de un elemento.|  
|[Cómo: Recuperar el valor de un elemento (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-retrieve-the-value-of-an-element-linq-to-xml.md)|Muestra cómo obtener los valores de los elementos.|  
|[Cómo: Filtrar por nombres de elemento (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-filter-on-element-names-linq-to-xml.md)|Muestra cómo filtrar por nombres de elemento al usar los ejes.|  
|[Cómo: Encadenar llamadas de métodos de eje (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-chain-axis-method-calls-linq-to-xml.md)|Muestra cómo encadenar llamadas a métodos de eje.|  
|[Cómo: Recuperar un único elemento secundario (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-retrieve-a-single-child-element-linq-to-xml.md)|Muestra cómo recuperar un elemento secundario de un elemento, con el nombre de etiqueta de dicho elemento secundario.|  
|[Cómo: Recuperar una colección de atributos (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-retrieve-a-collection-of-attributes-linq-to-xml.md)|Presenta el método <xref:System.Xml.Linq.XElement.Attributes%2A>. Este método recupera los atributos de un elemento.|  
|[Cómo: Recuperar un único atributo (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-retrieve-a-single-attribute-linq-to-xml.md)|Muestra cómo recuperar un atributo de un elemento, con el nombre del atributo.|  
|[Cómo: Recuperar el valor de un atributo (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-retrieve-the-value-of-an-attribute-linq-to-xml.md)|Muestra cómo obtener los valores de los atributos.|  
|[Cómo: Recuperar el valor superficial de un elemento (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-retrieve-the-shallow-value-of-an-element.md)|Muestra cómo recuperar el valor superficial de un elemento.|  
  
## <a name="see-also"></a>Vea también  
 [Métodos de extensión (Guía de programación de C#)](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md)   
 [Guía de programación (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)
