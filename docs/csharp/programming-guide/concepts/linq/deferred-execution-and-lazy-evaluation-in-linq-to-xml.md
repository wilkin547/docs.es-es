---
title: "Ejecución aplazada y evaluación diferida en LINQ to XML (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 8683d1b4-b7ec-407b-be12-906ebe958a09
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 847d8f830c26f54521664accc4bf569f822f255a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="deferred-execution-and-lazy-evaluation-in-linq-to-xml-c"></a>Ejecución aplazada y evaluación diferida en LINQ to XML (C#)
Las operaciones de consulta y de eje a menudo se implementan para usar la ejecución aplazada. Este tema describe los requisitos y las ventajas de la ejecución aplazada, y algunas consideraciones acerca de la implementación.  
  
## <a name="deferred-execution"></a>Ejecución aplazada  
 La ejecución aplazada significa que la evaluación de una expresión se retrasa hasta que su valor *realizado* sea realmente necesario. La ejecución aplazada puede mejorar considerablemente el rendimiento cuando deba manipular grandes recolecciones de datos, sobre todo en programas que contengan una serie de manipulaciones o consultas encadenadas. En el mejor de los casos, la ejecución aplazada solo habilita una iteración a través de la recolección de origen.  
  
 Las tecnologías LINQ usan intensivamente la ejecución aplazada tanto en los miembros de las clases <xref:System.Linq?displayProperty=nameWithType> principales como en los métodos de extensión de los diversos espacios de nombres LINQ, por ejemplo, <xref:System.Xml.Linq.Extensions?displayProperty=nameWithType>.  
  
 El lenguaje C# admite directamente la ejecución aplazada mediante la palabra clave [yield](../../../../csharp/language-reference/keywords/yield.md) (en forma de instrucción `yield-return`) cuando se usa en un bloque de iteradores. Este tipo de iterador debe devolver una colección de tipo <xref:System.Collections.IEnumerator> o <xref:System.Collections.Generic.IEnumerator%601> (o bien un tipo derivado).  
  
## <a name="eager-vs-lazy-evaluation"></a>Diferencias entre la evaluación diligente y la evaluación diferida  
 Al escribir un método que implemente una ejecución aplazada, también debe decidir si implementa el método con la evaluación diferida o la evaluación diligente.  
  
-   En la *evaluación diferida*, un único elemento de la colección de origen se procesa durante cada llamada al iterador. Esta es la forma habitual en la que se implementan los iteradores.  
  
-   En la *evaluación diligente*, la primera llamada al iterador hará que se procese toda la colección. Es posible que también se requiera una copia temporal de la colección de origen. Por ejemplo, el método <xref:System.Linq.Enumerable.OrderBy%2A> debe ordenar toda la colección antes de devolver el primer elemento.  
  
 Normalmente, la evaluación diferida presenta un mejor rendimiento, ya que distribuye el procesamiento de sobrecarga de forma equitativa durante la evaluación de la colección y minimiza el uso de los datos temporales. Obviamente, para algunas operaciones, no existe otra alternativa que materializar resultados intermedios.  
  
## <a name="next-steps"></a>Pasos siguientes  
 El siguiente tema de este tutorial ilustra la ejecución aplazada:  
  
-   [Ejemplo de ejecución diferida (C#)](../../../../csharp/programming-guide/concepts/linq/deferred-execution-example.md)  
  
## <a name="see-also"></a>Vea también  
 [Tutorial: encadenar cadenas juntas (C#)](../../../../csharp/programming-guide/concepts/linq/tutorial-chaining-queries-together.md)  
 [Conceptos y terminología (transformación funcional) (C#)](../../../../csharp/programming-guide/concepts/linq/concepts-and-terminology-functional-transformation.md)  
 [Aggregation Operations (C#)](../../../../csharp/programming-guide/concepts/linq/aggregation-operations.md) (Operaciones de agregación [C#])  
 [yield](../../../../csharp/language-reference/keywords/yield.md)
