---
title: continue (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- continue_CSharpKeyword
- continue
dev_langs:
- CSharp
helpviewer_keywords:
- continue keyword [C#]
ms.assetid: 8a5ac96f-f98a-4519-b32d-345847ed7be0
caps.latest.revision: 20
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 4a0dcedb32b153c31ec5ed799f66062463307db9
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="continue-c-reference"></a>continue (Referencia de C#)
La instrucción `continue` transfiere el control a la siguiente iteración de la instrucción envolvente [while](../../../csharp/language-reference/keywords/while.md), [do](../../../csharp/language-reference/keywords/do.md), [for](../../../csharp/language-reference/keywords/for.md) o [foreach](../../../csharp/language-reference/keywords/foreach-in.md) en la que aparece.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se inicializa un contador para contar del 1 al 10. Si se usa la instrucción `continue` junto con la expresión `(i < 9)`, se omiten las instrucciones comprendidas entre `continue` y el final del cuerpo de `for`.  
  
 [!code-cs[csrefKeywordsJump#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/continue_1.cs)]  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)   
 [break (Instrucción)](/cpp/cpp/break-statement-cpp)   
 [Instrucciones de salto](../../../csharp/language-reference/keywords/jump-statements.md)

