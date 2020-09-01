---
description: '#endif: Referencia de C#'
title: '#endif: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- '#endif'
helpviewer_keywords:
- '#endif directive [C#]'
ms.assetid: 6a5fca55-5aee-441f-86f6-1c99fbe9ec05
ms.openlocfilehash: 8068a6e437145178fd5c88763c86692a8700c349
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89138168"
---
# <a name="endif-c-reference"></a><span data-ttu-id="15b73-103">#endif (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="15b73-103">#endif (C# Reference)</span></span>
<span data-ttu-id="15b73-104">`#endif` especifica el final de una directiva condicional, que comienza con la directiva [#if](./preprocessor-if.md).</span><span class="sxs-lookup"><span data-stu-id="15b73-104">`#endif` specifies the end of a conditional directive, which began with the [#if](./preprocessor-if.md) directive.</span></span> <span data-ttu-id="15b73-105">Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="15b73-105">For example,</span></span>  
  
```csharp
#define DEBUG  
// ...  
#if DEBUG  
    Console.WriteLine("Debug version");  
#endif  
```  
  
## <a name="remarks"></a><span data-ttu-id="15b73-106">Observaciones</span><span class="sxs-lookup"><span data-stu-id="15b73-106">Remarks</span></span>  
 <span data-ttu-id="15b73-107">Una directiva condicional que empieza con una directiva `#if` debe terminar de forma explícita con una directiva `#endif`.</span><span class="sxs-lookup"><span data-stu-id="15b73-107">A conditional directive, beginning with a `#if` directive, must explicitly be terminated with a `#endif` directive.</span></span> <span data-ttu-id="15b73-108">Vea [#if](./preprocessor-if.md) para obtener un ejemplo de cómo usar `#endif`.</span><span class="sxs-lookup"><span data-stu-id="15b73-108">See [#if](./preprocessor-if.md) for an example of how to use `#endif`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15b73-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="15b73-109">See also</span></span>

- [<span data-ttu-id="15b73-110">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="15b73-110">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="15b73-111">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="15b73-111">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="15b73-112">Directivas de preprocesador de C#</span><span class="sxs-lookup"><span data-stu-id="15b73-112">C# Preprocessor Directives</span></span>](./index.md)
