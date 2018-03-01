---
title: '#endif (Referencia de C#)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#endif'
helpviewer_keywords:
- '#endif directive [C#]'
ms.assetid: 6a5fca55-5aee-441f-86f6-1c99fbe9ec05
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d7e68dd20d914052c3fe5cabcb83abdae100465c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="endif-c-reference"></a><span data-ttu-id="f421c-102">#endif (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="f421c-102">#endif (C# Reference)</span></span>
<span data-ttu-id="f421c-103">`#endif` especifica el final de una directiva condicional, que comienza con la directiva [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md).</span><span class="sxs-lookup"><span data-stu-id="f421c-103">`#endif` specifies the end of a conditional directive, which began with the [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) directive.</span></span> <span data-ttu-id="f421c-104">Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="f421c-104">For example,</span></span>  
  
```csharp
#define DEBUG  
// ...  
#if DEBUG  
    Console.WriteLine("Debug version");  
#endif  
```  
  
## <a name="remarks"></a><span data-ttu-id="f421c-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f421c-105">Remarks</span></span>  
 <span data-ttu-id="f421c-106">Una directiva condicional que empieza con una directiva `#if` debe terminar de forma explícita con una directiva `#endif`.</span><span class="sxs-lookup"><span data-stu-id="f421c-106">A conditional directive, beginning with a `#if` directive, must explicitly be terminated with a `#endif` directive.</span></span> <span data-ttu-id="f421c-107">Vea [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) para obtener un ejemplo de cómo usar `#endif`.</span><span class="sxs-lookup"><span data-stu-id="f421c-107">See [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) for an example of how to use `#endif`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f421c-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="f421c-108">See Also</span></span>  
 [<span data-ttu-id="f421c-109">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="f421c-109">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="f421c-110">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="f421c-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="f421c-111">Directivas de preprocesador de C#</span><span class="sxs-lookup"><span data-stu-id="f421c-111">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
