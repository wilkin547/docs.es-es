---
title: Operador &gt;&gt; (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '>>_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- '>> operator [C#]'
- right shift operator (>>) [C#]
ms.assetid: a07f8679-d318-4ef8-b38b-65903efb8056
caps.latest.revision: 15
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
ms.openlocfilehash: dd3f077e9bb491cefce7db7c015bde201f6f8207
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="gtgt-operator-c-reference"></a>Operador &gt;&gt; (Referencia de C#)
El operador de desplazamiento a la derecha (`>>`) desplaza su primer operando a la derecha el número de bits especificado por su segundo operando.  
  
## <a name="remarks"></a>Comentarios  
 Si el primer operando es [int](../../../csharp/language-reference/keywords/int.md) o [uint](../../../csharp/language-reference/keywords/uint.md) (cantidad de 32 bits), el valor de desplazamiento viene dado por los cinco bits de orden inferior del segundo operando (segundo operando y 0x1f).  
  
 Si el primer operando es [long](../../../csharp/language-reference/keywords/long.md) o [ulong](../../../csharp/language-reference/keywords/ulong.md) (cantidad de 64 bits), el valor de desplazamiento viene dado por los seis bits de orden inferior del segundo operando (segundo operando y 0x3f).  
  
 Si el primer operando es [int](../../../csharp/language-reference/keywords/int.md) o [long](../../../csharp/language-reference/keywords/long.md), el desplazamiento a la derecha es un desplazamiento aritmético (los bits vacíos de orden superior se establecen en el bit de signo). Si el primer operando es de tipo [uint](../../../csharp/language-reference/keywords/uint.md) o [ulong](../../../csharp/language-reference/keywords/ulong.md), el desplazamiento a la derecha es un desplazamiento lógico (los bits de orden superior se rellenan con ceros).  
  
 Los tipos definidos por el usuario pueden sobrecargar el operador `>>`; el tipo del primer operando debe ser el tipo definido por el usuario y el tipo del segundo operando debe ser [int](../../../csharp/language-reference/keywords/int.md). Para obtener más información, vea [operator (Referencia de C#)](../../../csharp/language-reference/keywords/operator.md). Cuando se sobrecarga un operador binario, el operador de asignación correspondiente, si lo hay, también se sobrecarga de modo implícito.  
  
## <a name="example"></a>Ejemplo  
 [!code-cs[csRefOperators#26](../../../csharp/language-reference/operators/codesnippet/CSharp/right-shift-operator_1.cs)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Operadores de C#](../../../csharp/language-reference/operators/index.md)

