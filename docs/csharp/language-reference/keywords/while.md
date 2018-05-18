---
title: while (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- while_CSharpKeyword
- while
helpviewer_keywords:
- while keyword [C#]
ms.assetid: 72a0765c-6852-4aca-b327-4a11cb7f5c59
ms.openlocfilehash: 23c5ca3bb7dc401a894a6c3918fbaec9a9306153
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="while-c-reference"></a>while (Referencia de C#)
La instrucción `while` ejecuta una instrucción o un bloque de instrucciones hasta que una expresión especificada se evalúa como `false`.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csrefKeywordsIteration#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_1.cs)]  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[csrefKeywordsIteration#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_2.cs)]  
  
## <a name="example"></a>Ejemplo  
 Como la comprobación de la expresión `while` tiene lugar antes de la ejecución del bucle, un bucle `while` se ejecuta cero o varias veces. Esto es diferente del bucle [do](../../../csharp/language-reference/keywords/do.md) que se ejecuta una o varias veces.  
  
 Un bucle `while` se puede terminar cuando una instrucción [break](../../../csharp/language-reference/keywords/break.md), [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md) o [throw](../../../csharp/language-reference/keywords/throw.md) transfiere el control fuera del bucle. Para pasar el control a la siguiente iteración sin salir del bucle, use la instrucción [continue](../../../csharp/language-reference/keywords/continue.md). Observe la diferencia en los resultados de los tres ejemplos anteriores, con relación a dónde se incrementa `int n`. En el ejemplo siguiente no se genera ningún resultado.  
  
 [!code-csharp[csrefKeywordsIteration#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_3.cs)]  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)  
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)  
 [while (Instrucción) (C++)](/cpp/cpp/while-statement-cpp)  
 [Instrucciones de iteración](../../../csharp/language-reference/keywords/iteration-statements.md)
