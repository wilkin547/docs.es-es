---
title: Modificar árboles XML (LINQ to XML) (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 4ae511a5-4fc9-4178-9c8e-761357deae3f
ms.openlocfilehash: 4673902880822e6e4ed0bc144aedc2428faa5b69
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62031803"
---
# <a name="modifying-xml-trees-linq-to-xml-visual-basic"></a>Modificar árboles XML (LINQ to XML) (Visual Basic)
[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] es el almacén de datos en memoria para un árbol XML. Una vez haya cargado o analizado un árbol XML a partir de un origen, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] le permitirá modificarlo en el momento, para luego serializarlo, quizá con el objetivo de guardarlo en un archivo o de enviarlo a un servidor remoto.  
  
 A la hora de modificar un árbol, puede utilizar ciertos métodos, como por ejemplo, <xref:System.Xml.Linq.XContainer.Add%2A>.  
  
 No obstante, existe otro enfoque, el cual consiste en usar una construcción funcional para generar un árbol nuevo que tenga otro aspecto. En función de los tipos de cambios que necesite hacer en el árbol XML y del tamaño de este, es posible que este enfoque resulte más robusto y sencillo de desarrollar. El primer punto de esta sección compara ambos enfoques.  
  
## <a name="in-this-section"></a>En esta sección  
  
|Tema|Descripción|  
|-----------|-----------------|  
|[Diferencias entre la modificación del árbol XML en memoria y Construcción funcional (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/in-memory-xml-tree-modification-vs-functional-construction.md)|Comparación entre modificar un árbol XML en memoria y mediante una construcción funcional|  
|[Agregar elementos, atributos y nodos a un árbol XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/adding-elements-attributes-and-nodes-to-an-xml-tree.md)|Proporciona información acerca de cómo agregar elementos, atributos o nodos a un árbol XML.|  
|[Modificar elementos, atributos y nodos de un árbol XML](../../../../visual-basic/programming-guide/concepts/linq/modifying-elements-attributes-and-nodes-in-an-xml-tree.md)|Proporciona información acerca de cómo modificar elementos, atributos o nodos ya existentes.|  
|[Quitar elementos, atributos y nodos de un árbol XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/removing-elements-attributes-and-nodes-from-an-xml-tree.md)|Proporciona información acerca de cómo eliminar elementos, atributos o nodos de un árbol XML.|  
|[Mantener pares nombre/valor (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/maintaining-name-value-pairs.md)|Describe cómo mantener aquella información de la aplicación que es mejor guardar en forma de pares nombre/valor, como por ejemplo, información sobre configuración o valores globales.|  
|[Cómo: Cambiar el Namespace para todo un árbol XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-change-the-namespace-for-an-entire-xml-tree.md)|Muestra cómo mover un árbol XML de un espacio de nombres a otro.|  
  
## <a name="see-also"></a>Vea también

- [Guía de programación (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)
