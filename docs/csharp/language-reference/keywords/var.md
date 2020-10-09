---
description: 'var: Referencia de C#'
title: 'var: Referencia de C#'
ms.date: 10/02/2020
f1_keywords:
- var
- var_CSharpKeyword
helpviewer_keywords:
- var keyword [C#]
ms.assetid: 0777850a-2691-4e3e-927f-0c850f5efe15
ms.openlocfilehash: d04bea9bcf5be726d3e81a1a53abed31f59330a0
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2020
ms.locfileid: "91608717"
---
# <a name="var-c-reference"></a><span data-ttu-id="0ab2a-103">var (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="0ab2a-103">var (C# reference)</span></span>

<span data-ttu-id="0ab2a-104">A partir de C# 3, las variables que se declaran en el ámbito de método pueden tener un "tipo" `var` implícito.</span><span class="sxs-lookup"><span data-stu-id="0ab2a-104">Beginning with C# 3, variables that are declared at method scope can have an implicit "type" `var`.</span></span> <span data-ttu-id="0ab2a-105">Una variable local con tipo implícito es fuertemente tipada exactamente igual que si hubiera declarado el tipo, solo que en este caso es el compilador el que lo determina.</span><span class="sxs-lookup"><span data-stu-id="0ab2a-105">An implicitly typed local variable is strongly typed just as if you had declared the type yourself, but the compiler determines the type.</span></span> <span data-ttu-id="0ab2a-106">Las dos declaraciones siguientes de `i` tienen una función equivalente:</span><span class="sxs-lookup"><span data-stu-id="0ab2a-106">The following two declarations of `i` are functionally equivalent:</span></span>

```csharp
var i = 10; // Implicitly typed.
int i = 10; // Explicitly typed.
```

> [!IMPORTANT]
> <span data-ttu-id="0ab2a-107">Cuando `var` se usa con [tipos de referencia que aceptan valores NULL](../builtin-types/nullable-reference-types.md), siempre implica un tipo de referencia que acepta valores NULL, aunque el tipo de expresión no los acepte.</span><span class="sxs-lookup"><span data-stu-id="0ab2a-107">When `var` is used with [nullable reference types](../builtin-types/nullable-reference-types.md) enabled, it always implies a nullable reference type even if the expression type isn't nullable.</span></span>

<span data-ttu-id="0ab2a-108">Un uso común de la palabra clave `var` es con las expresiones de invocación del constructor.</span><span class="sxs-lookup"><span data-stu-id="0ab2a-108">A common use of the `var` keyword is with constructor invocation expressions.</span></span> <span data-ttu-id="0ab2a-109">El uso de `var` permite no repetir un nombre de tipo en una declaración de variable y una creación de instancias de objeto, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0ab2a-109">The use of `var` allows you to not repeat a type name in a variable declaration and object instantiation, as the following example shows:</span></span>

```csharp
var xs = new List<int>();
```

<span data-ttu-id="0ab2a-110">A partir de C# 9.0, se puede usar una [expresión `new`](../operators/new-operator.md) de con tipo de destino como alternativa:</span><span class="sxs-lookup"><span data-stu-id="0ab2a-110">Beginning with C# 9.0, you can use a target-typed [`new` expression](../operators/new-operator.md) as an alternative:</span></span>

```csharp
List<int> xs = new();
List<int>? ys = new();
```

## <a name="example"></a><span data-ttu-id="0ab2a-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0ab2a-111">Example</span></span>

<span data-ttu-id="0ab2a-112">En el siguiente ejemplo se muestran dos expresiones de consulta.</span><span class="sxs-lookup"><span data-stu-id="0ab2a-112">The following example shows two query expressions.</span></span> <span data-ttu-id="0ab2a-113">En la primera expresión, el uso de `var` se permite pero no es necesario, ya que el tipo del resultado de la consulta se puede indicar explícitamente como `IEnumerable<string>`.</span><span class="sxs-lookup"><span data-stu-id="0ab2a-113">In the first expression, the use of `var` is permitted but is not required, because the type of the query result can be stated explicitly as an `IEnumerable<string>`.</span></span> <span data-ttu-id="0ab2a-114">En cambio, en la segunda expresión, `var` permite que el resultado sea una colección de tipos anónimos y solo el compilador puede tener acceso al nombre de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="0ab2a-114">However, in the second expression, `var` allows the result to be a collection of anonymous types, and the name of that type is not accessible except to the compiler itself.</span></span> <span data-ttu-id="0ab2a-115">El uso de `var` elimina la necesidad de crear una nueva clase para el resultado.</span><span class="sxs-lookup"><span data-stu-id="0ab2a-115">Use of `var` eliminates the requirement to create a new class for the result.</span></span> <span data-ttu-id="0ab2a-116">Tenga en cuenta que, en el ejemplo 2, la variable de iteración `foreach``item` también debe tener tipo implícito.</span><span class="sxs-lookup"><span data-stu-id="0ab2a-116">Note that in Example #2, the `foreach` iteration variable `item` must also be implicitly typed.</span></span>

[!code-csharp[csrefKeywordsTypes#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#18)]

## <a name="see-also"></a><span data-ttu-id="0ab2a-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="0ab2a-117">See also</span></span>

- [<span data-ttu-id="0ab2a-118">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="0ab2a-118">C# reference</span></span>](../index.md)
- [<span data-ttu-id="0ab2a-119">Variables locales con asignación implícita de tipos</span><span class="sxs-lookup"><span data-stu-id="0ab2a-119">Implicitly typed local variables</span></span>](../../programming-guide/classes-and-structs/implicitly-typed-local-variables.md)
- [<span data-ttu-id="0ab2a-120">Relaciones entre tipos en las operaciones de consulta LINQ</span><span class="sxs-lookup"><span data-stu-id="0ab2a-120">Type relationships in LINQ query operations</span></span>](../../programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md)
