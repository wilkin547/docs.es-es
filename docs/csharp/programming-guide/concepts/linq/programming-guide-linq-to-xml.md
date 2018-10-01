---
title: Guía de programación (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: 4b1ffd10-ab81-4a0d-a0ca-e9876478d924
ms.openlocfilehash: acb8271ad9ea338d31516c35bae46593a5fd2f78
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2018
ms.locfileid: "47199053"
---
# <a name="programming-guide-linq-to-xml-c"></a>Guía de programación (LINQ to XML) (C#)
En esta sección se ofrece información conceptual y paso a paso acerca de la programación con [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].  
  
## <a name="who-should-read-this-documentation"></a>A quiénes va destinada esta documentación  
 Esta documentación se dirige a aquellos desarrolladores que ya conocen C# y algunos aspectos básicos de [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].  
  
 El objetivo de esta documentación es facilitar el uso de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] a todo tipo de desarrolladores. [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] hace que la programación XML sea más sencilla. No necesita ser un experto desarrollador para utilizarla.  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] se basa principalmente en clases genéricas. Por tanto, es muy importante que comprenda cómo se utilizan las clases genéricas. Más aún, resultaría de utilidad que estuviera familiarizado con los delegados que se declaran como tipos parametrizados. Si no está familiarizado con las clases genéricas de C#, vea [Clases genéricas](../../../../csharp/programming-guide/generics/generic-classes.md).  
  
## <a name="in-this-section"></a>En esta sección  
  
|Tema|Descripción|  
|-----------|-----------------|  
|[Información general sobre la programación de LINQ to XML (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)|Ofrece una descripción general de las clases de [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], así como información detallada acerca de las tres clases más importantes: <xref:System.Xml.Linq.XElement>, <xref:System.Xml.Linq.XAttribute> y <xref:System.Xml.Linq.XDocument>.|  
|[Creating XML Trees (C#)](../../../../csharp/programming-guide/concepts/linq/creating-xml-trees.md) (Crear árboles XML (C#))|Proporciona información conceptual y paso a paso acerca de cómo crear árboles XML. Puede crear árboles XML utilizando una construcción funcional, o bien analizando el texto XML a partir de una cadena o de un archivo. También puede utilizar un <xref:System.Xml.XmlReader> para rellenar un árbol XML.|  
|[Trabajar con espacios de nombres XML (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md)|Proporciona información detallada acerca de cómo crear árboles XML que utilizan espacios de nombres.|  
|[Serializar árboles XML (C#)](../../../../csharp/programming-guide/concepts/linq/serializing-xml-trees.md)|Describe diferentes aproximaciones a la hora de serializar un árbol XML y proporciona una orientación de qué aproximación utilizar.|  
|[LINQ to XML Axes (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes.md) (Ejes de LINQ to XML [C#])|Enumera y describe los métodos del eje [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], los cuales deberá entender antes de poder escribir consultas [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].|  
|[Consultar árboles XML (C#)](../../../../csharp/programming-guide/concepts/linq/querying-xml-trees.md)|Proporciona ejemplos comunes acerca de la creación de consultas sobre árboles XML.|  
|[Modificar árboles XML (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)|Al igual que el Modelo de objetos de documento (DOM), [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] le permite modificar un árbol XML directamente.|  
|[Programación avanzada de LINQ to XML (C#)](../../../../csharp/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)|Proporciona información acerca de las anotaciones, los eventos, las secuencias y otros escenarios avanzados.|  
|[Seguridad de LINQ to XML (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-security.md)|Describe los problemas de seguridad asociados a LINQ to XML y ofrece una cierta orientación acerca de cómo minimizar el grado de exposición a esos problemas de seguridad.|  
|[Documentos XML de ejemplo (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-documents-linq-to-xml.md)|Contiene los documentos XML de muestra que utilizan numerosos ejemplos de esta documentación.|  
  
## <a name="see-also"></a>Vea también

- [Introducción (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/getting-started-linq-to-xml.md)  
- [LINQ to XML (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml.md)
