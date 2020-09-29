---
description: '#else: Referencia de C#'
title: '#else: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- '#else'
helpviewer_keywords:
- '#else directive [C#]'
ms.assetid: 6a347322-cfa2-4a86-98f8-ddfa2cb7d4db
ms.openlocfilehash: f0dc8c34672c3e9e5a2207211794fbc8099640c5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91168678"
---
# <a name="else-c-reference"></a><span data-ttu-id="95bfa-103">#else (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="95bfa-103">#else (C# Reference)</span></span>

<span data-ttu-id="95bfa-104">`#else` permite crear una directiva condicional compuesta, de modo que, si ninguna de las expresiones de las directivas [#if](./preprocessor-if.md) o [#elif](./preprocessor-elif.md) (opcional) anteriores se evalúan como `true`, el compilador evaluará todo el código entre `#else` y la directiva `#endif` siguiente.</span><span class="sxs-lookup"><span data-stu-id="95bfa-104">`#else` lets you create a compound conditional directive, so that, if none of the expressions in the preceding [#if](./preprocessor-if.md) or (optional) [#elif](./preprocessor-elif.md) directives evaluate to `true`, the compiler will evaluate all code between `#else` and the subsequent `#endif`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="95bfa-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="95bfa-105">Remarks</span></span>  

 <span data-ttu-id="95bfa-106">[#endif](./preprocessor-endif.md) debe ser la siguiente directiva de preprocesador después de `#else`.</span><span class="sxs-lookup"><span data-stu-id="95bfa-106">[#endif](./preprocessor-endif.md) must be the next preprocessor directive after `#else`.</span></span> <span data-ttu-id="95bfa-107">Vea [#if](./preprocessor-if.md) para obtener un ejemplo de cómo usar `#else`.</span><span class="sxs-lookup"><span data-stu-id="95bfa-107">See [#if](./preprocessor-if.md) for an example of how to use `#else`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95bfa-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="95bfa-108">See also</span></span>

- [<span data-ttu-id="95bfa-109">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="95bfa-109">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="95bfa-110">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="95bfa-110">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="95bfa-111">Directivas de preprocesador de C#</span><span class="sxs-lookup"><span data-stu-id="95bfa-111">C# Preprocessor Directives</span></span>](./index.md)
