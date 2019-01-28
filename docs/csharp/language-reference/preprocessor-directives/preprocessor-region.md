---
title: '#region: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#region'
helpviewer_keywords:
- '#region directive [C#]'
ms.assetid: 672c87d1-9771-4f64-ab3f-0ad3d4ffb2b4
ms.openlocfilehash: adaa58fc47da557a31270e99ff8a1dae3d0731bb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54724036"
---
# <a name="region-c-reference"></a><span data-ttu-id="96683-102">#region (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="96683-102">#region (C# Reference)</span></span>
<span data-ttu-id="96683-103">`#region` permite especificar un bloque de código que se puede expandir o contraer cuando se usa la característica de [esquematización](/visualstudio/ide/outlining) del editor de código de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="96683-103">`#region` lets you specify a block of code that you can expand or collapse when using the [outlining](/visualstudio/ide/outlining) feature of the Visual Studio Code Editor.</span></span> <span data-ttu-id="96683-104">En archivos de código más largos, es conveniente poder contraer u ocultar una o varias regiones para poder centrarse en la parte del archivo en la que se está trabajando actualmente.</span><span class="sxs-lookup"><span data-stu-id="96683-104">In longer code files, it is convenient to be able to collapse or hide one or more regions so that you can focus on the part of the file that you are currently working on.</span></span> <span data-ttu-id="96683-105">En el ejemplo siguiente se muestra cómo definir una región:</span><span class="sxs-lookup"><span data-stu-id="96683-105">The following example shows how to define a region:</span></span>  
  
```csharp
#region MyClass definition  
public class MyClass   
{  
    static void Main()   
    {  
    }  
}  
#endregion  
```  
  
## <a name="remarks"></a><span data-ttu-id="96683-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="96683-106">Remarks</span></span>  
 <span data-ttu-id="96683-107">Un bloque `#region` se debe terminar con una directiva [#endregion](../../../csharp/language-reference/preprocessor-directives/preprocessor-endregion.md).</span><span class="sxs-lookup"><span data-stu-id="96683-107">A `#region` block must be terminated with a [#endregion](../../../csharp/language-reference/preprocessor-directives/preprocessor-endregion.md) directive.</span></span>  
  
 <span data-ttu-id="96683-108">Un bloque `#region` no se puede superponer con un bloque [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md).</span><span class="sxs-lookup"><span data-stu-id="96683-108">A `#region` block cannot overlap with a [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) block.</span></span> <span data-ttu-id="96683-109">Pero, un bloque `#region` se puede anidar en un bloque `#if` y un bloque `#if` se puede anidar en un bloque `#region`.</span><span class="sxs-lookup"><span data-stu-id="96683-109">However, a `#region` block can be nested in a `#if` block, and a `#if` block can be nested in a `#region` block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96683-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="96683-110">See also</span></span>

- [<span data-ttu-id="96683-111">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="96683-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="96683-112">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="96683-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="96683-113">Directivas de preprocesador de C#</span><span class="sxs-lookup"><span data-stu-id="96683-113">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
