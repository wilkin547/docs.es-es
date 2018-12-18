---
title: 'Operador (): Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- ()_CSharpKeyword
helpviewer_keywords:
- type conversion [C#], () operator
- cast operator [C#]
- () operator [C#]
ms.assetid: 846e1f94-8a8c-42fc-a42c-fbd38e70d8cc
ms.openlocfilehash: 57c23dbd6ee95597514dba92e7217bdcc3e38f24
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53236462"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="77963-102">() (operador) (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="77963-102">() Operator (C# Reference)</span></span>
<span data-ttu-id="77963-103">Además de usarse para especificar el orden de las operaciones de una expresión, los paréntesis se usan para llevar a cabo las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="77963-103">In addition to being used to specify the order of operations in an expression, parentheses are used to perform the following tasks:</span></span>  
  
1.  <span data-ttu-id="77963-104">Especificar conversiones o conversiones de tipo.</span><span class="sxs-lookup"><span data-stu-id="77963-104">Specify casts, or type conversions.</span></span>  
  
     [!code-csharp[csRefOperators#1](../../../csharp/language-reference/operators/codesnippet/CSharp/invocation-operator_1.cs)]  
  
2.  <span data-ttu-id="77963-105">Invocar métodos o delegados.</span><span class="sxs-lookup"><span data-stu-id="77963-105">Invoke methods or delegates.</span></span>  
  
     [!code-csharp[csRefOperators#2](../../../csharp/language-reference/operators/codesnippet/CSharp/invocation-operator_2.cs)]  
  
## <a name="remarks"></a><span data-ttu-id="77963-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="77963-106">Remarks</span></span>  
 <span data-ttu-id="77963-107">Una conversión invoca explícitamente el operador de conversión de un tipo a otro; si no se define ningún operador de conversión, se produce un error en la conversión.</span><span class="sxs-lookup"><span data-stu-id="77963-107">A cast explicitly invokes the conversion operator from one type to another; the cast fails if no such conversion operator is defined.</span></span> <span data-ttu-id="77963-108">Para definir un operador de conversión, vea [explicit](../../../csharp/language-reference/keywords/explicit.md) e [implicit](../../../csharp/language-reference/keywords/implicit.md).</span><span class="sxs-lookup"><span data-stu-id="77963-108">To define a conversion operator, see [explicit](../../../csharp/language-reference/keywords/explicit.md) and [implicit](../../../csharp/language-reference/keywords/implicit.md).</span></span>  
  
 <span data-ttu-id="77963-109">El operador `()` no se puede sobrecargar.</span><span class="sxs-lookup"><span data-stu-id="77963-109">The `()` operator cannot be overloaded.</span></span>  
  
 <span data-ttu-id="77963-110">Para obtener más información, vea [Conversiones de tipos](../../../csharp/programming-guide/types/casting-and-type-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="77963-110">For more information, see [Casting and Type Conversions](../../../csharp/programming-guide/types/casting-and-type-conversions.md).</span></span>  
  
 <span data-ttu-id="77963-111">Para obtener más información sobre la invocación de métodos, vea [Métodos](../../../csharp/programming-guide/classes-and-structs/methods.md).</span><span class="sxs-lookup"><span data-stu-id="77963-111">For more information about method invocation, see [Methods](../../../csharp/programming-guide/classes-and-structs/methods.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="77963-112">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="77963-112">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="77963-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="77963-113">See Also</span></span>

- [<span data-ttu-id="77963-114">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="77963-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="77963-115">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="77963-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="77963-116">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="77963-116">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
