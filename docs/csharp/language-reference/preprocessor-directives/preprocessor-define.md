---
title: '#define: Referencia de C#'
ms.date: 06/30/2018
f1_keywords:
- '#define'
helpviewer_keywords:
- '#define directive [C#]'
ms.assetid: 23638b8f-779c-450e-b600-d55682de7d01
ms.openlocfilehash: c08d6f42c11184a4d14aa6712f9f0f8706a72cab
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173437"
---
# <a name="define-c-reference"></a><span data-ttu-id="f53e3-102">#define (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="f53e3-102">#define (C# Reference)</span></span>
<span data-ttu-id="f53e3-103">Usa `#define` para definir un símbolo.</span><span class="sxs-lookup"><span data-stu-id="f53e3-103">You use `#define` to define a symbol.</span></span> <span data-ttu-id="f53e3-104">Si usa el símbolo como expresión que se pasa a la directiva [#if](./preprocessor-if.md), la expresión se evaluará como `true`, como se muestra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f53e3-104">When you use the symbol as the expression that's passed to the [#if](./preprocessor-if.md) directive, the expression will evaluate to `true`, as the following example shows:</span></span>  

 ```csharp
 #define DEBUG
 ```
  
## <a name="remarks"></a><span data-ttu-id="f53e3-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f53e3-105">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f53e3-106">La directiva `#define` no puede usarse para declarar valores constantes como suele hacerse en C y C++.</span><span class="sxs-lookup"><span data-stu-id="f53e3-106">The `#define` directive cannot be used to declare constant values as is typically done in C and C++.</span></span> <span data-ttu-id="f53e3-107">En C#, las constantes se definen mejor como miembros estáticos de una clase o struct.</span><span class="sxs-lookup"><span data-stu-id="f53e3-107">Constants in C# are best defined as static members of a class or struct.</span></span> <span data-ttu-id="f53e3-108">Si tiene varias constantes de este tipo, puede considerar la posibilidad de crear una clase "Constants" independiente donde incluirlas.</span><span class="sxs-lookup"><span data-stu-id="f53e3-108">If you have several such constants, consider creating a separate "Constants" class to hold them.</span></span>  
  
 <span data-ttu-id="f53e3-109">Los símbolos se pueden usar para especificar condiciones de compilación.</span><span class="sxs-lookup"><span data-stu-id="f53e3-109">Symbols can be used to specify conditions for compilation.</span></span> <span data-ttu-id="f53e3-110">Puede comprobar el símbolo tanto con [#if](./preprocessor-if.md) como con [#elif](./preprocessor-elif.md).</span><span class="sxs-lookup"><span data-stu-id="f53e3-110">You can test for the symbol with either [#if](./preprocessor-if.md) or [#elif](./preprocessor-elif.md).</span></span> <span data-ttu-id="f53e3-111">También se puede usar <xref:System.Diagnostics.ConditionalAttribute> para realizar una compilación condicional.</span><span class="sxs-lookup"><span data-stu-id="f53e3-111">You can also use the <xref:System.Diagnostics.ConditionalAttribute> to perform conditional compilation.</span></span>  
  
 <span data-ttu-id="f53e3-112">Es posible definir un símbolo, pero no asignar un valor a un símbolo.</span><span class="sxs-lookup"><span data-stu-id="f53e3-112">You can define a symbol, but you cannot assign a value to a symbol.</span></span> <span data-ttu-id="f53e3-113">La directiva `#define` debe aparecer en el archivo antes de que use cualquier instrucción que tampoco sea una directiva del preprocesador.</span><span class="sxs-lookup"><span data-stu-id="f53e3-113">The `#define` directive must appear in the file before you use any instructions that aren't also preprocessor directives.</span></span>  
  
 <span data-ttu-id="f53e3-114">También se puede definir un símbolo con la opción del compilador [-define](../compiler-options/define-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="f53e3-114">You can also define a symbol with the [-define](../compiler-options/define-compiler-option.md) compiler option.</span></span> <span data-ttu-id="f53e3-115">La definición de un símbolo se puede anular mediante [#undef](./preprocessor-undef.md).</span><span class="sxs-lookup"><span data-stu-id="f53e3-115">You can undefine a symbol with [#undef](./preprocessor-undef.md).</span></span>  
  
 <span data-ttu-id="f53e3-116">Un símbolo definido mediante `-define` o `#define` no debe entrar en conflicto con una variable del mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="f53e3-116">A symbol that you define with `-define` or with `#define` does not conflict with a variable of the same name.</span></span> <span data-ttu-id="f53e3-117">Es decir, no se debería pasar un nombre de variable a una directiva de preprocesador ni evaluar solo un símbolo mediante una directiva de preprocesador.</span><span class="sxs-lookup"><span data-stu-id="f53e3-117">That is, a variable name should not be passed to a preprocessor directive and a symbol can only be evaluated by a preprocessor directive.</span></span>  
  
 <span data-ttu-id="f53e3-118">El ámbito de un símbolo que se ha creado mediante `#define` corresponde al archivo en el que se ha definido.</span><span class="sxs-lookup"><span data-stu-id="f53e3-118">The scope of a symbol that was created by using `#define` is the file in which the symbol was defined.</span></span>  
  
 <span data-ttu-id="f53e3-119">Como se muestra en el siguiente ejemplo, debe colocar directivas `#define` en la parte superior del archivo.</span><span class="sxs-lookup"><span data-stu-id="f53e3-119">As the following example shows, you must put `#define` directives at the top of the file.</span></span>  
  
```csharp  
#define DEBUG  
//#define TRACE  
#undef TRACE  
  
using System;  
  
public class TestDefine  
{  
    static void Main()  
    {  
#if (DEBUG)  
        Console.WriteLine("Debugging is enabled.");  
#endif  
  
#if (TRACE)  
     Console.WriteLine("Tracing is enabled.");  
#endif  
    }  
}  
// Output:  
// Debugging is enabled.  
```  
  
 <span data-ttu-id="f53e3-120">Para obtener un ejemplo de cómo anular la definición de un símbolo, vea [#undef](./preprocessor-undef.md).</span><span class="sxs-lookup"><span data-stu-id="f53e3-120">For an example of how to undefine a symbol, see [#undef](./preprocessor-undef.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f53e3-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="f53e3-121">See also</span></span>

- [<span data-ttu-id="f53e3-122">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="f53e3-122">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="f53e3-123">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="f53e3-123">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="f53e3-124">Directivas de preprocesador de C#</span><span class="sxs-lookup"><span data-stu-id="f53e3-124">C# Preprocessor Directives</span></span>](./index.md)
- [<span data-ttu-id="f53e3-125">const</span><span class="sxs-lookup"><span data-stu-id="f53e3-125">const</span></span>](../keywords/const.md)
- [<span data-ttu-id="f53e3-126">Compilación condicional con Trace y Debug</span><span class="sxs-lookup"><span data-stu-id="f53e3-126">How to: Compile Conditionally with Trace and Debug</span></span>](../../../framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md)
- [<span data-ttu-id="f53e3-127">#undef</span><span class="sxs-lookup"><span data-stu-id="f53e3-127">#undef</span></span>](./preprocessor-undef.md)
- [<span data-ttu-id="f53e3-128">#if</span><span class="sxs-lookup"><span data-stu-id="f53e3-128">#if</span></span>](./preprocessor-if.md)
