---
description: 'var: Referencia de C#'
title: 'var: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- var
- var_CSharpKeyword
helpviewer_keywords:
- var keyword [C#]
ms.assetid: 0777850a-2691-4e3e-927f-0c850f5efe15
ms.openlocfilehash: 303a880a54a79e50515060e0ea28e8d021fa1b76
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89141717"
---
# <a name="var-c-reference"></a><span data-ttu-id="58d0a-103">var (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="58d0a-103">var (C# Reference)</span></span>

<span data-ttu-id="58d0a-104">A partir de Visual C# 3.0, las variables que se declaran en el ámbito de método pueden tener un "tipo" `var` implícito.</span><span class="sxs-lookup"><span data-stu-id="58d0a-104">Beginning in Visual C# 3.0, variables that are declared at method scope can have an implicit "type" `var`.</span></span> <span data-ttu-id="58d0a-105">Una variable local con tipo implícito es fuertemente tipada exactamente igual que si hubiera declarado el tipo, solo que en este caso es el compilador el que lo determina.</span><span class="sxs-lookup"><span data-stu-id="58d0a-105">An implicitly typed local variable is strongly typed just as if you had declared the type yourself, but the compiler determines the type.</span></span> <span data-ttu-id="58d0a-106">Las dos declaraciones siguientes de `i` tienen una función equivalente:</span><span class="sxs-lookup"><span data-stu-id="58d0a-106">The following two declarations of `i` are functionally equivalent:</span></span>

```csharp
var i = 10; // Implicitly typed.
int i = 10; // Explicitly typed.
```

<span data-ttu-id="58d0a-107">Para obtener más información, vea [Variables locales con asignación implícita de tipos](../../programming-guide/classes-and-structs/implicitly-typed-local-variables.md) y [Relaciones entre tipos en operaciones de consulta LINQ](../../programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).</span><span class="sxs-lookup"><span data-stu-id="58d0a-107">For more information, see [Implicitly Typed Local Variables](../../programming-guide/classes-and-structs/implicitly-typed-local-variables.md) and [Type Relationships in LINQ Query Operations](../../programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="58d0a-108">Cuando `var` se usa con tipos de referencia que aceptan valores NULL, siempre implica un tipo de referencia que acepta valores NULL, aunque el tipo de expresión no los acepte.</span><span class="sxs-lookup"><span data-stu-id="58d0a-108">When `var` is used with nullable reference types enabled, it always implies a nullable reference type even if the expression type isn't nullable.</span></span>

## <a name="example"></a><span data-ttu-id="58d0a-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="58d0a-109">Example</span></span>

<span data-ttu-id="58d0a-110">En el siguiente ejemplo se muestran dos expresiones de consulta.</span><span class="sxs-lookup"><span data-stu-id="58d0a-110">The following example shows two query expressions.</span></span> <span data-ttu-id="58d0a-111">En la primera expresión, el uso de `var` se permite pero no es necesario, ya que el tipo del resultado de la consulta se puede indicar explícitamente como `IEnumerable<string>`.</span><span class="sxs-lookup"><span data-stu-id="58d0a-111">In the first expression, the use of `var` is permitted but is not required, because the type of the query result can be stated explicitly as an `IEnumerable<string>`.</span></span> <span data-ttu-id="58d0a-112">En cambio, en la segunda expresión, `var` permite que el resultado sea una colección de tipos anónimos y solo el compilador puede tener acceso al nombre de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="58d0a-112">However, in the second expression, `var` allows the result to be a collection of anonymous types, and the name of that type is not accessible except to the compiler itself.</span></span> <span data-ttu-id="58d0a-113">El uso de `var` elimina la necesidad de crear una nueva clase para el resultado.</span><span class="sxs-lookup"><span data-stu-id="58d0a-113">Use of `var` eliminates the requirement to create a new class for the result.</span></span> <span data-ttu-id="58d0a-114">Tenga en cuenta que, en el ejemplo 2, la variable de iteración `foreach``item` también debe tener tipo implícito.</span><span class="sxs-lookup"><span data-stu-id="58d0a-114">Note that in Example #2, the `foreach` iteration variable `item` must also be implicitly typed.</span></span>

[!code-csharp[csrefKeywordsTypes#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#18)]

## <a name="see-also"></a><span data-ttu-id="58d0a-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="58d0a-115">See also</span></span>

- [<span data-ttu-id="58d0a-116">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="58d0a-116">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="58d0a-117">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="58d0a-117">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="58d0a-118">Variables locales con asignación implícita de tipos</span><span class="sxs-lookup"><span data-stu-id="58d0a-118">Implicitly Typed Local Variables</span></span>](../../programming-guide/classes-and-structs/implicitly-typed-local-variables.md)
