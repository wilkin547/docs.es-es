---
title: Controlar excepciones en expresiones de consulta
description: 'Cómo: Controlar excepciones en expresiones de consulta'
ms.date: 12/1/2016
ms.assetid: 2bf0c397-13fb-4f68-bc2b-531c6c88a167
ms.openlocfilehash: 691373fabeb3934ecc454cbc3b36a5f7bf477bee
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33284856"
---
# <a name="handle-exceptions-in-query-expressions"></a>Controlar excepciones en expresiones de consulta

Es posible llamar a cualquier método en el contexto de una expresión de consulta. Pero se recomienda evitar llamar a cualquier método en una expresión de consulta que pueda crear un efecto secundario, como modificar el contenido del origen de datos o producir una excepción. En este ejemplo se muestra cómo evitar que se produzcan excepciones al llamar a métodos en una expresión de consulta sin infringir las directrices generales de .NET Framework sobre el control de excepciones. Esas directrices indican que es aceptable detectar una excepción concreta al comprender por qué se producirá en un contexto determinado. Para obtener más información, vea [Procedimientos recomendados para excepciones](../../standard/exceptions/best-practices-for-exceptions.md).  
  
 En el último ejemplo se muestra cómo controlar los casos en los que se debe producir una excepción durante la ejecución de una consulta.  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se muestra cómo mover código de control de excepciones fuera de una expresión de consulta. Esto solo es posible cuando el método no depende de ninguna variable local de la consulta.  
  
 [!code-csharp[csProgGuideLINQ#10](../../../samples/snippets/csharp/concepts/linq/how-to-handle-exceptions-in-query-expressions_1.cs)]  
  
## <a name="example"></a>Ejemplo 

 En algunos casos, la mejor respuesta a una excepción que se produce dentro de una consulta podría ser detener la ejecución de la consulta inmediatamente. En el ejemplo siguiente se muestra cómo controlar las excepciones que pueden producirse desde el cuerpo de una consulta. Supongamos que `SomeMethodThatMightThrow` puede producir una excepción que requiere que se detenga la ejecución de la consulta.  
  
 Tenga en cuenta que el bloque `try` encierra el bucle `foreach` y no la propia consulta. Esto es porque el bucle `foreach` es el punto en el que se ejecuta realmente la consulta. Para obtener más información, vea [Introduction to LINQ queries](../programming-guide/concepts/linq/introduction-to-linq-queries.md) (Introducción a las consultas LINQ).  
  
 [!code-csharp[csProgGuideLINQ#12](../../../samples/snippets/csharp/concepts/linq/how-to-handle-exceptions-in-query-expressions_2.cs)]  
  

## <a name="see-also"></a>Vea también  
 [Expresiones de consulta LINQ](index.md)
