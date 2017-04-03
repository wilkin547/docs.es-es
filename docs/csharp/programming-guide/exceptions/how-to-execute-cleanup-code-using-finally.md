---
title: "Cómo: Ejecutar código de limpieza mediante finally (Guía de programación de C#) | Microsoft Docs"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- try/finally blocks [C#]
- exceptions [C#], try/finally block
- exception handling [C#], try/finally block
ms.assetid: 1b1e5aef-3f32-4a88-9d39-b5fffb33bdaf
caps.latest.revision: 21
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: b9c22ca8ee9c83e6f1808520530c6d1912d8f4f1
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-execute-cleanup-code-using-finally-c-programming-guide"></a>Cómo: Ejecutar código de limpieza mediante finally (Guía de programación de C#)
El propósito de una instrucción `finally` es asegurarse de que la limpieza necesaria de los objetos, por lo general objetos que contienen recursos externos, se produzca inmediatamente, incluso si se produce una excepción. Un ejemplo de esta limpieza es llamar a <xref:System.IO.Stream.Close%2A> en un <xref:System.IO.FileStream> inmediatamente después de su uso en lugar de esperar a que el objeto sea recolectado por el Common Language Runtime, de esta forma:  
  
 [!code-cs[csProgGuideExceptions#16](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/how-to-execute-cleanup-code-using-finally_1.cs)]  
  
## <a name="example"></a>Ejemplo  
 Para activar el código anterior en una instrucción `try-catch-finally`, el código de limpieza se separa del código de trabajo, de esta forma.  
  
 [!code-cs[csProgGuideExceptions#17](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/how-to-execute-cleanup-code-using-finally_2.cs)]  
  
 Dado que una excepción puede producirse en cualquier momento dentro del bloque `try` antes de la llamada a `OpenWrite()`, o que podría producirse un error en la propia llamada a `OpenWrite()`, no se garantiza que el archivo está abierto cuando se intenta cerrar. El bloque `finally` agrega una comprobación para asegurarse de que el objeto <xref:System.IO.FileStream> no es `null` antes de llamar al método <xref:System.IO.Stream.Close%2A>. Sin la comprobación `null`, el bloque `finally` podría iniciar su propia excepción <xref:System.NullReferenceException>, pero debería evitarse generar excepciones en bloques `finally` si es posible.  
  
 Una conexión de base de datos es otra buena candidata para cerrarse en un bloque `finally`. Dado que a veces se limita el número de conexiones permitido en un servidor de base de datos, se deben cerrar las conexiones de base de datos tan pronto como sea posible. Si se produce una excepción antes de poder cerrar la conexión, se trata de otro caso en el que usar el bloque `finally` es mejor que esperar a la recolección de elementos no utilizados.  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Excepciones y control de excepciones](../../../csharp/programming-guide/exceptions/index.md)   
 [Control de excepciones](../../../csharp/programming-guide/exceptions/exception-handling.md)   
 [using (Instrucción)](../../../csharp/language-reference/keywords/using-statement.md)   
 [try-catch](../../../csharp/language-reference/keywords/try-catch.md)   
 [try-finally](../../../csharp/language-reference/keywords/try-finally.md)   
 [try-catch-finally](../../../csharp/language-reference/keywords/try-catch-finally.md)
