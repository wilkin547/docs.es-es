---
title: Programación funcional frente a programación basada en procedimientos (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: fc64e39c-a487-4882-9169-da4de97917d9
ms.openlocfilehash: e87114d2edcda4b2df14eb2d84f62ebe9638b5eb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "69594250"
---
# <a name="functional-vs-procedural-programming-linq-to-xml-c"></a>Programación funcional frente a programación basada en procedimientos (LINQ to XML) (C#)
Existen varios tipos de aplicaciones XML:  
  
- Algunas aplicaciones toman los documentos XML de origen y crean nuevos documentos XML que tienen una forma diferente que los documentos de origen.  
  
- Algunas aplicaciones toman documentos XML de origen y crean documentos de resultado de una forma totalmente diferente, como archivos HTML o de texto CSV.  
  
- Algunas aplicaciones toman documentos XML de origen e insertan registros en una base de datos.  
  
- Algunas aplicaciones toman datos de otro origen de datos, como una base de datos y crean documentos XML a partir de él.  
  
 Estos no son todos los tipos de aplicaciones XML, pero son un conjunto representativo de los tipos de funcionalidad que un programador XML debe implementar.  
  
 Con todos esos tipos de aplicaciones un desarrollador puede tomar dos enfoques opuestos:  
  
- Construcción funcional usando un enfoque declarativo.  
  
- Modificación del árbol XML en memoria usando código de procedimiento.  
  
 LINQ to XML admite ambos enfoques.  
  
 Cuando se utiliza el enfoque funcional, se escriben transformaciones que toman los documentos de origen y generan documentos de resultados completamente nuevos con la forma que se desee.  
  
 Cuando se modifica un árbol XML, se escribe código que atraviese los nodos de un árbol XML y navegue por ellos en memoria para insertar, eliminar y modificar nodos según sea necesario.  
  
 Puede usar LINQ to XML con cualquier enfoque. Se usan las mismas clases y, en algunos casos, los mismos métodos. No obstante, la estructura y los objetivos de los dos enfoques son muy diferentes. Por ejemplo, en situaciones diferentes, uno u otro enfoque tendrá a menudo un rendimiento mejor y usará más o menos memoria. Asimismo, uno u otro enfoque será más fácil de escribir y proporcionará código más fácil de mantener.  
  
 Para obtener una comparación de los dos enfoques, vea [Diferencias entre la modificación del árbol XML en memoria y la construcción funcional (LINQ to XML) (C#)](./in-memory-xml-tree-modification-vs-functional-construction-linq-to-xml.md).  
  
 Para obtener un tutorial sobre la escritura de transformaciones funcionales, vea [Pure Functional Transformations of XML (C#) (Transformaciones funcionales puras de XML (C#))](./introduction-to-pure-functional-transformations.md).  
  
## <a name="see-also"></a>Vea también

- [Información general sobre la programación de LINQ to XML (C#)](./linq-to-xml-overview.md)
