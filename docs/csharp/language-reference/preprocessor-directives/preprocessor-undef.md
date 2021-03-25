---
description: '#undef: Referencia de C#'
title: '#undef: Referencia de C#'
ms.date: 06/30/2018
f1_keywords:
- '#undef'
helpviewer_keywords:
- '#undef directive [C#]'
ms.assetid: 686c92d2-7194-4be4-b2f4-80091712d513
ms.openlocfilehash: ecbf8f5793e70c7dd6e602a3992ee3783a76c7ca
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "103477977"
---
# <a name="undef-c-reference"></a><span data-ttu-id="8baa2-103">#undef (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="8baa2-103">#undef (C# Reference)</span></span>

<span data-ttu-id="8baa2-104">`#undef` le permite anular la definición de un símbolo, de tal forma que, si se usa como la expresión en una directiva [#if](./preprocessor-if.md), la expresión se evaluará como `false`.</span><span class="sxs-lookup"><span data-stu-id="8baa2-104">`#undef` lets you undefine a symbol, such that, by using the symbol as the expression in a [#if](./preprocessor-if.md) directive, the expression will evaluate to `false`.</span></span>  
  
 <span data-ttu-id="8baa2-105">Un símbolo se puede definir con la directiva [#define](./preprocessor-define.md) o la [opción del compilador **DefineConstants**](../compiler-options/language.md#defineconstants).</span><span class="sxs-lookup"><span data-stu-id="8baa2-105">A symbol can be defined either with the [#define](./preprocessor-define.md) directive or the [**DefineConstants**](../compiler-options/language.md#defineconstants) compiler option.</span></span> <span data-ttu-id="8baa2-106">La directiva `#undef` debe aparecer en el archivo antes de que use cualquier instrucción que tampoco sea una directiva.</span><span class="sxs-lookup"><span data-stu-id="8baa2-106">The `#undef` directive must appear in the file before you use any statements that are not also directives.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8baa2-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8baa2-107">Example</span></span>  

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

<span data-ttu-id="8baa2-108">**DEBUG está sin definirse**</span><span class="sxs-lookup"><span data-stu-id="8baa2-108">**DEBUG is not defined**</span></span>

## <a name="see-also"></a><span data-ttu-id="8baa2-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="8baa2-109">See also</span></span>

- [<span data-ttu-id="8baa2-110">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="8baa2-110">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="8baa2-111">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="8baa2-111">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="8baa2-112">Directivas de preprocesador de C#</span><span class="sxs-lookup"><span data-stu-id="8baa2-112">C# Preprocessor Directives</span></span>](./index.md)
