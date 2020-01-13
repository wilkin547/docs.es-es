---
title: '#elif: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- '#elif'
helpviewer_keywords:
- '#elif directive [C#]'
ms.assetid: 731d78df-08e0-4d51-b8c8-f193c27de13f
ms.openlocfilehash: c78818f40b76414d289af6c704ff019b63befe37
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712577"
---
# <a name="elif-c-reference"></a><span data-ttu-id="5ef15-102">#elif (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="5ef15-102">#elif (C# Reference)</span></span>
<span data-ttu-id="5ef15-103">`#elif` permite crear una directiva condicional compuesta.</span><span class="sxs-lookup"><span data-stu-id="5ef15-103">`#elif` lets you create a compound conditional directive.</span></span> <span data-ttu-id="5ef15-104">La expresión `#elif` se evaluará si ninguna de las expresiones de las directivas [#if](./preprocessor-if.md) o `#elif` (opcional) precedentes se evalúan como `true`.</span><span class="sxs-lookup"><span data-stu-id="5ef15-104">The `#elif` expression will be evaluated if neither the preceding [#if](./preprocessor-if.md) nor any preceding, optional, `#elif` directive expressions evaluate to `true`.</span></span> <span data-ttu-id="5ef15-105">Si una expresión `#elif` se evalúa como `true`, el compilador incluye en la compilación todo el código comprendido entre `#elif` y la siguiente directiva condicional.</span><span class="sxs-lookup"><span data-stu-id="5ef15-105">If a `#elif` expression evaluates to `true`, the compiler evaluates all the code between the `#elif` and the next conditional directive.</span></span> <span data-ttu-id="5ef15-106">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5ef15-106">For example:</span></span>  
  
```csharp
#define VC7  
//...  
#if debug  
    Console.WriteLine("Debug build");  
#elif VC7  
    Console.WriteLine("Visual Studio 7");  
#endif  
```  
  
 <span data-ttu-id="5ef15-107">Se pueden usar los operadores `==` (igualdad), `!=` (desigualdad), `&&` (y), así como `||` (o), para evaluar varios símbolos.</span><span class="sxs-lookup"><span data-stu-id="5ef15-107">You can use the operators `==` (equality), `!=` (inequality), `&&` (and), and `||` (or), to evaluate multiple symbols.</span></span> <span data-ttu-id="5ef15-108">Es posible agrupar símbolos y operadores mediante paréntesis.</span><span class="sxs-lookup"><span data-stu-id="5ef15-108">You can also group symbols and operators with parentheses.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5ef15-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5ef15-109">Remarks</span></span>  
 <span data-ttu-id="5ef15-110">`#elif` equivale a usar:</span><span class="sxs-lookup"><span data-stu-id="5ef15-110">`#elif` is equivalent to using:</span></span>  
  
```csharp
#else  
#if  
```  
  
 <span data-ttu-id="5ef15-111">El uso de `#elif` es más simple ya que cada directiva `#if` requiere una directiva [#endif](./preprocessor-endif.md), mientras que una directiva `#elif` se puede usar sin la directiva `#endif` correspondiente.</span><span class="sxs-lookup"><span data-stu-id="5ef15-111">Using `#elif` is simpler, because each `#if` requires a [#endif](./preprocessor-endif.md), whereas a `#elif` can be used without a matching `#endif`.</span></span>  
  
 <span data-ttu-id="5ef15-112">Vea [#if](./preprocessor-if.md) para obtener un ejemplo de cómo usar `#elif`.</span><span class="sxs-lookup"><span data-stu-id="5ef15-112">See [#if](./preprocessor-if.md) for an example of how to use `#elif`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ef15-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="5ef15-113">See also</span></span>

- [<span data-ttu-id="5ef15-114">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="5ef15-114">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="5ef15-115">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="5ef15-115">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="5ef15-116">Directivas de preprocesador de C#</span><span class="sxs-lookup"><span data-stu-id="5ef15-116">C# Preprocessor Directives</span></span>](./index.md)
