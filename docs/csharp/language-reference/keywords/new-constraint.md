---
title: "new (Restricción, Referencia de C#) | Microsoft Docs"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- new constraint keyword [C#]
ms.assetid: 58850b64-cb97-4136-be50-1f3bc7fc1da9
caps.latest.revision: 20
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
ms.openlocfilehash: 10f3693678f5a3eeaa335739bb383e204c80b375
ms.lasthandoff: 03/13/2017

---
# <a name="new-constraint-c-reference"></a>Restricción new (Referencia de C#)
La restricción `new` especifica que ningún tipo de argumento en una declaración de clase genérica debe tener un constructor sin parámetros público. Para usar la restricción new, el tipo no puede ser abstracto.  
  
## <a name="example"></a>Ejemplo  
 Aplique la restricción `new` a un tipo de parámetro cuando la clase genérica cree otras instancias del tipo, tal y como se muestra en el ejemplo siguiente:  
  
 [!code-cs[csrefKeywordsOperator#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-constraint_1.cs)]  
  
## <a name="example"></a>Ejemplo  
 Cuando use la restricción `new()` con otras restricciones, se debe especificar en último lugar:  
  
 [!code-cs[csrefKeywordsOperator#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-constraint_2.cs)]  
  
 Para obtener más información, vea [Constraints on Type Parameters](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md) (Restricciones de tipos de parámetros [Guía de programación de C#]).  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Collections.Generic>   
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)   
 [Operator Keywords](../../../csharp/language-reference/keywords/operator-keywords.md)  (Palabras clave de operador [Referencia de C#])  
 [Genéricos](../../../csharp/programming-guide/generics/index.md)
