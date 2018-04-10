---
title: Operador = (Referencia de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- =_CSharpKeyword
helpviewer_keywords:
- = operator [C#]
ms.assetid: d802a6d5-32f0-42b8-b180-12f5a081bfc1
caps.latest.revision: 14
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 4c7188abe54cb69678720b4dbbf4dbdea1be4abe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="2e2ed-102">Operador = (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="2e2ed-102">= Operator (C# Reference)</span></span>
<span data-ttu-id="2e2ed-103">El operador de asignación (`=`) almacena el valor de su operando de la derecha en la ubicación de almacenamiento, propiedad o indexador indicado por su operando de la izquierda y devuelve el valor como su resultado.</span><span class="sxs-lookup"><span data-stu-id="2e2ed-103">The assignment operator (`=`) stores the value of its right-hand operand in the storage location, property, or indexer denoted by its left-hand operand and returns the value as its result.</span></span> <span data-ttu-id="2e2ed-104">Los operandos deben ser del mismo tipo (o el operando de la derecha debe poder convertirse implícitamente en el tipo del operando de la izquierda).</span><span class="sxs-lookup"><span data-stu-id="2e2ed-104">The operands must be of the same type (or the right-hand operand must be implicitly convertible to the type of the left-hand operand).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2e2ed-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2e2ed-105">Remarks</span></span>  
 <span data-ttu-id="2e2ed-106">El operador de asignación no se puede sobrecargar.</span><span class="sxs-lookup"><span data-stu-id="2e2ed-106">The assignment operator cannot be overloaded.</span></span> <span data-ttu-id="2e2ed-107">En cambio, puede definir operadores de conversión implícitos para un tipo, que le permiten usar el operador de asignación con esos tipos.</span><span class="sxs-lookup"><span data-stu-id="2e2ed-107">However, you can define implicit conversion operators for a type, which enable you to use the assignment operator with those types.</span></span> <span data-ttu-id="2e2ed-108">Para obtener más información, vea [Usar operadores de conversión (Guía de programación de C#)](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).</span><span class="sxs-lookup"><span data-stu-id="2e2ed-108">For more information, see [Using Conversion Operators](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2e2ed-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2e2ed-109">Example</span></span>  
 [!code-csharp[csRefOperators#49](../../../csharp/language-reference/operators/codesnippet/CSharp/assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="2e2ed-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="2e2ed-110">See Also</span></span>  
 [<span data-ttu-id="2e2ed-111">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="2e2ed-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="2e2ed-112">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="2e2ed-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="2e2ed-113">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="2e2ed-113">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
