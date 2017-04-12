---
title: "Modificar árboles XML (LINQ to XML) (Visual Basic) | Documentos de Microsoft"
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
ms.assetid: 4ae511a5-4fc9-4178-9c8e-761357deae3f
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: cf605973e68230e9e3e09f0abf6de49635cd5845
ms.lasthandoff: 03/13/2017


---
# <a name="modifying-xml-trees-linq-to-xml-visual-basic"></a>Modificar árboles XML (LINQ to XML) (Visual Basic)
[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] es el almacén de datos en memoria para un árbol XML. Una vez que haya cargado o analizado un árbol XML desde un origen, [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] le permite modificar ese árbol y luego serializarlo, quizá guardarlo en un archivo o enviarlos a un servidor remoto.  
  
 Cuando se modifica un árbol en su lugar, puede utilizar ciertos métodos, como <xref:System.Xml.Linq.XContainer.Add%2A>.</xref:System.Xml.Linq.XContainer.Add%2A>  
  
 No obstante, existe otra aproximación posible, la cual consiste en utilizar una construcción funcional para generar un árbol nuevo que tenga un aspecto diferente. Dependiendo de los tipos de cambios que necesite hacer en el árbol XML y del tamaño de éste, es posible que esta aproximación resulte más robusta y sencilla de desarrollar. El primer punto de esta sección compara ambas aproximaciones.  
  
## <a name="in-this-section"></a>En esta sección  
  
|Tema|Descripción|  
|-----------|-----------------|  
|[Diferencias entre la modificación del árbol XML en memoria y Construcción funcional (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/in-memory-xml-tree-modification-vs-functional-construction.md)|Comparación entre modificar un árbol XML en memoria y mediante una construcción funcional|  
|[Agregar elementos, atributos y nodos a un árbol XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/adding-elements-attributes-and-nodes-to-an-xml-tree.md)|Proporciona información acerca de cómo agregar elementos, atributos o nodos a un árbol XML.|  
|[Modificar elementos, atributos y nodos de un árbol XML](../../../../visual-basic/programming-guide/concepts/linq/modifying-elements-attributes-and-nodes-in-an-xml-tree.md)|Proporciona información acerca de cómo modificar elementos, atributos o nodos ya existentes.|  
|[Quitar elementos, atributos y nodos de un árbol XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/removing-elements-attributes-and-nodes-from-an-xml-tree.md)|Proporciona información acerca de cómo eliminar elementos, atributos o nodos de un árbol XML.|  
|[Mantenimiento de pares nombre/valor (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/maintaining-name-value-pairs.md)|Describe cómo mantener aquella información de la aplicación que es mejor guardar en forma de pares nombre/valor, como por ejemplo, información sobre configuración o valores globales.|  
|[Cómo: cambiar el Namespace para un árbol XML completo (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-change-the-namespace-for-an-entire-xml-tree.md)|Muestra cómo mover un árbol XML de un espacio de nombres a otro.|  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)
