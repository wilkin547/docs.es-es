---
title: do (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- do_CSharpKeyword
- do
dev_langs:
- CSharp
helpviewer_keywords:
- do keyword [C#]
ms.assetid: 50725f79-9ba6-4898-aa78-6e331568a1bb
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 58a9361c440bc1b17c5ab929ff7b45ba71ce50a4
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="do-c-reference"></a>do (Referencia de C#)
La instrucción `do` ejecuta una instrucción o un bloque de instrucciones repetidamente hasta que una expresión especificada se evalúa como `false`. El cuerpo del bucle debe incluirse entre llaves, `{}`, a menos que conste de una sola instrucción. En ese caso, las llaves son opcionales.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, las instrucciones de bucle `do-while` se ejecutan siempre que la variable `x` sea menor que 5.  
  
 [!code-cs[csrefKeywordsIteration#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/do_1.cs)]  
  
 A diferencia de la instrucción [while](../../../csharp/language-reference/keywords/while.md), un bucle `do-while` se ejecuta una vez antes de que se evalúe la expresión condicional.  
  
 En cualquier punto del bloque `do-while`, puede salir del bucle mediante la instrucción [break](../../../csharp/language-reference/keywords/break.md). Puede ir directamente a la instrucción de evaluación de expresiones `while` mediante la instrucción [continue](../../../csharp/language-reference/keywords/continue.md). Si la expresión `while` se evalúa como true, la ejecución continúa en la primera instrucción del bucle. Si la expresión se evalúa como false, la ejecución continúa en la primera instrucción después del bucle `do-while`.  
  
 También se puede salir de un bucle `do-while` mediante las instrucciones [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md) o [throw](../../../csharp/language-reference/keywords/throw.md).  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)   
 [Instrucción do-while (C++)](/cpp/cpp/do-while-statement-cpp)   
 [Instrucciones de iteración](../../../csharp/language-reference/keywords/iteration-statements.md)

