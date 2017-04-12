---
title: "Programación funcional frente a Programación de procedimientos (LINQ to XML) (Visual Basic) | Documentos de Microsoft"
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
ms.assetid: ea1015a5-d4c8-4d79-8e1e-ba17a40a4f39
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 9d5afe31c8c81f4b099853a5e6e274156a1baa7f
ms.lasthandoff: 03/13/2017

---
# <a name="functional-vs-procedural-programming-linq-to-xml-visual-basic"></a>Programación funcional frente a Programación de procedimientos (LINQ to XML) (Visual Basic)
Existen varios tipos de aplicaciones XML:  
  
-   Algunas aplicaciones toman los documentos XML de origen y crean nuevos documentos XML que tienen una forma diferente que los documentos de origen.  
  
-   Algunas aplicaciones toman documentos XML de origen y crean documentos de resultado de una forma totalmente diferente, como archivos HTML o de texto CSV.  
  
-   Algunas aplicaciones toman documentos XML de origen e insertan registros en una base de datos.  
  
-   Algunas aplicaciones toman datos de otro origen de datos, como una base de datos y crean documentos XML a partir de él.  
  
 Estos no son todos los tipos de aplicaciones XML, pero son un conjunto representativo de los tipos de funcionalidad que un programador XML debe implementar.  
  
 Con todos esos tipos de aplicaciones un desarrollador puede tomar dos enfoques opuestos:  
  
-   Construcción funcional usando un enfoque declarativo.  
  
-   Modificación del árbol XML en memoria usando código de procedimiento.  
  
 LINQ to XML admite ambos enfoques.  
  
 Cuando se utiliza el enfoque funcional, se escriben transformaciones que toman los documentos de origen y generan documentos de resultados completamente nuevos con la forma que se desee.  
  
 Cuando se modifica un árbol XML, se escribe código que atraviese los nodos de un árbol XML y navegue por ellos en memoria para insertar, eliminar y modificar nodos según sea necesario.  
  
 Puede usar LINQ to XML con cualquier enfoque. Se usan las mismas clases y, en algunos casos, los mismos métodos. No obstante, la estructura y los objetivos de los dos enfoques son muy diferentes. Por ejemplo, en situaciones diferentes, uno u otro enfoque tendrá a menudo un rendimiento mejor y usará más o menos memoria. Asimismo, uno u otro enfoque será más fácil de escribir y proporcionará código más fácil de mantener.  
  
 Para ver los dos enfoques diferencias, consulte [frente a la modificación del árbol XML en memoria. Construcción funcional (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/in-memory-xml-tree-modification-vs-functional-construction.md).  
  
 Para obtener un tutorial sobre cómo escribir transformaciones funcionales, vea [Pure Functional Transformations of XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/pure-functional-transformations-of-xml.md).  
  
## <a name="see-also"></a>Vea también  
 [LINQ to XML de información general de programación (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
