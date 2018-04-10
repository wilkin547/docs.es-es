---
title: Restricción new (Referencia de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- new constraint keyword [C#]
ms.assetid: 58850b64-cb97-4136-be50-1f3bc7fc1da9
caps.latest.revision: 20
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 8557e056a664fd470b1f185b619d81235c8fcba7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="new-constraint-c-reference"></a><span data-ttu-id="df7e9-102">Restricción new (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="df7e9-102">new Constraint (C# Reference)</span></span>
<span data-ttu-id="df7e9-103">La restricción `new` especifica que ningún tipo de argumento en una declaración de clase genérica debe tener un constructor sin parámetros público.</span><span class="sxs-lookup"><span data-stu-id="df7e9-103">The `new` constraint specifies that any type argument in a generic class declaration must have a public parameterless constructor.</span></span> <span data-ttu-id="df7e9-104">Para usar la restricción new, el tipo no puede ser abstracto.</span><span class="sxs-lookup"><span data-stu-id="df7e9-104">To use the new constraint, the type cannot be abstract.</span></span>  
  
## <a name="example"></a><span data-ttu-id="df7e9-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="df7e9-105">Example</span></span>  
 <span data-ttu-id="df7e9-106">Aplique la restricción `new` a un tipo de parámetro cuando la clase genérica cree otras instancias del tipo, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="df7e9-106">Apply the `new` constraint to a type parameter when your generic class creates new instances of the type, as shown in the following example:</span></span>  
  
 [!code-csharp[csrefKeywordsOperator#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-constraint_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="df7e9-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="df7e9-107">Example</span></span>  
 <span data-ttu-id="df7e9-108">Cuando use la restricción `new()` con otras restricciones, se debe especificar en último lugar:</span><span class="sxs-lookup"><span data-stu-id="df7e9-108">When you use the `new()` constraint with other constraints, it must be specified last:</span></span>  
  
 [!code-csharp[csrefKeywordsOperator#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-constraint_2.cs)]  
  
 <span data-ttu-id="df7e9-109">Para obtener más información, vea [Restricciones de tipos de parámetros](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="df7e9-109">For more information, see [Constraints on Type Parameters](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="df7e9-110">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="df7e9-110">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="df7e9-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="df7e9-111">See Also</span></span>  
 <xref:System.Collections.Generic>  
 [<span data-ttu-id="df7e9-112">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="df7e9-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="df7e9-113">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="df7e9-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="df7e9-114">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="df7e9-114">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="df7e9-115">Palabras clave de operador</span><span class="sxs-lookup"><span data-stu-id="df7e9-115">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)  
 [<span data-ttu-id="df7e9-116">Genéricos</span><span class="sxs-lookup"><span data-stu-id="df7e9-116">Generics</span></span>](../../../csharp/programming-guide/generics/index.md)
