---
title: '#warning: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- '#warning'
helpviewer_keywords:
- '#warning directive [C#]'
ms.assetid: e6fb496d-bb8b-4018-baf6-5b60a0c8902b
ms.openlocfilehash: 38c3807a696599390667060d3bf374c68845fed0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75715070"
---
# <a name="warning-c-reference"></a><span data-ttu-id="ec4fb-102">#warning (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="ec4fb-102">#warning (C# Reference)</span></span>
<span data-ttu-id="ec4fb-103">`#warning` permite generar una advertencia del compilador [CS1030](../../misc/cs1030.md) de nivel uno desde una ubicación específica en el código.</span><span class="sxs-lookup"><span data-stu-id="ec4fb-103">`#warning` lets you generate a [CS1030](../../misc/cs1030.md) level one compiler warning from a specific location in your code.</span></span> <span data-ttu-id="ec4fb-104">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="ec4fb-104">For example:</span></span>  
  
```csharp
#warning Deprecated code in this method.  
```  
  
## <a name="remarks"></a><span data-ttu-id="ec4fb-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ec4fb-105">Remarks</span></span>
 <span data-ttu-id="ec4fb-106">Un uso común de `#warning` es en una directiva condicional.</span><span class="sxs-lookup"><span data-stu-id="ec4fb-106">A common use of `#warning` is in a conditional directive.</span></span> <span data-ttu-id="ec4fb-107">También es posible generar un error definido por el usuario con [#error](./preprocessor-error.md).</span><span class="sxs-lookup"><span data-stu-id="ec4fb-107">It is also possible to generate a user-defined error with [#error](./preprocessor-error.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ec4fb-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ec4fb-108">Example</span></span>  

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

## <a name="see-also"></a><span data-ttu-id="ec4fb-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="ec4fb-109">See also</span></span>

- [<span data-ttu-id="ec4fb-110">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="ec4fb-110">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="ec4fb-111">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="ec4fb-111">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="ec4fb-112">Directivas de preprocesador de C#</span><span class="sxs-lookup"><span data-stu-id="ec4fb-112">C# Preprocessor Directives</span></span>](./index.md)
