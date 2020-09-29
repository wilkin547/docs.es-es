---
description: '#endif: Referencia de C#'
title: '#endif: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- '#endif'
helpviewer_keywords:
- '#endif directive [C#]'
ms.assetid: 6a5fca55-5aee-441f-86f6-1c99fbe9ec05
ms.openlocfilehash: 0ccc00ceab2aa67c77140e3ef09907ba260d7e9b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91168639"
---
# <a name="endif-c-reference"></a><span data-ttu-id="2291f-103">#endif (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="2291f-103">#endif (C# Reference)</span></span>

<span data-ttu-id="2291f-104">`#endif` especifica el final de una directiva condicional, que comienza con la directiva [#if](./preprocessor-if.md).</span><span class="sxs-lookup"><span data-stu-id="2291f-104">`#endif` specifies the end of a conditional directive, which began with the [#if](./preprocessor-if.md) directive.</span></span> <span data-ttu-id="2291f-105">Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="2291f-105">For example,</span></span>  
  
```csharp
#define DEBUG  
// ...  
#if DEBUG  
    Console.WriteLine("Debug version");  
#endif  
```  
  
## <a name="remarks"></a><span data-ttu-id="2291f-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2291f-106">Remarks</span></span>  

 <span data-ttu-id="2291f-107">Una directiva condicional que empieza con una directiva `#if` debe terminar de forma explícita con una directiva `#endif`.</span><span class="sxs-lookup"><span data-stu-id="2291f-107">A conditional directive, beginning with a `#if` directive, must explicitly be terminated with a `#endif` directive.</span></span> <span data-ttu-id="2291f-108">Vea [#if](./preprocessor-if.md) para obtener un ejemplo de cómo usar `#endif`.</span><span class="sxs-lookup"><span data-stu-id="2291f-108">See [#if](./preprocessor-if.md) for an example of how to use `#endif`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2291f-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="2291f-109">See also</span></span>

- [<span data-ttu-id="2291f-110">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="2291f-110">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="2291f-111">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="2291f-111">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="2291f-112">Directivas de preprocesador de C#</span><span class="sxs-lookup"><span data-stu-id="2291f-112">C# Preprocessor Directives</span></span>](./index.md)
