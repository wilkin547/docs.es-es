---
title: '#error: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- '#error'
helpviewer_keywords:
- '#error directive [C#]'
ms.assetid: f2a7f3af-4cf9-4111-b369-70204d24b26b
ms.openlocfilehash: 28e77304edee617adc1422e6a52d0a617cd9b3bb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173411"
---
# <a name="error-c-reference"></a><span data-ttu-id="e29a3-102">#error (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="e29a3-102">#error (C# Reference)</span></span>
<span data-ttu-id="e29a3-103">`#error` permite generar un error [CS1029](../compiler-messages/cs1029.md) definido por el usuario desde una ubicación específica en el código.</span><span class="sxs-lookup"><span data-stu-id="e29a3-103">`#error` lets you generate a [CS1029](../compiler-messages/cs1029.md) user-defined error from a specific location in your code.</span></span> <span data-ttu-id="e29a3-104">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e29a3-104">For example:</span></span>  
  
```csharp
#error Deprecated code in this method.  
```  
  
## <a name="remarks"></a><span data-ttu-id="e29a3-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e29a3-105">Remarks</span></span>  
 <span data-ttu-id="e29a3-106">Un uso común de `#error` es en una directiva condicional.</span><span class="sxs-lookup"><span data-stu-id="e29a3-106">A common use of `#error` is in a conditional directive.</span></span>  
  
 <span data-ttu-id="e29a3-107">También es posible generar una advertencia definida por el usuario con [#warning](./preprocessor-warning.md).</span><span class="sxs-lookup"><span data-stu-id="e29a3-107">It is also possible to generate a user-defined warning with [#warning](./preprocessor-warning.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e29a3-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e29a3-108">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e29a3-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="e29a3-109">See also</span></span>

- [<span data-ttu-id="e29a3-110">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="e29a3-110">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="e29a3-111">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="e29a3-111">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="e29a3-112">Directivas de preprocesador de C#</span><span class="sxs-lookup"><span data-stu-id="e29a3-112">C# Preprocessor Directives</span></span>](./index.md)
