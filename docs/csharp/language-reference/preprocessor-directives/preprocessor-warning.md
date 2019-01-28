---
title: '#warning: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#warning'
helpviewer_keywords:
- '#warning directive [C#]'
ms.assetid: e6fb496d-bb8b-4018-baf6-5b60a0c8902b
ms.openlocfilehash: 55768a354b2841021607ed40b4ef87b9767edcad
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54620323"
---
# <a name="warning-c-reference"></a><span data-ttu-id="d70ce-102">#warning (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="d70ce-102">#warning (C# Reference)</span></span>
<span data-ttu-id="d70ce-103">`#warning` permite generar una advertencia del compilador [CS1030](../../misc/cs1030.md) de nivel uno desde una ubicación específica en el código.</span><span class="sxs-lookup"><span data-stu-id="d70ce-103">`#warning` lets you generate a [CS1030](../../misc/cs1030.md) level one compiler warning from a specific location in your code.</span></span> <span data-ttu-id="d70ce-104">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d70ce-104">For example:</span></span>  
  
```csharp
#warning Deprecated code in this method.  
```  
  
## <a name="remarks"></a><span data-ttu-id="d70ce-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d70ce-105">Remarks</span></span>
 <span data-ttu-id="d70ce-106">Un uso común de `#warning` es en una directiva condicional.</span><span class="sxs-lookup"><span data-stu-id="d70ce-106">A common use of `#warning` is in a conditional directive.</span></span> <span data-ttu-id="d70ce-107">También es posible generar un error definido por el usuario con [#error](../../../csharp/language-reference/preprocessor-directives/preprocessor-error.md).</span><span class="sxs-lookup"><span data-stu-id="d70ce-107">It is also possible to generate a user-defined error with [#error](../../../csharp/language-reference/preprocessor-directives/preprocessor-error.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d70ce-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d70ce-108">Example</span></span>  

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

## <a name="see-also"></a><span data-ttu-id="d70ce-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="d70ce-109">See also</span></span>

- [<span data-ttu-id="d70ce-110">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="d70ce-110">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="d70ce-111">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="d70ce-111">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="d70ce-112">Directivas de preprocesador de C#</span><span class="sxs-lookup"><span data-stu-id="d70ce-112">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
