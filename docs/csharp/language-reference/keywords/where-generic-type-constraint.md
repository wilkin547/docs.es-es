---
title: "where (restricción de tipo genérico) (Referencia de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- whereconstraint
- whereconstraint_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- where (generic type constraint) [C#]
ms.assetid: d7aa871b-0714-416a-bab2-96f87ada4310
caps.latest.revision: 10
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
ms.openlocfilehash: 8e81640ee56ed672bb09242a070fdf167740874b
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="where-generic-type-constraint-c-reference"></a><span data-ttu-id="84f2c-102">where (restricción de tipo genérico) (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="84f2c-102">where (generic type constraint) (C# Reference)</span></span>
<span data-ttu-id="84f2c-103">En una definición de tipo genérico, la cláusula `where` se usa para especificar restricciones sobre los tipos que se pueden usar como argumentos para un parámetro de tipo definido en una declaración genérica.</span><span class="sxs-lookup"><span data-stu-id="84f2c-103">In a generic type definition, the `where` clause is used to specify constraints on the types that can be used as arguments for a type parameter defined in a generic declaration.</span></span> <span data-ttu-id="84f2c-104">Por ejemplo, se puede declarar una clase genérica, `MyGenericClass`, de modo que el parámetro de tipo `T` implemente la interfaz <xref:System.IComparable%601>:</span><span class="sxs-lookup"><span data-stu-id="84f2c-104">For example, you can declare a generic class, `MyGenericClass`, such that the type parameter `T` implements the <xref:System.IComparable%601> interface:</span></span>  
  
```csharp  
public class MyGenericClass<T> where T:IComparable { }  
```  
  
> [!NOTE]
>  <span data-ttu-id="84f2c-105">Para obtener más información sobre la cláusula where en una expresión de consulta, vea [where (Cláusula)](../../../csharp/language-reference/keywords/where-clause.md).</span><span class="sxs-lookup"><span data-stu-id="84f2c-105">For more information on the where clause in a query expression, see [where clause](../../../csharp/language-reference/keywords/where-clause.md).</span></span>  
  
 <span data-ttu-id="84f2c-106">Además de las restricciones de interfaz, una cláusula `where` puede incluir una restricción de clase base, que establece que un tipo debe tener la clase especificada como clase base (o ser la propia clase) para poder usarse como un argumento de tipo para ese tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="84f2c-106">In addition to interface constraints, a `where` clause can include a base class constraint, which states that a type must have the specified class as a base class (or be that class itself) in order to be used as a type argument for that generic type.</span></span> <span data-ttu-id="84f2c-107">Si se usa este tipo de restricción, debe aparecer antes que cualquier otra restricción sobre ese parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="84f2c-107">If such a constraint is used, it must appear before any other constraints on that type parameter.</span></span>  
  
 <span data-ttu-id="84f2c-108">[!code-cs[csrefKeywordsContextual#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-generic-type-constraint_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="84f2c-108">[!code-cs[csrefKeywordsContextual#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-generic-type-constraint_1.cs)]</span></span>  
  
 <span data-ttu-id="84f2c-109">Puede que la cláusula `where` incluya también una restricción de constructor.</span><span class="sxs-lookup"><span data-stu-id="84f2c-109">The `where` clause may also include a constructor constraint.</span></span> <span data-ttu-id="84f2c-110">Es posible crear una instancia de un parámetro de tipo usando el operador new; pero, para ello, el parámetro de tipo debe restringirse mediante la restricción de constructor, `new()`.</span><span class="sxs-lookup"><span data-stu-id="84f2c-110">It is possible to create an instance of a type parameter using the new operator; however, in order to do so the type parameter must be constrained by the constructor constraint, `new()`.</span></span> <span data-ttu-id="84f2c-111">La [restricción new()](../../../csharp/language-reference/keywords/new-constraint.md) permite que el compilador sepa que cualquier argumento de tipo especificado debe tener accesible un constructor sin parámetros o el constructor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="84f2c-111">The [new() Constraint](../../../csharp/language-reference/keywords/new-constraint.md) lets the compiler know that any type argument supplied must have an accessible parameterless--or default-- constructor.</span></span> <span data-ttu-id="84f2c-112">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="84f2c-112">For example:</span></span>  
  
 <span data-ttu-id="84f2c-113">[!code-cs[csrefKeywordsContextual#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-generic-type-constraint_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="84f2c-113">[!code-cs[csrefKeywordsContextual#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-generic-type-constraint_2.cs)]</span></span>  
  
 <span data-ttu-id="84f2c-114">La restricción `new()` aparece en último lugar en la cláusula `where`.</span><span class="sxs-lookup"><span data-stu-id="84f2c-114">The `new()` constraint appears last in the `where` clause.</span></span>  
  
 <span data-ttu-id="84f2c-115">Con varios parámetros de tipo, use una cláusula `where` para cada parámetro de tipo, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="84f2c-115">With multiple type parameters, use one `where` clause for each type parameter, for example:</span></span>  
  
 <span data-ttu-id="84f2c-116">[!code-cs[csrefKeywordsContextual#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-generic-type-constraint_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="84f2c-116">[!code-cs[csrefKeywordsContextual#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/where-generic-type-constraint_3.cs)]</span></span>  
  
 <span data-ttu-id="84f2c-117">También puede asociar restricciones a parámetros de tipo de métodos genéricos, de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="84f2c-117">You can also attach constraints to type parameters of generic methods, like this:</span></span>  
  
```csharp  
public bool MyMethod<T>(T t) where T : IMyInterface { }  
```  
  
 <span data-ttu-id="84f2c-118">Observe que la sintaxis para describir las restricciones de parámetro de tipo en delegados es igual que la de métodos:</span><span class="sxs-lookup"><span data-stu-id="84f2c-118">Notice that the syntax to describe type parameter constraints on delegates is the same as that of methods:</span></span>  
  
```csharp  
delegate T MyDelegate<T>() where T : new()  
```  
  
 <span data-ttu-id="84f2c-119">Para obtener información sobre los delegados genéricos, vea [Delegados genéricos](../../../csharp/programming-guide/generics/generic-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="84f2c-119">For information on generic delegates, see [Generic Delegates](../../../csharp/programming-guide/generics/generic-delegates.md).</span></span>  
  
 <span data-ttu-id="84f2c-120">Para obtener más información sobre la sintaxis y el uso de restricciones, vea [Restricciones de tipos de parámetros](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="84f2c-120">For details on the syntax and use of constraints, see [Constraints on Type Parameters](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="84f2c-121">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="84f2c-121">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="84f2c-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="84f2c-122">See Also</span></span>  
 <span data-ttu-id="84f2c-123">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="84f2c-123">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="84f2c-124">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="84f2c-124">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="84f2c-125">[Introducción a los genéricos](../../../csharp/programming-guide/generics/introduction-to-generics.md) </span><span class="sxs-lookup"><span data-stu-id="84f2c-125">[Introduction to Generics](../../../csharp/programming-guide/generics/introduction-to-generics.md) </span></span>  
 <span data-ttu-id="84f2c-126">[new (Restricción)](../../../csharp/language-reference/keywords/new-constraint.md) </span><span class="sxs-lookup"><span data-stu-id="84f2c-126">[new Constraint](../../../csharp/language-reference/keywords/new-constraint.md) </span></span>  
 [<span data-ttu-id="84f2c-127">Restricciones de tipos de parámetros</span><span class="sxs-lookup"><span data-stu-id="84f2c-127">Constraints on Type Parameters</span></span>](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)

