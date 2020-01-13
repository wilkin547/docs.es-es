---
title: 'var: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- var
- var_CSharpKeyword
helpviewer_keywords:
- var keyword [C#]
ms.assetid: 0777850a-2691-4e3e-927f-0c850f5efe15
ms.openlocfilehash: ff8348a725f43fa8789c73fa58549da26126369c
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712889"
---
# <a name="var-c-reference"></a><span data-ttu-id="b092f-102">var (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="b092f-102">var (C# Reference)</span></span>

<span data-ttu-id="b092f-103">A partir de Visual C# 3.0, las variables que se declaran en el ámbito de método pueden tener un "tipo" `var` implícito.</span><span class="sxs-lookup"><span data-stu-id="b092f-103">Beginning in Visual C# 3.0, variables that are declared at method scope can have an implicit "type" `var`.</span></span> <span data-ttu-id="b092f-104">Una variable local con tipo implícito es fuertemente tipada exactamente igual que si hubiera declarado el tipo, solo que en este caso es el compilador el que lo determina.</span><span class="sxs-lookup"><span data-stu-id="b092f-104">An implicitly typed local variable is strongly typed just as if you had declared the type yourself, but the compiler determines the type.</span></span> <span data-ttu-id="b092f-105">Las dos declaraciones siguientes de `i` tienen una función equivalente:</span><span class="sxs-lookup"><span data-stu-id="b092f-105">The following two declarations of `i` are functionally equivalent:</span></span>

```csharp
var i = 10; // Implicitly typed.
int i = 10; // Explicitly typed.
```

<span data-ttu-id="b092f-106">Para obtener más información, vea [Implicitly typed local variables](../../programming-guide/classes-and-structs/implicitly-typed-local-variables.md) (Variables locales con tipo implícito) y [Type relationships in LINQ query operations](../../programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md) (Relaciones entre tipos en las operaciones de consulta de LINQ).</span><span class="sxs-lookup"><span data-stu-id="b092f-106">For more information, see [Implicitly Typed Local Variables](../../programming-guide/classes-and-structs/implicitly-typed-local-variables.md) and [Type Relationships in LINQ Query Operations](../../programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).</span></span>

## <a name="example"></a><span data-ttu-id="b092f-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b092f-107">Example</span></span>

<span data-ttu-id="b092f-108">En el siguiente ejemplo se muestran dos expresiones de consulta.</span><span class="sxs-lookup"><span data-stu-id="b092f-108">The following example shows two query expressions.</span></span> <span data-ttu-id="b092f-109">En la primera expresión, el uso de `var` se permite pero no es necesario, ya que el tipo del resultado de la consulta se puede indicar explícitamente como `IEnumerable<string>`.</span><span class="sxs-lookup"><span data-stu-id="b092f-109">In the first expression, the use of `var` is permitted but is not required, because the type of the query result can be stated explicitly as an `IEnumerable<string>`.</span></span> <span data-ttu-id="b092f-110">En cambio, en la segunda expresión, `var` permite que el resultado sea una colección de tipos anónimos y solo el compilador puede tener acceso al nombre de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="b092f-110">However, in the second expression, `var` allows the result to be a collection of anonymous types, and the name of that type is not accessible except to the compiler itself.</span></span> <span data-ttu-id="b092f-111">El uso de `var` elimina la necesidad de crear una nueva clase para el resultado.</span><span class="sxs-lookup"><span data-stu-id="b092f-111">Use of `var` eliminates the requirement to create a new class for the result.</span></span> <span data-ttu-id="b092f-112">Tenga en cuenta que, en el ejemplo 2, la variable de iteración `foreach``item` también debe tener tipo implícito.</span><span class="sxs-lookup"><span data-stu-id="b092f-112">Note that in Example #2, the `foreach` iteration variable `item` must also be implicitly typed.</span></span>

[!code-csharp[csrefKeywordsTypes#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#18)]

## <a name="see-also"></a><span data-ttu-id="b092f-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="b092f-113">See also</span></span>

- [<span data-ttu-id="b092f-114">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="b092f-114">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="b092f-115">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="b092f-115">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="b092f-116">Variables locales con asignación implícita de tipos</span><span class="sxs-lookup"><span data-stu-id="b092f-116">Implicitly Typed Local Variables</span></span>](../../programming-guide/classes-and-structs/implicitly-typed-local-variables.md)
