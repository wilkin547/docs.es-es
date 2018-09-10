---
title: Operador ~ (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- ~_CSharpKeyword
helpviewer_keywords:
- tilde (~) one's complement operator [C#]
- ~ operator [C#]
- ~ [C#], bitwise complement operator
- bitwise complement operator [C#]
ms.assetid: 11bc078a-50e2-4d7e-9896-67ef669dc602
ms.openlocfilehash: 8af25217f9e7e66796192783a0b8e3415604dc90
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43510116"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="3e231-102">Operador ~ (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="3e231-102">~ Operator (C# Reference)</span></span>
<span data-ttu-id="3e231-103">El operador `~` realiza una operación de complemento bit a bit en su operando, lo que tiene el efecto de invertir cada bit.</span><span class="sxs-lookup"><span data-stu-id="3e231-103">The `~` operator performs a bitwise complement operation on its operand, which has the effect of reversing each bit.</span></span> <span data-ttu-id="3e231-104">Los operadores de complemento bit a bit están predefinidos para [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md) y [ulong](../../../csharp/language-reference/keywords/ulong.md).</span><span class="sxs-lookup"><span data-stu-id="3e231-104">Bitwise complement operators are predefined for [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), and [ulong](../../../csharp/language-reference/keywords/ulong.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3e231-105">El símbolo `~` también se usa para declarar finalizadores.</span><span class="sxs-lookup"><span data-stu-id="3e231-105">The `~` symbol also is used to declare finalizers.</span></span> <span data-ttu-id="3e231-106">Para obtener más información, vea [Finalizadores](../../../csharp/programming-guide/classes-and-structs/destructors.md).</span><span class="sxs-lookup"><span data-stu-id="3e231-106">For more information, see [Finalizers](../../../csharp/programming-guide/classes-and-structs/destructors.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3e231-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3e231-107">Remarks</span></span>  
 <span data-ttu-id="3e231-108">Los tipos definidos por el usuario pueden sobrecargar el operador `~`.</span><span class="sxs-lookup"><span data-stu-id="3e231-108">User-defined types can overload the `~` operator.</span></span> <span data-ttu-id="3e231-109">Para obtener más información, vea [operator (Referencia de C#)](../../../csharp/language-reference/keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="3e231-109">For more information, see [operator](../../../csharp/language-reference/keywords/operator.md).</span></span> <span data-ttu-id="3e231-110">Las operaciones de tipos enteros suelen estar permitidas en la enumeración.</span><span class="sxs-lookup"><span data-stu-id="3e231-110">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3e231-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3e231-111">Example</span></span>  
 [!code-csharp[csRefOperators#25](../../../csharp/language-reference/operators/codesnippet/CSharp/bitwise-complement-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="3e231-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="3e231-112">See Also</span></span>

- [<span data-ttu-id="3e231-113">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="3e231-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="3e231-114">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="3e231-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="3e231-115">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="3e231-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
- [<span data-ttu-id="3e231-116">Finalizadores</span><span class="sxs-lookup"><span data-stu-id="3e231-116">Finalizers</span></span>](../../../csharp/programming-guide/classes-and-structs/destructors.md)
