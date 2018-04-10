---
title: '#warning (Referencia de C#)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#warning'
helpviewer_keywords:
- '#warning directive [C#]'
ms.assetid: e6fb496d-bb8b-4018-baf6-5b60a0c8902b
caps.latest.revision: 9
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 8145c4a62d5179d6fa46e27186d83fc0108939d1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="warning-c-reference"></a><span data-ttu-id="277ef-102">#warning (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="277ef-102">#warning (C# Reference)</span></span>
<span data-ttu-id="277ef-103">`#warning` le permite generar una advertencia de nivel uno desde una ubicación específica en el código.</span><span class="sxs-lookup"><span data-stu-id="277ef-103">`#warning` lets you generate a level one warning from a specific location in your code.</span></span> <span data-ttu-id="277ef-104">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="277ef-104">For example:</span></span>  
  
```csharp
#warning Deprecated code in this method.  
```  
  
## <a name="remarks"></a><span data-ttu-id="277ef-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="277ef-105">Remarks</span></span>  
 <span data-ttu-id="277ef-106">Un uso común de `#warning` es en una directiva condicional.</span><span class="sxs-lookup"><span data-stu-id="277ef-106">A common use of `#warning` is in a conditional directive.</span></span> <span data-ttu-id="277ef-107">También es posible generar un error definido por el usuario con [#error](../../../csharp/language-reference/preprocessor-directives/preprocessor-error.md).</span><span class="sxs-lookup"><span data-stu-id="277ef-107">It is also possible to generate a user-defined error with [#error](../../../csharp/language-reference/preprocessor-directives/preprocessor-error.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="277ef-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="277ef-108">Example</span></span>  
  
```csharp
// preprocessor_warning.cs  
// CS1030 expected  
#define DEBUG  
class MainClass   
{  
    static void Main()   
    {  
#if DEBUG  
#warning DEBUG is defined  
#endif  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="277ef-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="277ef-109">See Also</span></span>  
 [<span data-ttu-id="277ef-110">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="277ef-110">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="277ef-111">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="277ef-111">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="277ef-112">Directivas de preprocesador de C#</span><span class="sxs-lookup"><span data-stu-id="277ef-112">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
