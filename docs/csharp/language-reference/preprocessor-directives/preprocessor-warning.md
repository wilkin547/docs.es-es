---
description: '#warning: Referencia de C#'
title: '#warning: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- '#warning'
helpviewer_keywords:
- '#warning directive [C#]'
ms.assetid: e6fb496d-bb8b-4018-baf6-5b60a0c8902b
ms.openlocfilehash: ab2cc5120492fc2a4b94296eb85e563c0a1d5ad3
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89137843"
---
# <a name="warning-c-reference"></a><span data-ttu-id="f5677-103">#warning (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="f5677-103">#warning (C# Reference)</span></span>
<span data-ttu-id="f5677-104">`#warning` permite generar una advertencia del compilador [CS1030](../../misc/cs1030.md) de nivel uno desde una ubicación específica en el código.</span><span class="sxs-lookup"><span data-stu-id="f5677-104">`#warning` lets you generate a [CS1030](../../misc/cs1030.md) level one compiler warning from a specific location in your code.</span></span> <span data-ttu-id="f5677-105">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f5677-105">For example:</span></span>  
  
```csharp
#warning Deprecated code in this method.  
```  
  
## <a name="remarks"></a><span data-ttu-id="f5677-106">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f5677-106">Remarks</span></span>
 <span data-ttu-id="f5677-107">Un uso común de `#warning` es en una directiva condicional.</span><span class="sxs-lookup"><span data-stu-id="f5677-107">A common use of `#warning` is in a conditional directive.</span></span> <span data-ttu-id="f5677-108">También es posible generar un error definido por el usuario con [#error](./preprocessor-error.md).</span><span class="sxs-lookup"><span data-stu-id="f5677-108">It is also possible to generate a user-defined error with [#error](./preprocessor-error.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f5677-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f5677-109">Example</span></span>  

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

## <a name="see-also"></a><span data-ttu-id="f5677-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="f5677-110">See also</span></span>

- [<span data-ttu-id="f5677-111">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="f5677-111">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="f5677-112">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="f5677-112">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="f5677-113">Directivas de preprocesador de C#</span><span class="sxs-lookup"><span data-stu-id="f5677-113">C# Preprocessor Directives</span></span>](./index.md)
