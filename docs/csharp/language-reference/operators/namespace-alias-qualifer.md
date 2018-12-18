---
title: ':: Operador: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- ::_CSharpKeyword
helpviewer_keywords:
- ':: operator [C#]'
- 'namespaces [C#], :: operator'
- namespace alias qualifier operator (::) [C#]
ms.assetid: 698b5a73-85cf-4e0e-9e8e-6496887f8527
ms.openlocfilehash: 2e456be075f3487676228244e0119ff46ed9a538
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53243483"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="6b4f1-102">:: Operador (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="6b4f1-102">:: Operator (C# Reference)</span></span>
<span data-ttu-id="6b4f1-103">El calificador de alias de espacio de nombres (`::`) se usa para buscar identificadores.</span><span class="sxs-lookup"><span data-stu-id="6b4f1-103">The namespace alias qualifier (`::`) is used to look up identifiers.</span></span> <span data-ttu-id="6b4f1-104">Siempre se coloca entre dos identificadores, como en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6b4f1-104">It is always positioned between two identifiers, as in this example:</span></span>  
  
 [!code-csharp[csRefOperators#27](../../../csharp/language-reference/operators/codesnippet/CSharp/namespace-alias-qualifer_1.cs)]  

<span data-ttu-id="6b4f1-105">El operador `::` también puede utilizarse con una *directiva de alias using*:</span><span class="sxs-lookup"><span data-stu-id="6b4f1-105">The `::` operator can also be used with a *using alias directive*:</span></span>

```csharp
// using Col=System.Collections.Generic;
var numbers = new Col::List<int> { 1, 2, 3 };
```

## <a name="remarks"></a><span data-ttu-id="6b4f1-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6b4f1-106">Remarks</span></span>  
 <span data-ttu-id="6b4f1-107">El calificador de alias de espacio de nombres puede ser `global`.</span><span class="sxs-lookup"><span data-stu-id="6b4f1-107">The namespace alias qualifier can be `global`.</span></span> <span data-ttu-id="6b4f1-108">Este invoca una búsqueda del espacio de nombres global, en lugar de un espacio de nombres con alias.</span><span class="sxs-lookup"><span data-stu-id="6b4f1-108">This invokes a lookup in the global namespace, rather than an aliased namespace.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="6b4f1-109">Para obtener más información</span><span class="sxs-lookup"><span data-stu-id="6b4f1-109">For More Information</span></span>  
 <span data-ttu-id="6b4f1-110">Para obtener un ejemplo de cómo usar el operador `::`, vea la siguiente sección:</span><span class="sxs-lookup"><span data-stu-id="6b4f1-110">For an example of how to use the `::` operator, see the following section:</span></span>  
  
-   [<span data-ttu-id="6b4f1-111">Cómo: Utilizar el alias del espacio de nombres global</span><span class="sxs-lookup"><span data-stu-id="6b4f1-111">How to: Use the Global Namespace Alias</span></span>](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="6b4f1-112">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="6b4f1-112">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6b4f1-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="6b4f1-113">See Also</span></span>

- [<span data-ttu-id="6b4f1-114">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="6b4f1-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="6b4f1-115">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="6b4f1-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="6b4f1-116">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="6b4f1-116">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
- [<span data-ttu-id="6b4f1-117">Palabras clave del espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="6b4f1-117">Namespace Keywords</span></span>](../../../csharp/language-reference/keywords/namespace-keywords.md)  
- [<span data-ttu-id="6b4f1-118">. !</span><span class="sxs-lookup"><span data-stu-id="6b4f1-118">. Operator</span></span>](../../../csharp/language-reference/operators/member-access-operator.md)  
- [<span data-ttu-id="6b4f1-119">extern alias</span><span class="sxs-lookup"><span data-stu-id="6b4f1-119">extern alias</span></span>](../../../csharp/language-reference/keywords/extern-alias.md)
