---
title: 'Cómo: Ejecutar código de limpieza mediante finally (Guía de programación de C#)'
ms.date: 07/20/2015
helpviewer_keywords:
- try/finally blocks [C#]
- exceptions [C#], try/finally block
- exception handling [C#], try/finally block
ms.assetid: 1b1e5aef-3f32-4a88-9d39-b5fffb33bdaf
ms.openlocfilehash: 948281af45d04714ed6fc308b60341e87abeb830
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-execute-cleanup-code-using-finally-c-programming-guide"></a>Cómo: Ejecutar código de limpieza mediante finally (Guía de programación de C#)
El propósito de una instrucción `finally` es asegurarse de que la limpieza necesaria de los objetos, por lo general objetos que contienen recursos externos, se produzca inmediatamente, incluso si se produce una excepción. Un ejemplo de esta limpieza es llamar a <xref:System.IO.Stream.Close%2A> en un <xref:System.IO.FileStream> inmediatamente después de su uso en lugar de esperar a que el objeto sea recolectado por el Common Language Runtime, de esta forma:  
  
 [!code-csharp[csProgGuideExceptions#16](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/how-to-execute-cleanup-code-using-finally_1.cs)]  
  
## <a name="example"></a>Ejemplo  
 Para activar el código anterior en una instrucción `try-catch-finally`, el código de limpieza se separa del código de trabajo, de esta forma.  
  
 [!code-csharp[csProgGuideExceptions#17](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/how-to-execute-cleanup-code-using-finally_2.cs)]  
  
 Dado que una excepción puede producirse en cualquier momento dentro del bloque `try` antes de la llamada a `OpenWrite()`, o que podría producirse un error en la propia llamada a `OpenWrite()`, no se garantiza que el archivo está abierto cuando se intenta cerrar. El bloque `finally` agrega una comprobación para asegurarse de que el objeto <xref:System.IO.FileStream> no es `null` antes de que pueda llamar al método <xref:System.IO.Stream.Close%2A>. Sin la comprobación `null`, el bloque `finally` podría iniciar su propia excepción <xref:System.NullReferenceException>, pero debería evitarse generar excepciones en bloques `finally` si es posible.  
  
 Una conexión de base de datos es otra buena candidata para cerrarse en un bloque `finally`. Dado que a veces se limita el número de conexiones permitido en un servidor de base de datos, se deben cerrar las conexiones de base de datos tan pronto como sea posible. Si se produce una excepción antes de poder cerrar la conexión, se trata de otro caso en el que usar el bloque `finally` es mejor que esperar a la recolección de elementos no utilizados.  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Excepciones y control de excepciones](../../../csharp/programming-guide/exceptions/index.md)  
 [Control de excepciones](../../../csharp/programming-guide/exceptions/exception-handling.md)  
 [using (instrucción)](../../../csharp/language-reference/keywords/using-statement.md)  
 [try-catch](../../../csharp/language-reference/keywords/try-catch.md)  
 [try-finally](../../../csharp/language-reference/keywords/try-finally.md)  
 [try-catch-finally](../../../csharp/language-reference/keywords/try-catch-finally.md)
