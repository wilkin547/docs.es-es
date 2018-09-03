---
title: '#endif (Referencia de C#)'
ms.date: 07/20/2015
f1_keywords:
- '#endif'
helpviewer_keywords:
- '#endif directive [C#]'
ms.assetid: 6a5fca55-5aee-441f-86f6-1c99fbe9ec05
ms.openlocfilehash: a652c1226f8f0c624ec8ebf0e665a4aa77ddf6f0
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2018
ms.locfileid: "43420819"
---
# <a name="endif-c-reference"></a><span data-ttu-id="3c7b4-102">#endif (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="3c7b4-102">#endif (C# Reference)</span></span>
<span data-ttu-id="3c7b4-103">`#endif` especifica el final de una directiva condicional, que comienza con la directiva [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md).</span><span class="sxs-lookup"><span data-stu-id="3c7b4-103">`#endif` specifies the end of a conditional directive, which began with the [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) directive.</span></span> <span data-ttu-id="3c7b4-104">Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="3c7b4-104">For example,</span></span>  
  
```csharp
#define DEBUG  
// ...  
#if DEBUG  
    Console.WriteLine("Debug version");  
#endif  
```  
  
## <a name="remarks"></a><span data-ttu-id="3c7b4-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3c7b4-105">Remarks</span></span>  
 <span data-ttu-id="3c7b4-106">Una directiva condicional que empieza con una directiva `#if` debe terminar de forma explícita con una directiva `#endif`.</span><span class="sxs-lookup"><span data-stu-id="3c7b4-106">A conditional directive, beginning with a `#if` directive, must explicitly be terminated with a `#endif` directive.</span></span> <span data-ttu-id="3c7b4-107">Vea [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) para obtener un ejemplo de cómo usar `#endif`.</span><span class="sxs-lookup"><span data-stu-id="3c7b4-107">See [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) for an example of how to use `#endif`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c7b4-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="3c7b4-108">See Also</span></span>

- [<span data-ttu-id="3c7b4-109">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="3c7b4-109">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="3c7b4-110">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="3c7b4-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="3c7b4-111">Directivas de preprocesador de C#</span><span class="sxs-lookup"><span data-stu-id="3c7b4-111">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
