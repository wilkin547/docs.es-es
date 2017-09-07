---
title: Operador &lt;&lt; (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- <<_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- left shift operator (<<) [C#]
- << operator [C#]
ms.assetid: a654eb56-1ff7-4bf3-9064-b631be0cdccc
caps.latest.revision: 18
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
ms.openlocfilehash: 4e6ad17232ec4eb087ca300342331af6a30789b1
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="ltlt-operator-c-reference"></a>Operador &lt;&lt; (Referencia de C#)
El operador de desplazamiento a la izquierda (`<<`) desplaza su primer operando a la izquierda el número de bits especificado por su segundo operando. El tipo del segundo operando debe ser [int](../../../csharp/language-reference/keywords/int.md) o un tipo que tiene una conversión numérica implícita predefinida en `int`.  
  
## <a name="remarks"></a>Comentarios  
 Si el primer operando es [int](../../../csharp/language-reference/keywords/int.md) o [uint](../../../csharp/language-reference/keywords/uint.md) (cantidad de 32 bits), el valor de desplazamiento viene dado por los cinco bits de orden inferior del segundo operando. Es decir, el recuento de desplazamiento real es de 0 a 31 bits.  
  
 Si el primer operando es [long](../../../csharp/language-reference/keywords/long.md) o [ulong](../../../csharp/language-reference/keywords/ulong.md) (cantidad de 64 bits), el valor de desplazamiento viene dado por los seis bits de orden inferior del segundo operando. Es decir, el recuento de desplazamiento real es de 0 a 63 bits.  
  
 Se descartan los bits de orden superior que no están dentro del intervalo del tipo del primer operando después del desplazamiento y se rellenan con ceros los bits vacíos de orden inferior. Las operaciones de desplazamiento nunca producen desbordamientos.  
  
 Los tipos definidos por el usuario pueden sobrecargar el operador `<<` (vea [operator](../../../csharp/language-reference/keywords/operator.md)); el tipo del primer operando debe ser el tipo definido por el usuario y el tipo del segundo operando debe ser `int`. Cuando se sobrecarga un operador binario, el operador de asignación correspondiente, si lo hay, también se sobrecarga de modo implícito.  
  
## <a name="example"></a>Ejemplo  
 [!code-cs[csRefOperators#14](../../../csharp/language-reference/operators/codesnippet/CSharp/left-shift-operator_1.cs)]  
  
## <a name="comments"></a>Comentarios  
 Tenga en cuenta que `i<<1` y `i<<33` dan el mismo resultado, ya que 1 y 33 tienen los mismos cinco bits de orden inferior.  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Operadores de C#](../../../csharp/language-reference/operators/index.md)

