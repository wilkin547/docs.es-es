---
title: "Consultas básicas (LINQ to XML) (C#) | Microsoft Docs"
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
ms.assetid: d333bb7d-20c1-448a-95b7-e5ba07915744
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: e3879dfe92f158c545a1f4a42c6bfc35aae06f3c
ms.lasthandoff: 03/13/2017


---
# <a name="basic-queries-linq-to-xml-c"></a>Consultas básicas (LINQ to XML) (C#)
En esta sección se ofrecen ejemplos de consultas básicas de [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].  
  
## <a name="in-this-section"></a>En esta sección  
  
|Tema|Descripción|  
|-----------|-----------------|  
|[How to: Find an Element with a Specific Attribute (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-find-an-element-with-a-specific-attribute.md) (Cómo: Buscar un elemento con un atributo específico (C#))|Muestra cómo encontrar un elemento en particular que tenga un atributo con un valor específico.|  
|[How to: Find an Element with a Specific Child Element (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-find-an-element-with-a-specific-child-element.md) (Cómo: Buscar un elemento con un elemento secundario específico (C#))|Muestra cómo encontrar un elemento en particular que tenga un elemento secundario con un valor específico.|  
|[Diferencias entre realizar consultas de un XDocument frente a realizar consultas de un XElement (C#)](../../../../csharp/programming-guide/concepts/linq/querying-an-xdocument-vs-querying-an-xelement.md)|Explica las diferencias entre escribir consultas en un árbol XML cuya raíz comienza en <xref:System.Xml.Linq.XElement> y escribir consultas sobre un árbol XML cuya raíz comienza en <xref:System.Xml.Linq.XDocument>.|  
|[How to: Find Descendants with a Specific Element Name (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-find-descendants-with-a-specific-element-name.md) (Cómo: Buscar descendientes con un nombre de elemento específico (C#))|Muestra cómo encontrar todos los descendientes de un elemento que tengan un nombre en particular. En este ejemplo se usa el eje <xref:System.Xml.Linq.XContainer.Descendants%2A>.|  
|[How to: Find a Single Descendant Using the Descendants Method (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-find-a-single-descendant-using-the-descendants-method.md) (Buscar un único descendiente usando el método Descendants (C#))|Muestra cómo usar el método de eje <xref:System.Xml.Linq.XContainer.Descendants%2A> para buscar un solo elemento cuyo nombre es único.|  
|[How to: Write Queries with Complex Filtering (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-write-queries-with-complex-filtering.md) (Cómo: Escribir consultas con filtrado complejo (C#))|Muestra cómo escribir una consulta que utilice un filtro más complejo.|  
|[How to: Filter on an Optional Element (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-filter-on-an-optional-element.md) (Cómo: Filtrar por un elemento opcional (C#))|Muestra cómo encontrar nodos en un árbol con forma irregular.|  
|[How to: Find All Nodes in a Namespace (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-find-all-nodes-in-a-namespace.md) (Cómo: Buscar todos los nodos de un espacio de nombres (C#))|Muestra cómo encontrar todos los nodos que se encuentren en un espacio de nombres en particular.|  
|[How to: Sort Elements (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-sort-elements.md) (Cómo: Ordenar elementos (C#))|Muestra cómo escribir una consulta que ordene sus resultados.|  
|[How to: Sort Elements on Multiple Keys (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-sort-elements-on-multiple-keys.md) (Cómo: Ordenar elementos en varias claves (C#))|Muestra cómo ordenar por varias claves.|  
|[How to: Calculate Intermediate Values (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-calculate-intermediate-values.md) (Cómo: Calcular valores intermedios (C#))|Muestra cómo usar la cláusula `Let` para calcular valores intermedios en una consulta [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].|  
|[How to: Write a Query that Finds Elements Based on Context (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-write-a-query-that-finds-elements-based-on-context.md) (Cómo: Escribir una consulta que busca elementos en función del contexto (C#))|Muestra cómo seleccionar elementos en base a otros elementos del árbol.|  
|[How to: Debug Empty Query Results Sets (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-debug-empty-query-results-sets.md) (Cómo: Depurar conjuntos de resultados de consulta vacíos (C#))|Muestra la solución apropiada cuando se depuran consultas sobre un XML que se encuentra en un espacio de nombres predeterminado.|  
  
## <a name="see-also"></a>Vea también  
 [Consultar árboles XML (C#)](../../../../csharp/programming-guide/concepts/linq/querying-xml-trees.md)
