---
title: ':: (operador) (Referencia de C#)'
ms.date: 07/20/2015
f1_keywords:
- ::_CSharpKeyword
helpviewer_keywords:
- ':: operator [C#]'
- 'namespaces [C#], :: operator'
- namespace alias qualifier operator (::) [C#]
ms.assetid: 698b5a73-85cf-4e0e-9e8e-6496887f8527
ms.openlocfilehash: 077d5835b372897cbe797385271effc5d00bf6e3
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43525661"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="419f6-102">:: (operador) (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="419f6-102">:: Operator (C# Reference)</span></span>
<span data-ttu-id="419f6-103">El calificador de alias de espacio de nombres (`::`) se usa para buscar identificadores.</span><span class="sxs-lookup"><span data-stu-id="419f6-103">The namespace alias qualifier (`::`) is used to look up identifiers.</span></span> <span data-ttu-id="419f6-104">Siempre se coloca entre dos identificadores, como en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="419f6-104">It is always positioned between two identifiers, as in this example:</span></span>  
  
 [!code-csharp[csRefOperators#27](../../../csharp/language-reference/operators/codesnippet/CSharp/namespace-alias-qualifer_1.cs)]  

<span data-ttu-id="419f6-105">El operador `::` también puede utilizarse con una *directiva de alias using*:</span><span class="sxs-lookup"><span data-stu-id="419f6-105">The `::` operator can also be used with a *using alias directive*:</span></span>

```csharp
// using Col=System.Collections.Generic;
var numbers = new Col::List<int> { 1, 2, 3 };
```

## <a name="remarks"></a><span data-ttu-id="419f6-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="419f6-106">Remarks</span></span>  
 <span data-ttu-id="419f6-107">El calificador de alias de espacio de nombres puede ser `global`.</span><span class="sxs-lookup"><span data-stu-id="419f6-107">The namespace alias qualifier can be `global`.</span></span> <span data-ttu-id="419f6-108">Este invoca una búsqueda del espacio de nombres global, en lugar de un espacio de nombres con alias.</span><span class="sxs-lookup"><span data-stu-id="419f6-108">This invokes a lookup in the global namespace, rather than an aliased namespace.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="419f6-109">Para obtener más información</span><span class="sxs-lookup"><span data-stu-id="419f6-109">For More Information</span></span>  
 <span data-ttu-id="419f6-110">Para obtener un ejemplo de cómo usar el operador `::`, vea la siguiente sección:</span><span class="sxs-lookup"><span data-stu-id="419f6-110">For an example of how to use the `::` operator, see the following section:</span></span>  
  
-   [<span data-ttu-id="419f6-111">Cómo: Utilizar el alias del espacio de nombres global</span><span class="sxs-lookup"><span data-stu-id="419f6-111">How to: Use the Global Namespace Alias</span></span>](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="419f6-112">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="419f6-112">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="419f6-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="419f6-113">See Also</span></span>

- [<span data-ttu-id="419f6-114">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="419f6-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="419f6-115">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="419f6-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="419f6-116">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="419f6-116">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
- [<span data-ttu-id="419f6-117">Palabras clave del espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="419f6-117">Namespace Keywords</span></span>](../../../csharp/language-reference/keywords/namespace-keywords.md)  
- [<span data-ttu-id="419f6-118">. !</span><span class="sxs-lookup"><span data-stu-id="419f6-118">. Operator</span></span>](../../../csharp/language-reference/operators/member-access-operator.md)  
- [<span data-ttu-id="419f6-119">extern alias</span><span class="sxs-lookup"><span data-stu-id="419f6-119">extern alias</span></span>](../../../csharp/language-reference/keywords/extern-alias.md)
