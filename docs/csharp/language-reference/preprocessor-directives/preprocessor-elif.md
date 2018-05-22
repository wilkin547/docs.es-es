---
title: '#elif (Referencia de C#)'
ms.date: 07/20/2015
f1_keywords:
- '#elif'
helpviewer_keywords:
- '#elif directive [C#]'
ms.assetid: 731d78df-08e0-4d51-b8c8-f193c27de13f
ms.openlocfilehash: ecc5c4b48790d0cb6825883922f3903414bb2b26
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="elif-c-reference"></a><span data-ttu-id="b3dae-102">#elif (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="b3dae-102">#elif (C# Reference)</span></span>
<span data-ttu-id="b3dae-103">`#elif` permite crear una directiva condicional compuesta.</span><span class="sxs-lookup"><span data-stu-id="b3dae-103">`#elif` lets you create a compound conditional directive.</span></span> <span data-ttu-id="b3dae-104">La expresión `#elif` se evaluará si ninguna de las expresiones de las directivas [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) o `#elif` (opcional) precedentes se evalúan como `true`.</span><span class="sxs-lookup"><span data-stu-id="b3dae-104">The `#elif` expression will be evaluated if neither the preceding [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) nor any preceding, optional, `#elif` directive expressions evaluate to `true`.</span></span> <span data-ttu-id="b3dae-105">Si una expresión `#elif` se evalúa como `true`, el compilador incluye en la compilación todo el código comprendido entre `#elif` y la siguiente directiva condicional.</span><span class="sxs-lookup"><span data-stu-id="b3dae-105">If a `#elif` expression evaluates to `true`, the compiler evaluates all the code between the `#elif` and the next conditional directive.</span></span> <span data-ttu-id="b3dae-106">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b3dae-106">For example:</span></span>  
  
```csharp
#define VC7  
//...  
#if debug  
    Console.Writeline("Debug build");  
#elif VC7  
    Console.Writeline("Visual Studio 7");  
#endif  
```  
  
 <span data-ttu-id="b3dae-107">Se pueden usar los operadores `==` (igualdad), `!=` (desigualdad), `&&` (y), así como `||` (o), para evaluar varios símbolos.</span><span class="sxs-lookup"><span data-stu-id="b3dae-107">You can use the operators `==` (equality), `!=` (inequality), `&&` (and), and `||` (or), to evaluate multiple symbols.</span></span> <span data-ttu-id="b3dae-108">Es posible agrupar símbolos y operadores mediante paréntesis.</span><span class="sxs-lookup"><span data-stu-id="b3dae-108">You can also group symbols and operators with parentheses.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b3dae-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b3dae-109">Remarks</span></span>  
 <span data-ttu-id="b3dae-110">`#elif` equivale a usar:</span><span class="sxs-lookup"><span data-stu-id="b3dae-110">`#elif` is equivalent to using:</span></span>  
  
```csharp
#else  
#if  
```  
  
 <span data-ttu-id="b3dae-111">El uso de `#elif` es más simple ya que cada directiva `#if` requiere una directiva [#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md), mientras que una directiva `#elif` se puede usar sin la directiva `#endif` correspondiente.</span><span class="sxs-lookup"><span data-stu-id="b3dae-111">Using `#elif` is simpler, because each `#if` requires a [#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md), whereas a `#elif` can be used without a matching `#endif`.</span></span>  
  
 <span data-ttu-id="b3dae-112">Vea [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) para obtener un ejemplo de cómo usar `#elif`.</span><span class="sxs-lookup"><span data-stu-id="b3dae-112">See [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) for an example of how to use `#elif`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3dae-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="b3dae-113">See Also</span></span>  
 [<span data-ttu-id="b3dae-114">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="b3dae-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="b3dae-115">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="b3dae-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="b3dae-116">Directivas de preprocesador de C#</span><span class="sxs-lookup"><span data-stu-id="b3dae-116">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
