---
title: while (Referencia de C#) | Microsoft Docs
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- while_CSharpKeyword
- while
dev_langs:
- CSharp
helpviewer_keywords:
- while keyword [C#]
ms.assetid: 72a0765c-6852-4aca-b327-4a11cb7f5c59
caps.latest.revision: 22
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
ms.translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 744980f2dd55806062901d874a3137f5936e0888
ms.contentlocale: es-es
ms.lasthandoff: 03/13/2017

---
# <a name="while-c-reference"></a>while (Referencia de C#)
La instrucción `while` ejecuta una instrucción o un bloque de instrucciones hasta que una expresión especificada se evalúa como `false`.  
  
## <a name="example"></a>Ejemplo  
 [!code-cs[csrefKeywordsIteration#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_1.cs)]  
  
## <a name="example"></a>Ejemplo  
 [!code-cs[csrefKeywordsIteration#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_2.cs)]  
  
## <a name="example"></a>Ejemplo  
 Como la comprobación de la expresión `while` tiene lugar antes de la ejecución del bucle, un bucle `while` se ejecuta cero o varias veces. Esto es diferente del bucle [do](../../../csharp/language-reference/keywords/do.md) que se ejecuta una o varias veces.  
  
 Un bucle `while` se puede terminar cuando una instrucción [break](../../../csharp/language-reference/keywords/break.md), [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md) o [throw](../../../csharp/language-reference/keywords/throw.md) transfiere el control fuera del bucle. Para pasar el control a la siguiente iteración sin salir del bucle, use la instrucción [continue](../../../csharp/language-reference/keywords/continue.md). Observe la diferencia en los resultados de los tres ejemplos anteriores, con relación a dónde se incrementa `int n`. En el ejemplo siguiente no se genera ningún resultado.  
  
 [!code-cs[csrefKeywordsIteration#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_3.cs)]  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)   
 [while (Instrucción) (C++)](https://docs.microsoft.com/cpp/cpp/while-statement-cpp)   
 [Instrucciones de iteración](../../../csharp/language-reference/keywords/iteration-statements.md)
