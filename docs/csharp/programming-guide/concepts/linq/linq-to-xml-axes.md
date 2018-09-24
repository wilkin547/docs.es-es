---
title: Ejes de LINQ to XML (C#)
ms.date: 07/20/2015
ms.assetid: 3f7d54ff-b608-43a1-9e2d-e70668b72df8
ms.openlocfilehash: 6a27adb1c7e1dcfefda13a355700202ccda3ffab
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2018
ms.locfileid: "46584128"
---
# <a name="linq-to-xml-axes-c"></a>Ejes de LINQ to XML (C#)
Tras crear un árbol XML o haber cargado un documento XML en un árbol XML, puede realizar consultas sobre él para encontrar elementos y atributos, así como para recuperar sus valores.  
  
 Antes de poder escribir consultas, debe entender los ejes [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]. Hay dos clases de métodos de eje. En primer lugar, hay métodos a los que se llama en un solo objeto <xref:System.Xml.Linq.XElement>, un objeto <xref:System.Xml.Linq.XDocument> o un objeto <xref:System.Xml.Linq.XNode>. Estos métodos funcionan en un objeto único y devuelven una colección de objetos <xref:System.Xml.Linq.XElement>, <xref:System.Xml.Linq.XAttribute> o <xref:System.Xml.Linq.XNode>. En segundo lugar, existen métodos de extensión que funcionan en colecciones y devuelven colecciones. Los métodos de extensión enumeran la colección de origen, llaman al método de eje adecuado en cada elemento de la colección y concatenan los resultados.  
  
## <a name="in-this-section"></a>En esta sección  
  
|Tema|Descripción|  
|-----------|-----------------|  
|[Información general sobre los ejes de LINQ to XML (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes-overview.md)|Define ejes y explica cómo se usan en el contexto de las consultas [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].|  
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

- [Métodos de extensión](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md)  
- [Guía de programación (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)
