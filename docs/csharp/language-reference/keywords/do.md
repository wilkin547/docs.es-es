---
title: do (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- do_CSharpKeyword
- do
helpviewer_keywords:
- do keyword [C#]
ms.assetid: 50725f79-9ba6-4898-aa78-6e331568a1bb
ms.openlocfilehash: 5599f079e29fd094c4d6a6a75afba89fb562a166
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="do-c-reference"></a>do (Referencia de C#)
La instrucción `do` ejecuta una instrucción o un bloque de instrucciones repetidamente hasta que una expresión especificada se evalúa como `false`. El cuerpo del bucle debe incluirse entre llaves, `{}`, a menos que conste de una sola instrucción. En ese caso, las llaves son opcionales.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, las instrucciones de bucle `do-while` se ejecutan siempre que la variable `x` sea menor que 5.  
  
 [!code-csharp[csrefKeywordsIteration#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/do_1.cs)]  
  
 A diferencia de la instrucción [while](../../../csharp/language-reference/keywords/while.md), un bucle `do-while` se ejecuta una vez antes de que se evalúe la expresión condicional.  
  
 En cualquier punto del bloque `do-while`, puede salir del bucle mediante la instrucción [break](../../../csharp/language-reference/keywords/break.md). Puede ir directamente a la instrucción de evaluación de expresiones `while` mediante la instrucción [continue](../../../csharp/language-reference/keywords/continue.md). Si la expresión `while` se evalúa como true, la ejecución continúa en la primera instrucción del bucle. Si la expresión se evalúa como false, la ejecución continúa en la primera instrucción después del bucle `do-while`.  
  
 También se puede salir de un bucle `do-while` mediante las instrucciones [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md) o [throw](../../../csharp/language-reference/keywords/throw.md).  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)  
 [do-while (Instrucción) (C++)](/cpp/cpp/do-while-statement-cpp)  
 [Instrucciones de iteración](../../../csharp/language-reference/keywords/iteration-statements.md)
