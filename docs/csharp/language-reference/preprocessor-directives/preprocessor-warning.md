---
description: '#warning: Referencia de C#'
title: '#warning: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- '#warning'
helpviewer_keywords:
- '#warning directive [C#]'
ms.assetid: e6fb496d-bb8b-4018-baf6-5b60a0c8902b
ms.openlocfilehash: 9ade723bdca17597dcd56240f506e60f2debf6be
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91186424"
---
# <a name="warning-c-reference"></a><span data-ttu-id="15e12-103">#warning (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="15e12-103">#warning (C# Reference)</span></span>

<span data-ttu-id="15e12-104">`#warning` permite generar una advertencia del compilador [CS1030](../../misc/cs1030.md) de nivel uno desde una ubicación específica en el código.</span><span class="sxs-lookup"><span data-stu-id="15e12-104">`#warning` lets you generate a [CS1030](../../misc/cs1030.md) level one compiler warning from a specific location in your code.</span></span> <span data-ttu-id="15e12-105">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="15e12-105">For example:</span></span>  
  
```csharp
#warning Deprecated code in this method.  
```  
  
## <a name="remarks"></a><span data-ttu-id="15e12-106">Observaciones</span><span class="sxs-lookup"><span data-stu-id="15e12-106">Remarks</span></span>

 <span data-ttu-id="15e12-107">Un uso común de `#warning` es en una directiva condicional.</span><span class="sxs-lookup"><span data-stu-id="15e12-107">A common use of `#warning` is in a conditional directive.</span></span> <span data-ttu-id="15e12-108">También es posible generar un error definido por el usuario con [#error](./preprocessor-error.md).</span><span class="sxs-lookup"><span data-stu-id="15e12-108">It is also possible to generate a user-defined error with [#error](./preprocessor-error.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="15e12-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="15e12-109">Example</span></span>  

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

## <a name="see-also"></a><span data-ttu-id="15e12-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="15e12-110">See also</span></span>

- [<span data-ttu-id="15e12-111">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="15e12-111">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="15e12-112">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="15e12-112">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="15e12-113">Directivas de preprocesador de C#</span><span class="sxs-lookup"><span data-stu-id="15e12-113">C# Preprocessor Directives</span></span>](./index.md)
