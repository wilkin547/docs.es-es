---
title: "Ejecución aplazada y evaluación diferida en LINQ to XML (C#) | Microsoft Docs"
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
ms.assetid: 8683d1b4-b7ec-407b-be12-906ebe958a09
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 1f9d60242c75b996d25997b2adc83ccafcc538de
ms.lasthandoff: 03/13/2017


---
# <a name="deferred-execution-and-lazy-evaluation-in-linq-to-xml-c"></a>Ejecución aplazada y evaluación diferida en LINQ to XML (C#)
Las operaciones de consulta y de eje a menudo se implementan para usar la ejecución aplazada. Este tema describe los requisitos y las ventajas de la ejecución aplazada, y algunas consideraciones acerca de la implementación.  
  
## <a name="deferred-execution"></a>Ejecución aplazada  
 La ejecución aplazada significa que la evaluación de una expresión se retrasa hasta que su valor *realizado* sea realmente necesario. La ejecución aplazada puede mejorar considerablemente el rendimiento cuando deba manipular grandes recolecciones de datos, sobre todo en programas que contengan una serie de manipulaciones o consultas encadenadas. En el mejor de los casos, la ejecución aplazada solo habilita una iteración a través de la recolección de origen.  
  
 Las tecnologías LINQ usan intensivamente la ejecución aplazada tanto en los miembros de las clases <xref:System.Linq?displayProperty=fullName> principales como en los métodos de extensión de los diversos espacios de nombres LINQ, por ejemplo, <xref:System.Xml.Linq.Extensions?displayProperty=fullName>.  
  
 El lenguaje C# admite directamente la ejecución aplazada mediante la palabra clave [yield](../../../../csharp/language-reference/keywords/yield.md) (en forma de instrucción `yield-return`) cuando se usa en un bloque de iteradores. Este tipo de iterador debe devolver una colección de tipo <xref:System.Collections.IEnumerator> o <xref:System.Collections.Generic.IEnumerator%601> (o un tipo derivado).  
  
## <a name="eager-vs-lazy-evaluation"></a>Diferencias entre la evaluación diligente y la evaluación diferida  
 Al escribir un método que implemente una ejecución aplazada, también debe decidir si implementa el método con la evaluación diferida o la evaluación diligente.  
  
-   En la *evaluación diferida*, un único elemento de la colección de origen se procesa durante cada llamada al iterador. Esta es la forma habitual en la que se implementan los iteradores.  
  
-   En la *evaluación diligente*, la primera llamada al iterador hará que se procese toda la colección. Es posible que también se requiera una copia temporal de la colección de origen. Por ejemplo, el método <xref:System.Linq.Enumerable.OrderBy%2A> debe ordenar toda la colección antes de devolver el primer elemento.  
  
 Normalmente, la evaluación diferida presenta un mejor rendimiento, ya que distribuye el procesamiento de sobrecarga de forma equitativa durante la evaluación de la colección y minimiza el uso de los datos temporales. Obviamente, para algunas operaciones, no existe otra alternativa que materializar resultados intermedios.  
  
## <a name="next-steps"></a>Pasos siguientes  
 El siguiente tema de este tutorial ilustra la ejecución aplazada:  
  
-   [Ejemplo de ejecución diferida (C#)](../../../../csharp/programming-guide/concepts/linq/deferred-execution-example.md)  
  
## <a name="see-also"></a>Vea también  
 [Tutorial: Encadenar consultas juntas (C#)](../../../../csharp/programming-guide/concepts/linq/tutorial-chaining-queries-together.md)   
 [Conceptos y terminología (transformación funcional) (C#)](../../../../csharp/programming-guide/concepts/linq/concepts-and-terminology-functional-transformation.md)   
 [Operaciones de agregación (C#)](../../../../csharp/programming-guide/concepts/linq/aggregation-operations.md)   
 [yield](../../../../csharp/language-reference/keywords/yield.md)
