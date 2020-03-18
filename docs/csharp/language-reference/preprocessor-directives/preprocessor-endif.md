---
title: '#endif: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- '#endif'
helpviewer_keywords:
- '#endif directive [C#]'
ms.assetid: 6a5fca55-5aee-441f-86f6-1c99fbe9ec05
ms.openlocfilehash: cc344a224e2308e843328b228dd5e2466d02069f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75712551"
---
# <a name="endif-c-reference"></a><span data-ttu-id="d7974-102">#endif (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="d7974-102">#endif (C# Reference)</span></span>
<span data-ttu-id="d7974-103">`#endif` especifica el final de una directiva condicional, que comienza con la directiva [#if](./preprocessor-if.md).</span><span class="sxs-lookup"><span data-stu-id="d7974-103">`#endif` specifies the end of a conditional directive, which began with the [#if](./preprocessor-if.md) directive.</span></span> <span data-ttu-id="d7974-104">Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="d7974-104">For example,</span></span>  
  
```csharp
#define DEBUG  
// ...  
#if DEBUG  
    Console.WriteLine("Debug version");  
#endif  
```  
  
## <a name="remarks"></a><span data-ttu-id="d7974-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d7974-105">Remarks</span></span>  
 <span data-ttu-id="d7974-106">Una directiva condicional que empieza con una directiva `#if` debe terminar de forma explícita con una directiva `#endif`.</span><span class="sxs-lookup"><span data-stu-id="d7974-106">A conditional directive, beginning with a `#if` directive, must explicitly be terminated with a `#endif` directive.</span></span> <span data-ttu-id="d7974-107">Vea [#if](./preprocessor-if.md) para obtener un ejemplo de cómo usar `#endif`.</span><span class="sxs-lookup"><span data-stu-id="d7974-107">See [#if](./preprocessor-if.md) for an example of how to use `#endif`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7974-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="d7974-108">See also</span></span>

- [<span data-ttu-id="d7974-109">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="d7974-109">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="d7974-110">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="d7974-110">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="d7974-111">Directivas de preprocesador de C#</span><span class="sxs-lookup"><span data-stu-id="d7974-111">C# Preprocessor Directives</span></span>](./index.md)
