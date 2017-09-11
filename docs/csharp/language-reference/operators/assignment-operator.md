---
title: Operador = (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- =_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- = operator [C#]
ms.assetid: d802a6d5-32f0-42b8-b180-12f5a081bfc1
caps.latest.revision: 14
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
ms.openlocfilehash: e40b2f221717461443a5d0247b3401eb527a7b5a
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="44521-102">Operador = (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="44521-102">= Operator (C# Reference)</span></span>
<span data-ttu-id="44521-103">El operador de asignación (`=`) almacena el valor de su operando de la derecha en la ubicación de almacenamiento, propiedad o indexador indicado por su operando de la izquierda y devuelve el valor como su resultado.</span><span class="sxs-lookup"><span data-stu-id="44521-103">The assignment operator (`=`) stores the value of its right-hand operand in the storage location, property, or indexer denoted by its left-hand operand and returns the value as its result.</span></span> <span data-ttu-id="44521-104">Los operandos deben ser del mismo tipo (o el operando de la derecha debe poder convertirse implícitamente en el tipo del operando de la izquierda).</span><span class="sxs-lookup"><span data-stu-id="44521-104">The operands must be of the same type (or the right-hand operand must be implicitly convertible to the type of the left-hand operand).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="44521-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="44521-105">Remarks</span></span>  
 <span data-ttu-id="44521-106">El operador de asignación no se puede sobrecargar.</span><span class="sxs-lookup"><span data-stu-id="44521-106">The assignment operator cannot be overloaded.</span></span> <span data-ttu-id="44521-107">En cambio, puede definir operadores de conversión implícitos para un tipo, que le permiten usar el operador de asignación con esos tipos.</span><span class="sxs-lookup"><span data-stu-id="44521-107">However, you can define implicit conversion operators for a type, which enable you to use the assignment operator with those types.</span></span> <span data-ttu-id="44521-108">Para obtener más información, vea [Uso de operadores de conversión](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).</span><span class="sxs-lookup"><span data-stu-id="44521-108">For more information, see [Using Conversion Operators](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="44521-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="44521-109">Example</span></span>  
 <span data-ttu-id="44521-110">[!code-cs[csRefOperators#49](../../../csharp/language-reference/operators/codesnippet/CSharp/assignment-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="44521-110">[!code-cs[csRefOperators#49](../../../csharp/language-reference/operators/codesnippet/CSharp/assignment-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44521-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="44521-111">See Also</span></span>  
 <span data-ttu-id="44521-112">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="44521-112">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="44521-113">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="44521-113">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="44521-114">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="44521-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

