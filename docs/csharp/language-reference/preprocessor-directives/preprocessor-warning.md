---
title: '#warning (Referencia de C#)'
ms.date: 07/20/2015
f1_keywords:
- '#warning'
helpviewer_keywords:
- '#warning directive [C#]'
ms.assetid: e6fb496d-bb8b-4018-baf6-5b60a0c8902b
ms.openlocfilehash: 59ca63d5089e377627a9116f24f9a0a1681bb4b2
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2018
ms.locfileid: "43461688"
---
# <a name="warning-c-reference"></a><span data-ttu-id="50c2e-102">#warning (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="50c2e-102">#warning (C# Reference)</span></span>
<span data-ttu-id="50c2e-103">`#warning` permite generar una advertencia del compilador [CS1030](../../misc/cs1030.md) de nivel uno desde una ubicación específica en el código.</span><span class="sxs-lookup"><span data-stu-id="50c2e-103">`#warning` lets you generate a [CS1030](../../misc/cs1030.md) level one compiler warning from a specific location in your code.</span></span> <span data-ttu-id="50c2e-104">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="50c2e-104">For example:</span></span>  
  
```csharp
#warning Deprecated code in this method.  
```  
  
## <a name="remarks"></a><span data-ttu-id="50c2e-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="50c2e-105">Remarks</span></span>
 <span data-ttu-id="50c2e-106">Un uso común de `#warning` es en una directiva condicional.</span><span class="sxs-lookup"><span data-stu-id="50c2e-106">A common use of `#warning` is in a conditional directive.</span></span> <span data-ttu-id="50c2e-107">También es posible generar un error definido por el usuario con [#error](../../../csharp/language-reference/preprocessor-directives/preprocessor-error.md).</span><span class="sxs-lookup"><span data-stu-id="50c2e-107">It is also possible to generate a user-defined error with [#error](../../../csharp/language-reference/preprocessor-directives/preprocessor-error.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="50c2e-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="50c2e-108">Example</span></span>  

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

## <a name="see-also"></a><span data-ttu-id="50c2e-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="50c2e-109">See Also</span></span>

- [<span data-ttu-id="50c2e-110">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="50c2e-110">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="50c2e-111">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="50c2e-111">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="50c2e-112">Directivas de preprocesador de C#</span><span class="sxs-lookup"><span data-stu-id="50c2e-112">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
