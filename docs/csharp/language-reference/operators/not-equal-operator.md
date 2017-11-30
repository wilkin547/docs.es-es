---
title: Operador != (Referencia de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: '!=_CSharpKeyword'
helpviewer_keywords:
- inequality operator (!=) [C#]
- not equals operator (!=) [C#]
- '!= operator [C#]'
ms.assetid: eeff7a4e-ad6f-462d-9f8d-49e9b91c6c97
caps.latest.revision: "14"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b69d0b12734e690f0ba0209ccbbc7627ff92fe8a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="67e95-102">Operador != (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="67e95-102">!= Operator (C# Reference)</span></span>
<span data-ttu-id="67e95-103">El operador de desigualdad (`!=`) devuelve false si sus dos operandos son iguales; en caso contrario, devuelve true.</span><span class="sxs-lookup"><span data-stu-id="67e95-103">The inequality operator (`!=`) returns false if its operands are equal, true otherwise.</span></span> <span data-ttu-id="67e95-104">Los operadores de desigualdad están predefinidos para todos los tipos, incluidos string y object.</span><span class="sxs-lookup"><span data-stu-id="67e95-104">Inequality operators are predefined for all types, including string and object.</span></span> <span data-ttu-id="67e95-105">Los tipos definidos por el usuario pueden sobrecargar el operador `!=`.</span><span class="sxs-lookup"><span data-stu-id="67e95-105">User-defined types can overload the `!=` operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="67e95-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="67e95-106">Remarks</span></span>  
 <span data-ttu-id="67e95-107">Para los tipos de valor predefinidos, el operador de desigualdad (`!=`) devuelve true si los valores de sus operandos son diferentes, y false en caso contrario.</span><span class="sxs-lookup"><span data-stu-id="67e95-107">For predefined value types, the inequality operator (`!=`) returns true if the values of its operands are different, false otherwise.</span></span> <span data-ttu-id="67e95-108">Para los tipos de referencia, excepto `string`, `!=` devuelve true si sus dos operandos hacen referencia a objetos diferentes.</span><span class="sxs-lookup"><span data-stu-id="67e95-108">For reference types other than `string`, `!=` returns true if its two operands refer to different objects.</span></span> <span data-ttu-id="67e95-109">Para el tipo `string`, `!=` compara los valores de las cadenas.</span><span class="sxs-lookup"><span data-stu-id="67e95-109">For the `string` type, `!=` compares the values of the strings.</span></span>  
  
 <span data-ttu-id="67e95-110">Los tipos de valor definidos por el usuario pueden sobrecargar el operador `!=` (vea [operator](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="67e95-110">User-defined value types can overload the `!=` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="67e95-111">Al igual que los tipos de referencia definidos por el usuario, aunque de manera predeterminada `!=` se comporta como se ha descrito anteriormente para los tipos de referencia definidos por el usuario y predefinidos.</span><span class="sxs-lookup"><span data-stu-id="67e95-111">So can user-defined reference types, although by default `!=` behaves as described above for both predefined and user-defined reference types.</span></span> <span data-ttu-id="67e95-112">Si `!=` está sobrecargado, [==](../../../csharp/language-reference/operators/equality-comparison-operator.md) también debe estar sobrecargado.</span><span class="sxs-lookup"><span data-stu-id="67e95-112">If `!=` is overloaded, [==](../../../csharp/language-reference/operators/equality-comparison-operator.md) must also be overloaded.</span></span> <span data-ttu-id="67e95-113">Las operaciones de tipos enteros suelen estar permitidas en la enumeración.</span><span class="sxs-lookup"><span data-stu-id="67e95-113">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="67e95-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="67e95-114">Example</span></span>  
 [!code-csharp[csRefOperators#33](../../../csharp/language-reference/operators/codesnippet/CSharp/not-equal-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="67e95-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="67e95-115">See Also</span></span>  
 [<span data-ttu-id="67e95-116">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="67e95-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="67e95-117">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="67e95-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="67e95-118">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="67e95-118">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
