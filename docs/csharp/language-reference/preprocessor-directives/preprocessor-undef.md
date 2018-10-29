---
title: '#undef (Referencia de C#)'
ms.date: 06/30/2018
f1_keywords:
- '#undef'
helpviewer_keywords:
- '#undef directive [C#]'
ms.assetid: 686c92d2-7194-4be4-b2f4-80091712d513
ms.openlocfilehash: 3957d58f61e51fab01618f5e1146be9cd0da58fd
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2018
ms.locfileid: "48034589"
---
# <a name="undef-c-reference"></a><span data-ttu-id="2406a-102">#undef (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="2406a-102">#undef (C# Reference)</span></span>
<span data-ttu-id="2406a-103">`#undef` le permite anular la definición de un símbolo, de tal forma que, si se usa como la expresión en una directiva [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md), la expresión se evaluará como `false`.</span><span class="sxs-lookup"><span data-stu-id="2406a-103">`#undef` lets you undefine a symbol, such that, by using the symbol as the expression in a [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) directive, the expression will evaluate to `false`.</span></span>  
  
 <span data-ttu-id="2406a-104">Un símbolo se puede definir con la directiva [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) o la opción del compilador [-define](../../../csharp/language-reference/compiler-options/define-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="2406a-104">A symbol can be defined either with the [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) directive or the [-define](../../../csharp/language-reference/compiler-options/define-compiler-option.md) compiler option.</span></span> <span data-ttu-id="2406a-105">La directiva `#undef` debe aparecer en el archivo antes de que use cualquier instrucción que tampoco sea una directiva.</span><span class="sxs-lookup"><span data-stu-id="2406a-105">The `#undef` directive must appear in the file before you use any statements that are not also directives.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2406a-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2406a-106">Example</span></span>  

```csharp
// preprocessor_undef.cs  
// compile with: /d:DEBUG  
#undef DEBUG  
using System;  
class MyClass
{  
    static void Main()
    {  
#if DEBUG  
        Console.WriteLine("DEBUG is defined");  
#else  
        Console.WriteLine("DEBUG is not defined");  
#endif  
    }  
}  
```

<span data-ttu-id="2406a-107">**DEBUG está sin definirse**</span><span class="sxs-lookup"><span data-stu-id="2406a-107">**DEBUG is not defined**</span></span>

## <a name="see-also"></a><span data-ttu-id="2406a-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="2406a-108">See Also</span></span>

- [<span data-ttu-id="2406a-109">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="2406a-109">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="2406a-110">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="2406a-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="2406a-111">Directivas de preprocesador de C#</span><span class="sxs-lookup"><span data-stu-id="2406a-111">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
