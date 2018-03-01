---
title: Operador ++ (Referencia de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ++_CSharpKeyword
helpviewer_keywords:
- increment operator (++) [C#]
- ++ operator [C#]
ms.assetid: e9dec353-070b-44fb-98ed-eb8fdf753feb
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 6deb2f772fefc93020e7eaaed6be35e48b11df7a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="a4b53-102">Operador ++ (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="a4b53-102">++ Operator (C# Reference)</span></span>
<span data-ttu-id="a4b53-103">El operador de incremento (`++`) incrementa su operando en 1.</span><span class="sxs-lookup"><span data-stu-id="a4b53-103">The increment operator (`++`) increments its operand by 1.</span></span> <span data-ttu-id="a4b53-104">El operador de incremento puede aparecer antes o después de su operando: `++variable` y `variable++`.</span><span class="sxs-lookup"><span data-stu-id="a4b53-104">The increment operator can appear before or after its operand: `++variable` and `variable++`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a4b53-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a4b53-105">Remarks</span></span>  
 <span data-ttu-id="a4b53-106">La primera forma es una operación de incremento de prefijo.</span><span class="sxs-lookup"><span data-stu-id="a4b53-106">The first form is a prefix increment operation.</span></span> <span data-ttu-id="a4b53-107">El resultado de la operación es el valor del operando después del incremento.</span><span class="sxs-lookup"><span data-stu-id="a4b53-107">The result of the operation is the value of the operand after it has been incremented.</span></span>  
  
 <span data-ttu-id="a4b53-108">La segunda forma es una operación de incremento de postfijo.</span><span class="sxs-lookup"><span data-stu-id="a4b53-108">The second form is a postfix increment operation.</span></span> <span data-ttu-id="a4b53-109">El resultado de la operación es el valor del operando antes del incremento.</span><span class="sxs-lookup"><span data-stu-id="a4b53-109">The result of the operation is the value of the operand before it has been incremented.</span></span>  
  
 <span data-ttu-id="a4b53-110">Los tipos numéricos y de enumeración poseen operadores de incremento predefinidos.</span><span class="sxs-lookup"><span data-stu-id="a4b53-110">Numeric and enumeration types have predefined increment operators.</span></span> <span data-ttu-id="a4b53-111">Los tipos definidos por el usuario pueden sobrecargar el operador `++` .</span><span class="sxs-lookup"><span data-stu-id="a4b53-111">User-defined types can overload the `++` operator.</span></span> <span data-ttu-id="a4b53-112">Las operaciones de tipos enteros suelen estar permitidas en la enumeración.</span><span class="sxs-lookup"><span data-stu-id="a4b53-112">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a4b53-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a4b53-113">Example</span></span>  
 [!code-csharp[csRefOperators#3](../../../csharp/language-reference/operators/codesnippet/CSharp/increment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="a4b53-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="a4b53-114">See Also</span></span>  
 [<span data-ttu-id="a4b53-115">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="a4b53-115">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="a4b53-116">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="a4b53-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="a4b53-117">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="a4b53-117">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
