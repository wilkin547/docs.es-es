---
title: Operador ~ (Referencia de C#)
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ffbfc379b7c021ccd8fbed9b796aa9fda6618b55
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="e5cf4-102">Operador ~ (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="e5cf4-102">~ Operator (C# Reference)</span></span>
<span data-ttu-id="e5cf4-103">El operador `~` realiza una operación de complemento bit a bit en su operando, lo que tiene el efecto de invertir cada bit.</span><span class="sxs-lookup"><span data-stu-id="e5cf4-103">The `~` operator performs a bitwise complement operation on its operand, which has the effect of reversing each bit.</span></span> <span data-ttu-id="e5cf4-104">Los operadores de complemento bit a bit están predefinidos para [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md) y [ulong](../../../csharp/language-reference/keywords/ulong.md).</span><span class="sxs-lookup"><span data-stu-id="e5cf4-104">Bitwise complement operators are predefined for [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), and [ulong](../../../csharp/language-reference/keywords/ulong.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e5cf4-105">El símbolo `~` también se usa para declarar finalizadores.</span><span class="sxs-lookup"><span data-stu-id="e5cf4-105">The `~` symbol also is used to declare finalizers.</span></span> <span data-ttu-id="e5cf4-106">Para obtener más información, vea [Finalizadores](../../../csharp/programming-guide/classes-and-structs/destructors.md).</span><span class="sxs-lookup"><span data-stu-id="e5cf4-106">For more information, see [Finalizers](../../../csharp/programming-guide/classes-and-structs/destructors.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e5cf4-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e5cf4-107">Remarks</span></span>  
 <span data-ttu-id="e5cf4-108">Los tipos definidos por el usuario pueden sobrecargar el operador `~`.</span><span class="sxs-lookup"><span data-stu-id="e5cf4-108">User-defined types can overload the `~` operator.</span></span> <span data-ttu-id="e5cf4-109">Para obtener más información, vea [operator (Referencia de C#)](../../../csharp/language-reference/keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="e5cf4-109">For more information, see [operator](../../../csharp/language-reference/keywords/operator.md).</span></span> <span data-ttu-id="e5cf4-110">Las operaciones de tipos enteros suelen estar permitidas en la enumeración.</span><span class="sxs-lookup"><span data-stu-id="e5cf4-110">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e5cf4-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e5cf4-111">Example</span></span>  
 <span data-ttu-id="e5cf4-112">[!code-cs[csRefOperators#25](../../../csharp/language-reference/operators/codesnippet/CSharp/bitwise-complement-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="e5cf4-112">[!code-cs[csRefOperators#25](../../../csharp/language-reference/operators/codesnippet/CSharp/bitwise-complement-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5cf4-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="e5cf4-113">See Also</span></span>  
 <span data-ttu-id="e5cf4-114">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="e5cf4-114">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="e5cf4-115">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="e5cf4-115">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="e5cf4-116">[Operadores de C#](../../../csharp/language-reference/operators/index.md) </span><span class="sxs-lookup"><span data-stu-id="e5cf4-116">[C# Operators](../../../csharp/language-reference/operators/index.md) </span></span>  
 [<span data-ttu-id="e5cf4-117">Finalizadores</span><span class="sxs-lookup"><span data-stu-id="e5cf4-117">Finalizers</span></span>](../../../csharp/programming-guide/classes-and-structs/destructors.md)

