---
title: try-finally (Referencia de C#) | Microsoft Docs
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- finally
- finally_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- finally keyword [C#]
- try-finally statement [C#]
ms.assetid: c27623fb-7261-4464-862c-7a369d3c8f0a
caps.latest.revision: 25
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
ms.openlocfilehash: 3f7618aa6d4ae3535b2b6cb562349650b3eba1ed
ms.lasthandoff: 03/13/2017

---
# <a name="try-finally-c-reference"></a>try-finally (Referencia de C#)
Mediante el uso de un bloque `finally`, puede limpiar todos los recursos asignados en un bloque [try](../../../csharp/language-reference/keywords/try-catch.md) y ejecutar código incluso si se produce una excepción en el bloque `try`. Normalmente, las instrucciones de un bloque `finally` se ejecutan cuando el control abandona una instrucción `try`. La transferencia de control se puede producir como resultado de la ejecución normal, de la ejecución de una instrucción `break`, `continue`, `goto` o `return`, o de la propagación de una excepción fuera de la instrucción `try`.  
  
 Dentro de una excepción controlada, se garantiza la ejecución del bloque `finally` asociado. Pero en el caso de una excepción no controlada, la ejecución del bloque `finally` depende de la manera en que se desencadene la operación de desenredo de la excepción. Esto, a su vez, depende de cómo esté configurado el equipo. Para obtener más información vea [Unhandled Exception Processing in the CLR](http://go.microsoft.com/fwlink/?LinkId=128371) (Procesamiento de excepciones no controladas en CLR).  
  
 Normalmente, cuando una excepción no controlada finaliza una aplicación, no es importante si el bloque `finally` se ejecuta o no. Pero si tiene instrucciones en un bloque `finally` que debe ejecutarse incluso en esa situación, una solución es agregar un bloque `catch` a la instrucción `try`-`finally`. Como alternativa, puede capturar la excepción que se podría producir en el bloque `try` de una instrucción `try`-`finally` más arriba en la pila de llamadas. Es decir, puede capturar la excepción en el método que llama al método que contiene la instrucción `try`-`finally`, en el método que llama a ese método o en cualquier método en la pila de llamadas. Si no se captura la excepción, la ejecución del bloque `finally` depende de si el sistema operativo decide desencadenar una operación de desenredo de la excepción.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, una instrucción de conversión no válida provoca una excepción `System.InvalidCastException`. Se trata de una excepción no controlada.  
  
 [!code-cs[csrefKeywordsExceptions#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-finally_1.cs)]  
  
 En el ejemplo siguiente, se captura una excepción del método `TryCast` en un método más arriba en la pila de llamadas.  
  
 [!code-cs[csrefKeywordsExceptions#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/try-finally_2.cs)]  
  
 Para obtener más información sobre `finally`, vea [try-catch-finally](../../../csharp/language-reference/keywords/try-catch-finally.md).  
  
 C# también contiene la [instrucción using](../../../csharp/language-reference/keywords/using-statement.md), que proporciona una funcionalidad similar para objetos <xref:System.IDisposable> en una sintaxis adecuada.  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)   
 [Instrucciones try, throw y catch (C++)](https://docs.microsoft.com/cpp/cpp/try-throw-and-catch-statements-cpp)   
 [Instrucciones para el control de excepciones](../../../csharp/language-reference/keywords/exception-handling-statements.md)   
 [throw](../../../csharp/language-reference/keywords/throw.md)   
 [try-catch](../../../csharp/language-reference/keywords/try-catch.md)   
 [Cómo: Iniciar excepciones explícitamente](https://msdn.microsoft.com/library/xhcbs8fz)
