---
title: "Modificar árboles XML (LINQ to XML) (C#) | Microsoft Docs"
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
ms.assetid: 8ec47e6d-2363-4694-be46-8d5ca4d15fc9
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: b7de6f5d53767a6d7910762618a109e5202d988e
ms.lasthandoff: 03/13/2017


---
# <a name="modifying-xml-trees-linq-to-xml-c"></a>Modificar árboles XML (LINQ to XML) (C#)
[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] es el almacén de datos en memoria para un árbol XML. Una vez haya cargado o analizado un árbol XML a partir de un origen, [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] le permitirá modificarlo en el momento, para luego serializarlo, quizá con el objetivo de guardarlo en un archivo o de enviarlo a un servidor remoto.  
  
 A la hora de modificar un árbol, puede usar ciertos métodos, como por ejemplo, <xref:System.Xml.Linq.XContainer.Add%2A>.  
  
 No obstante, existe otra aproximación posible, la cual consiste en utilizar una construcción funcional para generar un árbol nuevo que tenga un aspecto diferente. Dependiendo de los tipos de cambios que necesite hacer en el árbol XML y del tamaño de éste, es posible que esta aproximación resulte más robusta y sencilla de desarrollar. El primer punto de esta sección compara ambas aproximaciones.  
  
## <a name="in-this-section"></a>En esta sección  
  
|Tema|Descripción|  
|-----------|-----------------|  
|[Diferencias entre la modificación del árbol XML en memoria y Construcción funcional (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/in-memory-xml-tree-modification-vs-functional-construction-linq-to-xml.md)|Comparación entre modificar un árbol XML en memoria y mediante una construcción funcional|  
|[Agregar elementos, atributos y nodos a un árbol XML (C#)](../../../../csharp/programming-guide/concepts/linq/adding-elements-attributes-and-nodes-to-an-xml-tree.md)|Proporciona información acerca de cómo agregar elementos, atributos o nodos a un árbol XML.|  
|[Modificar elementos, atributos y nodos de un árbol XML](../../../../csharp/programming-guide/concepts/linq/modifying-elements-attributes-and-nodes-in-an-xml-tree.md)|Proporciona información acerca de cómo modificar elementos, atributos o nodos ya existentes.|  
|[Quitar elementos, atributos y nodos de un árbol XML (C#)](../../../../csharp/programming-guide/concepts/linq/removing-elements-attributes-and-nodes-from-an-xml-tree.md)|Proporciona información acerca de cómo eliminar elementos, atributos o nodos de un árbol XML.|  
|[Mantener pares nombre-valor (C#)](../../../../csharp/programming-guide/concepts/linq/maintaining-name-value-pairs.md)|Describe cómo mantener aquella información de la aplicación que es mejor guardar en forma de pares nombre/valor, como por ejemplo, información sobre configuración o valores globales.|  
|[Cómo: Cambiar el espacio de nombres de todo un árbol XML (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-change-the-namespace-for-an-entire-xml-tree.md)|Muestra cómo mover un árbol XML de un espacio de nombres a otro.|  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)
