---
title: Ejecución aplazada y evaluación diferida en LINQ to XML (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 31998eed-b95e-47fb-a865-9de1f337d1fb
ms.openlocfilehash: b5c3e2a484aa16df22742ddf77d6438ec2a699bb
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58839044"
---
# <a name="deferred-execution-and-lazy-evaluation-in-linq-to-xml-visual-basic"></a>Ejecución aplazada y evaluación diferida en LINQ to XML (Visual Basic)
Las operaciones de consulta y de eje a menudo se implementan para usar la ejecución aplazada. Este tema describe los requisitos y las ventajas de la ejecución aplazada, y algunas consideraciones acerca de la implementación.  
  
## <a name="deferred-execution"></a>Ejecución aplazada  
 La ejecución aplazada significa que la evaluación de una expresión se retrasa hasta que su valor *realizado* sea realmente necesario. La ejecución aplazada puede mejorar considerablemente el rendimiento cuando deba manipular grandes recolecciones de datos, sobre todo en programas que contengan una serie de manipulaciones o consultas encadenadas. En el mejor de los casos, la ejecución aplazada solo habilita una iteración a través de la recolección de origen.  
  
 Las tecnologías LINQ usan intensivamente la ejecución aplazada tanto en los miembros de las clases <xref:System.Linq?displayProperty=nameWithType> principales como en los métodos de extensión de los diversos espacios de nombres LINQ, por ejemplo, <xref:System.Xml.Linq.Extensions?displayProperty=nameWithType>.  
  
## <a name="eager-vs-lazy-evaluation"></a>Diferencias entre la evaluación diligente y la evaluación diferida  
 Al escribir un método que implemente una ejecución aplazada, también debe decidir si implementa el método con la evaluación diferida o la evaluación diligente.  
  
-   En la *evaluación diferida*, un único elemento de la colección de origen se procesa durante cada llamada al iterador. Esta es la forma habitual en la que se implementan los iteradores.  
  
-   En la *evaluación diligente*, la primera llamada al iterador hará que se procese toda la colección. Es posible que también se requiera una copia temporal de la colección de origen. Por ejemplo, el método <xref:System.Linq.Enumerable.OrderBy%2A> debe ordenar toda la colección antes de devolver el primer elemento.  
  
 Normalmente, la evaluación diferida presenta un mejor rendimiento, ya que distribuye el procesamiento de sobrecarga de forma equitativa durante la evaluación de la colección y minimiza el uso de los datos temporales. Obviamente, para algunas operaciones, no existe otra alternativa que materializar resultados intermedios.  
  
## <a name="next-steps"></a>Pasos siguientes  
 El siguiente tema de este tutorial ilustra la ejecución aplazada:  
  
-   [Ejemplo de ejecución diferida (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/deferred-execution-example.md)  
  
## <a name="see-also"></a>Vea también

- [Tutorial: Ejecución diferida (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/tutorial-deferred-execution.md)
- [Conceptos y terminología (transformación funcional) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/concepts-and-terminology-functional-transformation.md)
- [Operaciones de agregación (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/aggregation-operations.md)
