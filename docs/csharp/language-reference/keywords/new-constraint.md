---
title: "Restricción new (Referencia de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- new constraint keyword [C#]
ms.assetid: 58850b64-cb97-4136-be50-1f3bc7fc1da9
caps.latest.revision: 20
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
ms.openlocfilehash: 762941794184605f90443ed8f36c88ecfa50aa84
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="new-constraint-c-reference"></a><span data-ttu-id="10d7a-102">Restricción new (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="10d7a-102">new Constraint (C# Reference)</span></span>
<span data-ttu-id="10d7a-103">La restricción `new` especifica que ningún tipo de argumento en una declaración de clase genérica debe tener un constructor sin parámetros público.</span><span class="sxs-lookup"><span data-stu-id="10d7a-103">The `new` constraint specifies that any type argument in a generic class declaration must have a public parameterless constructor.</span></span> <span data-ttu-id="10d7a-104">Para usar la restricción new, el tipo no puede ser abstracto.</span><span class="sxs-lookup"><span data-stu-id="10d7a-104">To use the new constraint, the type cannot be abstract.</span></span>  
  
## <a name="example"></a><span data-ttu-id="10d7a-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="10d7a-105">Example</span></span>  
 <span data-ttu-id="10d7a-106">Aplique la restricción `new` a un tipo de parámetro cuando la clase genérica cree otras instancias del tipo, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="10d7a-106">Apply the `new` constraint to a type parameter when your generic class creates new instances of the type, as shown in the following example:</span></span>  
  
 <span data-ttu-id="10d7a-107">[!code-cs[csrefKeywordsOperator#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-constraint_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="10d7a-107">[!code-cs[csrefKeywordsOperator#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-constraint_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="10d7a-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="10d7a-108">Example</span></span>  
 <span data-ttu-id="10d7a-109">Cuando use la restricción `new()` con otras restricciones, se debe especificar en último lugar:</span><span class="sxs-lookup"><span data-stu-id="10d7a-109">When you use the `new()` constraint with other constraints, it must be specified last:</span></span>  
  
 <span data-ttu-id="10d7a-110">[!code-cs[csrefKeywordsOperator#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-constraint_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="10d7a-110">[!code-cs[csrefKeywordsOperator#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-constraint_2.cs)]</span></span>  
  
 <span data-ttu-id="10d7a-111">Para obtener más información, vea [Constraints on Type Parameters](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md) (Restricciones de tipos de parámetros [Guía de programación de C#]).</span><span class="sxs-lookup"><span data-stu-id="10d7a-111">For more information, see [Constraints on Type Parameters](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="10d7a-112">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="10d7a-112">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="10d7a-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="10d7a-113">See Also</span></span>  
 <span data-ttu-id="10d7a-114"><xref:System.Collections.Generic></span><span class="sxs-lookup"><span data-stu-id="10d7a-114"><xref:System.Collections.Generic></span></span>   
 <span data-ttu-id="10d7a-115">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="10d7a-115">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="10d7a-116">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="10d7a-116">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="10d7a-117">[Palabras clave de C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="10d7a-117">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="10d7a-118">[Operator Keywords](../../../csharp/language-reference/keywords/operator-keywords.md)  (Palabras clave de operador [Referencia de C#])</span><span class="sxs-lookup"><span data-stu-id="10d7a-118">[Operator Keywords](../../../csharp/language-reference/keywords/operator-keywords.md) </span></span>  
 [<span data-ttu-id="10d7a-119">Genéricos</span><span class="sxs-lookup"><span data-stu-id="10d7a-119">Generics</span></span>](../../../csharp/programming-guide/generics/index.md)

