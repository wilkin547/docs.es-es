---
title: Controlar excepciones en expresiones de consulta
description: "Cómo: Controlar excepciones en expresiones de consulta"
keywords: .NET, .NET Core, C#
author: stevehoag
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 2bf0c397-13fb-4f68-bc2b-531c6c88a167
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: da0ed7ee7f7653e23140732a785ee73b16a150a5
ms.lasthandoff: 03/13/2017

---
# <a name="handle-exceptions-in-query-expressions"></a>Controlar excepciones en expresiones de consulta

Es posible llamar a cualquier método en el contexto de una expresión de consulta. Pero se recomienda evitar llamar a cualquier método en una expresión de consulta que pueda crear un efecto secundario, como modificar el contenido del origen de datos o producir una excepción. En este ejemplo se muestra cómo evitar que se produzcan excepciones al llamar a métodos en una expresión de consulta sin infringir las directrices generales de .NET Framework sobre el control de excepciones. Esas directrices indican que es aceptable detectar una excepción concreta al comprender por qué se producirá en un contexto determinado. Para obtener más información, vea [Procedimientos recomendados para excepciones](http://msdn.microsoft.com/library/f06da765-235b-427a-bfb6-47cd219af539).  
  
 En el último ejemplo se muestra cómo controlar los casos en los que se debe producir una excepción durante la ejecución de una consulta.  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se muestra cómo mover código de control de excepciones fuera de una expresión de consulta. Esto solo es posible cuando el método no depende de ninguna variable local de la consulta.  
  
 [!code-cs[csProgGuideLINQ#10](../../../samples/snippets/csharp/concepts/linq/how-to-handle-exceptions-in-query-expressions_1.cs)]  
  
## <a name="example"></a>Ejemplo 

 En algunos casos, la mejor respuesta a una excepción que se produce dentro de una consulta podría ser detener la ejecución de la consulta inmediatamente. En el ejemplo siguiente se muestra cómo controlar las excepciones que pueden producirse desde el cuerpo de una consulta. Supongamos que `SomeMethodThatMightThrow` puede producir una excepción que requiere que se detenga la ejecución de la consulta.  
  
 Tenga en cuenta que el bloque `try` encierra el bucle `foreach` y no la propia consulta. Esto es porque el bucle `foreach` es el punto en el que se ejecuta realmente la consulta. Para obtener más información, vea [Introduction to LINQ queries](../programming-guide/concepts/linq/introduction-to-linq-queries.md) (Introducción a las consultas LINQ).  
  
 [!code-cs[csProgGuideLINQ#12](../../../samples/snippets/csharp/concepts/linq/how-to-handle-exceptions-in-query-expressions_2.cs)]  
  

## <a name="see-also"></a>Vea también  
 [Expresiones de consulta LINQ](index.md)
