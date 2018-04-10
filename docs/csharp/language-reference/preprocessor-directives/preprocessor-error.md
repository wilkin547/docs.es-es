---
title: '#error (Referencia de C#)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#error'
helpviewer_keywords:
- '#error directive [C#]'
ms.assetid: f2a7f3af-4cf9-4111-b369-70204d24b26b
caps.latest.revision: 10
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 23528ae81e4ddca23c67c937ca2588ab4c982e98
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="error-c-reference"></a><span data-ttu-id="7db3e-102">#error (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="7db3e-102">#error (C# Reference)</span></span>
<span data-ttu-id="7db3e-103">`#error` le permite generar un error desde una ubicación específica en el código.</span><span class="sxs-lookup"><span data-stu-id="7db3e-103">`#error` lets you generate an error from a specific location in your code.</span></span> <span data-ttu-id="7db3e-104">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="7db3e-104">For example:</span></span>  
  
```csharp
#error Deprecated code in this method.  
```  
  
## <a name="remarks"></a><span data-ttu-id="7db3e-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7db3e-105">Remarks</span></span>  
 <span data-ttu-id="7db3e-106">Un uso común de `#error` es en una directiva condicional.</span><span class="sxs-lookup"><span data-stu-id="7db3e-106">A common use of `#error` is in a conditional directive.</span></span>  
  
 <span data-ttu-id="7db3e-107">También es posible generar una advertencia definida por el usuario con [#warning](../../../csharp/language-reference/preprocessor-directives/preprocessor-warning.md).</span><span class="sxs-lookup"><span data-stu-id="7db3e-107">It is also possible to generate a user-defined warning with [#warning](../../../csharp/language-reference/preprocessor-directives/preprocessor-warning.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7db3e-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7db3e-108">Example</span></span>  
  
```csharp
// preprocessor_error.cs  
// CS1029 expected  
#define DEBUG  
class MainClass   
{  
    static void Main()   
    {  
#if DEBUG  
#error DEBUG is defined  
#endif  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="7db3e-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="7db3e-109">See Also</span></span>  
 [<span data-ttu-id="7db3e-110">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="7db3e-110">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="7db3e-111">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="7db3e-111">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="7db3e-112">Directivas de preprocesador de C#</span><span class="sxs-lookup"><span data-stu-id="7db3e-112">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
