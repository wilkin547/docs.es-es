---
title: '#error: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- '#error'
helpviewer_keywords:
- '#error directive [C#]'
ms.assetid: f2a7f3af-4cf9-4111-b369-70204d24b26b
ms.openlocfilehash: 7203e1271da66e78bfbd70717b0f5e536a7ebd86
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712525"
---
# <a name="error-c-reference"></a><span data-ttu-id="510c1-102">#error (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="510c1-102">#error (C# Reference)</span></span>
<span data-ttu-id="510c1-103">`#error` permite generar un error [CS1029](../compiler-messages/cs1029.md) definido por el usuario desde una ubicación específica en el código.</span><span class="sxs-lookup"><span data-stu-id="510c1-103">`#error` lets you generate a [CS1029](../compiler-messages/cs1029.md) user-defined error from a specific location in your code.</span></span> <span data-ttu-id="510c1-104">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="510c1-104">For example:</span></span>  
  
```csharp
#error Deprecated code in this method.  
```  
  
## <a name="remarks"></a><span data-ttu-id="510c1-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="510c1-105">Remarks</span></span>  
 <span data-ttu-id="510c1-106">Un uso común de `#error` es en una directiva condicional.</span><span class="sxs-lookup"><span data-stu-id="510c1-106">A common use of `#error` is in a conditional directive.</span></span>  
  
 <span data-ttu-id="510c1-107">También es posible generar una advertencia definida por el usuario con [#warning](./preprocessor-warning.md).</span><span class="sxs-lookup"><span data-stu-id="510c1-107">It is also possible to generate a user-defined warning with [#warning](./preprocessor-warning.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="510c1-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="510c1-108">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="510c1-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="510c1-109">See also</span></span>

- [<span data-ttu-id="510c1-110">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="510c1-110">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="510c1-111">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="510c1-111">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="510c1-112">Directivas de preprocesador de C#</span><span class="sxs-lookup"><span data-stu-id="510c1-112">C# Preprocessor Directives</span></span>](./index.md)
