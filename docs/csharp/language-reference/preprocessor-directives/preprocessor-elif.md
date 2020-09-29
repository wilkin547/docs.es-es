---
description: '#elif: Referencia de C#'
title: '#elif: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- '#elif'
helpviewer_keywords:
- '#elif directive [C#]'
ms.assetid: 731d78df-08e0-4d51-b8c8-f193c27de13f
ms.openlocfilehash: 383c143792a39bb3abcd255804360ad5e2f8ef74
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91168704"
---
# <a name="elif-c-reference"></a><span data-ttu-id="147f7-103">#elif (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="147f7-103">#elif (C# Reference)</span></span>

<span data-ttu-id="147f7-104">`#elif` permite crear una directiva condicional compuesta.</span><span class="sxs-lookup"><span data-stu-id="147f7-104">`#elif` lets you create a compound conditional directive.</span></span> <span data-ttu-id="147f7-105">La expresión `#elif` se evaluará si ninguna de las expresiones de las directivas [#if](./preprocessor-if.md) o `#elif` (opcional) precedentes se evalúan como `true`.</span><span class="sxs-lookup"><span data-stu-id="147f7-105">The `#elif` expression will be evaluated if neither the preceding [#if](./preprocessor-if.md) nor any preceding, optional, `#elif` directive expressions evaluate to `true`.</span></span> <span data-ttu-id="147f7-106">Si una expresión `#elif` se evalúa como `true`, el compilador incluye en la compilación todo el código comprendido entre `#elif` y la siguiente directiva condicional.</span><span class="sxs-lookup"><span data-stu-id="147f7-106">If a `#elif` expression evaluates to `true`, the compiler evaluates all the code between the `#elif` and the next conditional directive.</span></span> <span data-ttu-id="147f7-107">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="147f7-107">For example:</span></span>  
  
```csharp
#define VC7  
//...  
#if debug  
    Console.WriteLine("Debug build");  
#elif VC7  
    Console.WriteLine("Visual Studio 7");  
#endif  
```  
  
 <span data-ttu-id="147f7-108">Se pueden usar los operadores `==` (igualdad), `!=` (desigualdad), `&&` (y), así como `||` (o), para evaluar varios símbolos.</span><span class="sxs-lookup"><span data-stu-id="147f7-108">You can use the operators `==` (equality), `!=` (inequality), `&&` (and), and `||` (or), to evaluate multiple symbols.</span></span> <span data-ttu-id="147f7-109">Es posible agrupar símbolos y operadores mediante paréntesis.</span><span class="sxs-lookup"><span data-stu-id="147f7-109">You can also group symbols and operators with parentheses.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="147f7-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="147f7-110">Remarks</span></span>  

 <span data-ttu-id="147f7-111">`#elif` equivale a usar:</span><span class="sxs-lookup"><span data-stu-id="147f7-111">`#elif` is equivalent to using:</span></span>  
  
```csharp
#else  
#if  
```  
  
 <span data-ttu-id="147f7-112">El uso de `#elif` es más simple ya que cada directiva `#if` requiere una directiva [#endif](./preprocessor-endif.md), mientras que una directiva `#elif` se puede usar sin la directiva `#endif` correspondiente.</span><span class="sxs-lookup"><span data-stu-id="147f7-112">Using `#elif` is simpler, because each `#if` requires a [#endif](./preprocessor-endif.md), whereas a `#elif` can be used without a matching `#endif`.</span></span>  
  
 <span data-ttu-id="147f7-113">Vea [#if](./preprocessor-if.md) para obtener un ejemplo de cómo usar `#elif`.</span><span class="sxs-lookup"><span data-stu-id="147f7-113">See [#if](./preprocessor-if.md) for an example of how to use `#elif`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="147f7-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="147f7-114">See also</span></span>

- [<span data-ttu-id="147f7-115">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="147f7-115">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="147f7-116">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="147f7-116">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="147f7-117">Directivas de preprocesador de C#</span><span class="sxs-lookup"><span data-stu-id="147f7-117">C# Preprocessor Directives</span></span>](./index.md)
