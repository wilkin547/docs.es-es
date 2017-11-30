---
title: var (Referencia de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- var
- var_CSharpKeyword
helpviewer_keywords: var keyword [C#]
ms.assetid: 0777850a-2691-4e3e-927f-0c850f5efe15
caps.latest.revision: "13"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d2be56243f9c4ddafb3903d14fa6d6f9cb0e2f84
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="var-c-reference"></a><span data-ttu-id="9d64c-102">var (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="9d64c-102">var (C# Reference)</span></span>
<span data-ttu-id="9d64c-103">A partir de Visual C# 3.0, las variables que se declaran en el ámbito de método pueden tener un "tipo" `var` implícito.</span><span class="sxs-lookup"><span data-stu-id="9d64c-103">Beginning in Visual C# 3.0, variables that are declared at method scope can have an implicit "type" `var`.</span></span> <span data-ttu-id="9d64c-104">Una variable local con tipo implícito es fuertemente tipada exactamente igual que si hubiera declarado el tipo, solo que en este caso es el compilador el que lo determina.</span><span class="sxs-lookup"><span data-stu-id="9d64c-104">An implicitly typed local variable is strongly typed just as if you had declared the type yourself, but the compiler determines the type.</span></span> <span data-ttu-id="9d64c-105">Las dos declaraciones siguientes de `i` tienen una función equivalente:</span><span class="sxs-lookup"><span data-stu-id="9d64c-105">The following two declarations of `i` are functionally equivalent:</span></span>  
  
```  
var i = 10; // implicitly typed  
int i = 10; //explicitly typed  
```  
  
 <span data-ttu-id="9d64c-106">Para obtener más información, vea [Implicitly typed local variables](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md) (Variables locales con tipo implícito) y [Type relationships in LINQ query operations](../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md) (Relaciones entre tipos en las operaciones de consulta de LINQ).</span><span class="sxs-lookup"><span data-stu-id="9d64c-106">For more information, see [Implicitly Typed Local Variables](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md) and [Type Relationships in LINQ Query Operations](../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9d64c-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9d64c-107">Example</span></span>  
 <span data-ttu-id="9d64c-108">En el siguiente ejemplo se muestran dos expresiones de consulta.</span><span class="sxs-lookup"><span data-stu-id="9d64c-108">The following example shows two query expressions.</span></span> <span data-ttu-id="9d64c-109">En la primera expresión, el uso de `var` se permite pero no es necesario, ya que el tipo del resultado de la consulta se puede indicar explícitamente como `IEnumerable<string>`.</span><span class="sxs-lookup"><span data-stu-id="9d64c-109">In the first expression, the use of `var` is permitted but is not required, because the type of the query result can be stated explicitly as an `IEnumerable<string>`.</span></span> <span data-ttu-id="9d64c-110">En cambio, en la segunda expresión debe usarse `var`, ya que el resultado es una colección de tipos anónimos y solamente el compilador puede tener acceso al nombre de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="9d64c-110">However, in the second expression, `var` must be used because the result is a collection of anonymous types, and the name of that type is not accessible except to the compiler itself.</span></span> <span data-ttu-id="9d64c-111">Tenga en cuenta que, en el ejemplo 2, la variable de iteración `foreach` `item` también debe tener tipo implícito.</span><span class="sxs-lookup"><span data-stu-id="9d64c-111">Note that in Example #2, the `foreach` iteration variable `item` must also be implicitly typed.</span></span>  
  
 [!code-csharp[csrefKeywordsTypes#18](../../../csharp/language-reference/keywords/codesnippet/CSharp/var_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="9d64c-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="9d64c-112">See Also</span></span>  
 [<span data-ttu-id="9d64c-113">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="9d64c-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="9d64c-114">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="9d64c-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="9d64c-115">Variables locales con asignación implícita de tipos</span><span class="sxs-lookup"><span data-stu-id="9d64c-115">Implicitly Typed Local Variables</span></span>](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md)
