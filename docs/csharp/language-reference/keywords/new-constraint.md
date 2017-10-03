---
title: "Restricción new (Referencia de C#)"
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 762941794184605f90443ed8f36c88ecfa50aa84
ms.contentlocale: es-es
ms.lasthandoff: 09/25/2017

---
# <a name="new-constraint-c-reference"></a>Restricción new (Referencia de C#)
La restricción `new` especifica que ningún tipo de argumento en una declaración de clase genérica debe tener un constructor sin parámetros público. Para usar la restricción new, el tipo no puede ser abstracto.  
  
## <a name="example"></a>Ejemplo  
 Aplique la restricción `new` a un tipo de parámetro cuando la clase genérica cree otras instancias del tipo, tal y como se muestra en el ejemplo siguiente:  
  
 [!code-cs[csrefKeywordsOperator#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-constraint_1.cs)]  
  
## <a name="example"></a>Ejemplo  
 Cuando use la restricción `new()` con otras restricciones, se debe especificar en último lugar:  
  
 [!code-cs[csrefKeywordsOperator#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-constraint_2.cs)]  
  
 Para obtener más información, vea [Restricciones de tipos de parámetros](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Collections.Generic>   
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Palabras clave de C#](../../../csharp/language-reference/keywords/index.md)   
 [Operator Keywords](../../../csharp/language-reference/keywords/operator-keywords.md)  (Palabras clave de operador [Referencia de C#])  
 [Genéricos](../../../csharp/programming-guide/generics/index.md)

