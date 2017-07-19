---
title: Operador ~ (Referencia de C#) | Microsoft Docs
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ~_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- tilde (~) one's complement operator [C#]
- ~ operator [C#]
- ~ [C#], bitwise complement operator
- bitwise complement operator [C#]
ms.assetid: 11bc078a-50e2-4d7e-9896-67ef669dc602
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
ms.translationtype: Human Translation
ms.sourcegitcommit: a5ed524a1b17f7be8903f998cbd732594faab831
ms.openlocfilehash: c7245700f78ff52a98c499d895c7eb2f95efe5b6
ms.contentlocale: es-es
ms.lasthandoff: 05/15/2017

---
# <a name="-operator-c-reference"></a>Operador ~ (Referencia de C#)
El operador `~` realiza una operación de complemento bit a bit en su operando, lo que tiene el efecto de invertir cada bit. Los operadores de complemento bit a bit están predefinidos para [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md) y [ulong](../../../csharp/language-reference/keywords/ulong.md).  
  
> [!NOTE]
>  El símbolo `~` también se usa para declarar finalizadores. Para obtener más información, vea [Finalizadores](../../../csharp/programming-guide/classes-and-structs/destructors.md).  
  
## <a name="remarks"></a>Comentarios  
 Los tipos definidos por el usuario pueden sobrecargar el operador `~`. Para obtener más información, vea [operator (Referencia de C#)](../../../csharp/language-reference/keywords/operator.md). Las operaciones de tipos enteros suelen estar permitidas en la enumeración.  
  
## <a name="example"></a>Ejemplo  
 [!code-cs[csRefOperators#25](../../../csharp/language-reference/operators/codesnippet/CSharp/bitwise-complement-operator_1.cs)]  
  
## <a name="see-also"></a>Vea también  
 [Referencia de C#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C#](../../../csharp/programming-guide/index.md)   
 [Operadores de C#](../../../csharp/language-reference/operators/index.md)   
 [Finalizadores](../../../csharp/programming-guide/classes-and-structs/destructors.md)
