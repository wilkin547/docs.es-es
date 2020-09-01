---
description: '#region: Referencia de C#'
title: '#region: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- '#region'
helpviewer_keywords:
- '#region directive [C#]'
ms.assetid: 672c87d1-9771-4f64-ab3f-0ad3d4ffb2b4
ms.openlocfilehash: ed40d895fedb9be271bb389a4f8de69d7ae3f266
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89137947"
---
# <a name="region-c-reference"></a><span data-ttu-id="b4448-103">#region (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="b4448-103">#region (C# Reference)</span></span>
<span data-ttu-id="b4448-104">`#region` permite especificar un bloque de código que se puede expandir o contraer cuando se usa la característica de [esquematización](/visualstudio/ide/outlining) del editor de código.</span><span class="sxs-lookup"><span data-stu-id="b4448-104">`#region` lets you specify a block of code that you can expand or collapse when using the [outlining](/visualstudio/ide/outlining) feature of the code editor.</span></span> <span data-ttu-id="b4448-105">En archivos de código más largos, es conveniente poder contraer u ocultar una o varias regiones para poder centrarse en la parte del archivo en la que se está trabajando actualmente.</span><span class="sxs-lookup"><span data-stu-id="b4448-105">In longer code files, it is convenient to be able to collapse or hide one or more regions so that you can focus on the part of the file that you are currently working on.</span></span> <span data-ttu-id="b4448-106">En el ejemplo siguiente se muestra cómo definir una región:</span><span class="sxs-lookup"><span data-stu-id="b4448-106">The following example shows how to define a region:</span></span>  
  
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
  
## <a name="remarks"></a><span data-ttu-id="b4448-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b4448-107">Remarks</span></span>  
 <span data-ttu-id="b4448-108">Un bloque `#region` se debe terminar con una directiva [#endregion](./preprocessor-endregion.md).</span><span class="sxs-lookup"><span data-stu-id="b4448-108">A `#region` block must be terminated with a [#endregion](./preprocessor-endregion.md) directive.</span></span>  
  
 <span data-ttu-id="b4448-109">Un bloque `#region` no se puede superponer con un bloque [#if](./preprocessor-if.md).</span><span class="sxs-lookup"><span data-stu-id="b4448-109">A `#region` block cannot overlap with a [#if](./preprocessor-if.md) block.</span></span> <span data-ttu-id="b4448-110">Pero, un bloque `#region` se puede anidar en un bloque `#if` y un bloque `#if` se puede anidar en un bloque `#region`.</span><span class="sxs-lookup"><span data-stu-id="b4448-110">However, a `#region` block can be nested in a `#if` block, and a `#if` block can be nested in a `#region` block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4448-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="b4448-111">See also</span></span>

- [<span data-ttu-id="b4448-112">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="b4448-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="b4448-113">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="b4448-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="b4448-114">Directivas de preprocesador de C#</span><span class="sxs-lookup"><span data-stu-id="b4448-114">C# Preprocessor Directives</span></span>](./index.md)
