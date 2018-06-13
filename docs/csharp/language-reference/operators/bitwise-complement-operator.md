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
ms.openlocfilehash: 25b157fafde7d2b75cd8b112848a01e9b3fb0db2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33270308"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="13ad0-102">Operador ~ (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="13ad0-102">~ Operator (C# Reference)</span></span>
<span data-ttu-id="13ad0-103">El operador `~` realiza una operación de complemento bit a bit en su operando, lo que tiene el efecto de invertir cada bit.</span><span class="sxs-lookup"><span data-stu-id="13ad0-103">The `~` operator performs a bitwise complement operation on its operand, which has the effect of reversing each bit.</span></span> <span data-ttu-id="13ad0-104">Los operadores de complemento bit a bit están predefinidos para [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md) y [ulong](../../../csharp/language-reference/keywords/ulong.md).</span><span class="sxs-lookup"><span data-stu-id="13ad0-104">Bitwise complement operators are predefined for [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), and [ulong](../../../csharp/language-reference/keywords/ulong.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="13ad0-105">El símbolo `~` también se usa para declarar finalizadores.</span><span class="sxs-lookup"><span data-stu-id="13ad0-105">The `~` symbol also is used to declare finalizers.</span></span> <span data-ttu-id="13ad0-106">Para obtener más información, vea [Finalizadores](../../../csharp/programming-guide/classes-and-structs/destructors.md).</span><span class="sxs-lookup"><span data-stu-id="13ad0-106">For more information, see [Finalizers](../../../csharp/programming-guide/classes-and-structs/destructors.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="13ad0-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="13ad0-107">Remarks</span></span>  
 <span data-ttu-id="13ad0-108">Los tipos definidos por el usuario pueden sobrecargar el operador `~`.</span><span class="sxs-lookup"><span data-stu-id="13ad0-108">User-defined types can overload the `~` operator.</span></span> <span data-ttu-id="13ad0-109">Para obtener más información, vea [operator (Referencia de C#)](../../../csharp/language-reference/keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="13ad0-109">For more information, see [operator](../../../csharp/language-reference/keywords/operator.md).</span></span> <span data-ttu-id="13ad0-110">Las operaciones de tipos enteros suelen estar permitidas en la enumeración.</span><span class="sxs-lookup"><span data-stu-id="13ad0-110">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="13ad0-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="13ad0-111">Example</span></span>  
 [!code-csharp[csRefOperators#25](../../../csharp/language-reference/operators/codesnippet/CSharp/bitwise-complement-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="13ad0-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="13ad0-112">See Also</span></span>  
 [<span data-ttu-id="13ad0-113">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="13ad0-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="13ad0-114">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="13ad0-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="13ad0-115">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="13ad0-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
 [<span data-ttu-id="13ad0-116">Finalizadores</span><span class="sxs-lookup"><span data-stu-id="13ad0-116">Finalizers</span></span>](../../../csharp/programming-guide/classes-and-structs/destructors.md)
