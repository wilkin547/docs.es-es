---
title: '#<a name="region-c-reference"></a>region (Referencia de C#)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: '#region'
helpviewer_keywords: '#region directive [C#]'
ms.assetid: 672c87d1-9771-4f64-ab3f-0ad3d4ffb2b4
caps.latest.revision: "12"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: cce4a8ac79c4687280e28618d8863d16cd193a3b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="region-c-reference"></a><span data-ttu-id="d75d1-102">#region (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="d75d1-102">#region (C# Reference)</span></span>
<span data-ttu-id="d75d1-103">`#region` permite especificar un bloque de código que se puede expandir o contraer cuando se usa la característica de [esquematización](/visualstudio/ide/outlining) del editor de código de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d75d1-103">`#region` lets you specify a block of code that you can expand or collapse when using the [outlining](/visualstudio/ide/outlining) feature of the Visual Studio Code Editor.</span></span> <span data-ttu-id="d75d1-104">En archivos de código más largos, es conveniente poder contraer u ocultar una o varias regiones para poder centrarse en la parte del archivo en la que se está trabajando actualmente.</span><span class="sxs-lookup"><span data-stu-id="d75d1-104">In longer code files, it is convenient to be able to collapse or hide one or more regions so that you can focus on the part of the file that you are currently working on.</span></span> <span data-ttu-id="d75d1-105">En el ejemplo siguiente se muestra cómo definir una región:</span><span class="sxs-lookup"><span data-stu-id="d75d1-105">The following example shows how to define a region:</span></span>  
  
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
  
## <a name="remarks"></a><span data-ttu-id="d75d1-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d75d1-106">Remarks</span></span>  
 <span data-ttu-id="d75d1-107">Un bloque `#region` se debe terminar con una directiva [#endregion](../../../csharp/language-reference/preprocessor-directives/preprocessor-endregion.md).</span><span class="sxs-lookup"><span data-stu-id="d75d1-107">A `#region` block must be terminated with a [#endregion](../../../csharp/language-reference/preprocessor-directives/preprocessor-endregion.md) directive.</span></span>  
  
 <span data-ttu-id="d75d1-108">Un bloque `#region` no se puede superponer con un bloque [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md).</span><span class="sxs-lookup"><span data-stu-id="d75d1-108">A `#region` block cannot overlap with a [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) block.</span></span> <span data-ttu-id="d75d1-109">Pero, un bloque `#region` se puede anidar en un bloque `#if` y un bloque `#if` se puede anidar en un bloque `#region`.</span><span class="sxs-lookup"><span data-stu-id="d75d1-109">However, a `#region` block can be nested in a `#if` block, and a `#if` block can be nested in a `#region` block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d75d1-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="d75d1-110">See Also</span></span>  
 [<span data-ttu-id="d75d1-111">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="d75d1-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="d75d1-112">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="d75d1-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="d75d1-113">Directivas de preprocesador de C#</span><span class="sxs-lookup"><span data-stu-id="d75d1-113">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
