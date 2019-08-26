---
title: '#endif: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#endif'
helpviewer_keywords:
- '#endif directive [C#]'
ms.assetid: 6a5fca55-5aee-441f-86f6-1c99fbe9ec05
ms.openlocfilehash: 74205c836b4eeb2d8b17b907bb13708f3225df08
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2019
ms.locfileid: "69608571"
---
# <a name="endif-c-reference"></a><span data-ttu-id="fa7e5-102">#endif (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="fa7e5-102">#endif (C# Reference)</span></span>
<span data-ttu-id="fa7e5-103">`#endif` especifica el final de una directiva condicional, que comienza con la directiva [#if](./preprocessor-if.md).</span><span class="sxs-lookup"><span data-stu-id="fa7e5-103">`#endif` specifies the end of a conditional directive, which began with the [#if](./preprocessor-if.md) directive.</span></span> <span data-ttu-id="fa7e5-104">Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="fa7e5-104">For example,</span></span>  
  
```csharp
#define DEBUG  
// ...  
#if DEBUG  
    Console.WriteLine("Debug version");  
#endif  
```  
  
## <a name="remarks"></a><span data-ttu-id="fa7e5-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fa7e5-105">Remarks</span></span>  
 <span data-ttu-id="fa7e5-106">Una directiva condicional que empieza con una directiva `#if` debe terminar de forma explícita con una directiva `#endif`.</span><span class="sxs-lookup"><span data-stu-id="fa7e5-106">A conditional directive, beginning with a `#if` directive, must explicitly be terminated with a `#endif` directive.</span></span> <span data-ttu-id="fa7e5-107">Vea [#if](./preprocessor-if.md) para obtener un ejemplo de cómo usar `#endif`.</span><span class="sxs-lookup"><span data-stu-id="fa7e5-107">See [#if](./preprocessor-if.md) for an example of how to use `#endif`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa7e5-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="fa7e5-108">See also</span></span>

- [<span data-ttu-id="fa7e5-109">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="fa7e5-109">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="fa7e5-110">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="fa7e5-110">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="fa7e5-111">Directivas de preprocesador de C#</span><span class="sxs-lookup"><span data-stu-id="fa7e5-111">C# Preprocessor Directives</span></span>](./index.md)
