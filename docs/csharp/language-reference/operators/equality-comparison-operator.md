---
title: 'Operador ==: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- ==_CSharpKeyword
helpviewer_keywords:
- == operator [C#]
- equality operator [C#]
ms.assetid: 34c6b597-caa2-4855-a7cd-38ecdd11bd07
ms.openlocfilehash: c6f93be4d422fe42787e36f5b86e2cccbfc645b7
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53239019"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="b6b3f-102">Operador == (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="b6b3f-102">== Operator (C# Reference)</span></span>
<span data-ttu-id="b6b3f-103">Para los tipos de valor predefinidos, el operador de igualdad (`==`) devuelve True si los valores de sus operandos son iguales, `false` en caso contrario.</span><span class="sxs-lookup"><span data-stu-id="b6b3f-103">For predefined value types, the equality operator (`==`) returns true if the values of its operands are equal, `false` otherwise.</span></span> <span data-ttu-id="b6b3f-104">Para los tipos de referencia diferentes de [string](../../../csharp/language-reference/keywords/string.md), `==` devuelve `true` si sus dos operandos hacen referencia al mismo objeto.</span><span class="sxs-lookup"><span data-stu-id="b6b3f-104">For reference types other than [string](../../../csharp/language-reference/keywords/string.md), `==` returns `true` if its two operands refer to the same object.</span></span> <span data-ttu-id="b6b3f-105">Para el tipo `string`, `==` compara los valores de las cadenas.</span><span class="sxs-lookup"><span data-stu-id="b6b3f-105">For the `string` type, `==` compares the values of the strings.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b6b3f-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b6b3f-106">Remarks</span></span>  
 <span data-ttu-id="b6b3f-107">Los tipos de valor definidos por el usuario pueden sobrecargar el operador `==` (vea [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="b6b3f-107">User-defined value types can overload the `==` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="b6b3f-108">Al igual que los tipos de referencia definidos por el usuario, aunque de manera predeterminada `==` se comporta como se ha descrito anteriormente para los tipos de referencia definidos por el usuario y predefinidos.</span><span class="sxs-lookup"><span data-stu-id="b6b3f-108">So can user-defined reference types, although by default `==` behaves as described above for both predefined and user-defined reference types.</span></span> <span data-ttu-id="b6b3f-109">Si `==` está sobrecargado, [!=](../../../csharp/language-reference/operators/not-equal-operator.md) también debe estar sobrecargado.</span><span class="sxs-lookup"><span data-stu-id="b6b3f-109">If `==` is overloaded, [!=](../../../csharp/language-reference/operators/not-equal-operator.md) must also be overloaded.</span></span> <span data-ttu-id="b6b3f-110">Las operaciones de tipos enteros suelen estar permitidas en la enumeración.</span><span class="sxs-lookup"><span data-stu-id="b6b3f-110">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b6b3f-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b6b3f-111">Example</span></span>  
 [!code-csharp[csRefOperators#36](../../../csharp/language-reference/operators/codesnippet/CSharp/equality-comparison-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="b6b3f-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="b6b3f-112">See Also</span></span>

- [<span data-ttu-id="b6b3f-113">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="b6b3f-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="b6b3f-114">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="b6b3f-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="b6b3f-115">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="b6b3f-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
