---
title: 'Operador :: (referencia de C#)'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- ::_CSharpKeyword
helpviewer_keywords:
- ':: operator [C#]'
- 'namespaces [C#], :: operator'
- namespace alias qualifier operator (::) [C#]
ms.assetid: 698b5a73-85cf-4e0e-9e8e-6496887f8527
ms.openlocfilehash: c494e8dbb18f44ce5520b21800a21d3feb03da59
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/12/2019
ms.locfileid: "67025077"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="96903-102">Operador :: (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="96903-102">:: operator (C# reference)</span></span>

<span data-ttu-id="96903-103">El calificador de alias de espacio de nombres (`::`) se usa para buscar identificadores.</span><span class="sxs-lookup"><span data-stu-id="96903-103">The namespace alias qualifier (`::`) is used to look up identifiers.</span></span> <span data-ttu-id="96903-104">Siempre se coloca entre dos identificadores, como en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="96903-104">It is always positioned between two identifiers, as in this example:</span></span>

[!code-csharp[csRefOperators#27](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#27)]

<span data-ttu-id="96903-105">El operador `::` también puede utilizarse con una *directiva de alias using*:</span><span class="sxs-lookup"><span data-stu-id="96903-105">The `::` operator can also be used with a *using alias directive*:</span></span>

```csharp
// using Col=System.Collections.Generic;
var numbers = new Col::List<int> { 1, 2, 3 };
```

## <a name="remarks"></a><span data-ttu-id="96903-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="96903-106">Remarks</span></span>

<span data-ttu-id="96903-107">El calificador de alias de espacio de nombres puede ser `global`.</span><span class="sxs-lookup"><span data-stu-id="96903-107">The namespace alias qualifier can be `global`.</span></span> <span data-ttu-id="96903-108">Este invoca una búsqueda del espacio de nombres global, en lugar de un espacio de nombres con alias.</span><span class="sxs-lookup"><span data-stu-id="96903-108">This invokes a lookup in the global namespace, rather than an aliased namespace.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="96903-109">Para obtener más información</span><span class="sxs-lookup"><span data-stu-id="96903-109">For more information</span></span>

<span data-ttu-id="96903-110">Para obtener un ejemplo de cómo usar el operador `::`, vea la siguiente sección:</span><span class="sxs-lookup"><span data-stu-id="96903-110">For an example of how to use the `::` operator, see the following section:</span></span>

- [<span data-ttu-id="96903-111">Cómo: Utilizar el alias del espacio de nombres global</span><span class="sxs-lookup"><span data-stu-id="96903-111">How to: Use the Global Namespace Alias</span></span>](../../programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)

## <a name="c-language-specification"></a><span data-ttu-id="96903-112">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="96903-112">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="96903-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="96903-113">See also</span></span>

- [<span data-ttu-id="96903-114">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="96903-114">C# reference</span></span>](../index.md)
- [<span data-ttu-id="96903-115">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="96903-115">C# operators</span></span>](index.md)
- [<span data-ttu-id="96903-116">Operador .</span><span class="sxs-lookup"><span data-stu-id="96903-116">. operator</span></span>](member-access-operators.md#member-access-operator-)
- [<span data-ttu-id="96903-117">extern alias</span><span class="sxs-lookup"><span data-stu-id="96903-117">extern alias</span></span>](../keywords/extern-alias.md)
