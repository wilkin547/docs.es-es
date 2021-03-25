---
description: '#define: Referencia de C#'
title: '#define: Referencia de C#'
ms.date: 06/30/2018
f1_keywords:
- '#define'
helpviewer_keywords:
- '#define directive [C#]'
ms.assetid: 23638b8f-779c-450e-b600-d55682de7d01
ms.openlocfilehash: dddc60b99a55762ae26a470fcd6b6a0e9b98bcf8
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "103480356"
---
# <a name="define-c-reference"></a><span data-ttu-id="d4b1e-103">#define (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="d4b1e-103">#define (C# Reference)</span></span>

<span data-ttu-id="d4b1e-104">Usa `#define` para definir un símbolo.</span><span class="sxs-lookup"><span data-stu-id="d4b1e-104">You use `#define` to define a symbol.</span></span> <span data-ttu-id="d4b1e-105">Si usa el símbolo como expresión que se pasa a la directiva [#if](./preprocessor-if.md), la expresión se evaluará como `true`, como se muestra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d4b1e-105">When you use the symbol as the expression that's passed to the [#if](./preprocessor-if.md) directive, the expression will evaluate to `true`, as the following example shows:</span></span>  

 ```csharp
 #define DEBUG
 ```
  
## <a name="remarks"></a><span data-ttu-id="d4b1e-106">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d4b1e-106">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d4b1e-107">La directiva `#define` no puede usarse para declarar valores constantes como suele hacerse en C y C++.</span><span class="sxs-lookup"><span data-stu-id="d4b1e-107">The `#define` directive cannot be used to declare constant values as is typically done in C and C++.</span></span> <span data-ttu-id="d4b1e-108">En C#, las constantes se definen mejor como miembros estáticos de una clase o struct.</span><span class="sxs-lookup"><span data-stu-id="d4b1e-108">Constants in C# are best defined as static members of a class or struct.</span></span> <span data-ttu-id="d4b1e-109">Si tiene varias constantes de este tipo, puede considerar la posibilidad de crear una clase "Constants" independiente donde incluirlas.</span><span class="sxs-lookup"><span data-stu-id="d4b1e-109">If you have several such constants, consider creating a separate "Constants" class to hold them.</span></span>  
  
 <span data-ttu-id="d4b1e-110">Los símbolos se pueden usar para especificar condiciones de compilación.</span><span class="sxs-lookup"><span data-stu-id="d4b1e-110">Symbols can be used to specify conditions for compilation.</span></span> <span data-ttu-id="d4b1e-111">Puede comprobar el símbolo tanto con [#if](./preprocessor-if.md) como con [#elif](./preprocessor-elif.md).</span><span class="sxs-lookup"><span data-stu-id="d4b1e-111">You can test for the symbol with either [#if](./preprocessor-if.md) or [#elif](./preprocessor-elif.md).</span></span> <span data-ttu-id="d4b1e-112">También se puede usar <xref:System.Diagnostics.ConditionalAttribute> para realizar una compilación condicional.</span><span class="sxs-lookup"><span data-stu-id="d4b1e-112">You can also use the <xref:System.Diagnostics.ConditionalAttribute> to perform conditional compilation.</span></span>  
  
 <span data-ttu-id="d4b1e-113">Es posible definir un símbolo, pero no asignar un valor a un símbolo.</span><span class="sxs-lookup"><span data-stu-id="d4b1e-113">You can define a symbol, but you cannot assign a value to a symbol.</span></span> <span data-ttu-id="d4b1e-114">La directiva `#define` debe aparecer en el archivo antes de que use cualquier instrucción que tampoco sea una directiva del preprocesador.</span><span class="sxs-lookup"><span data-stu-id="d4b1e-114">The `#define` directive must appear in the file before you use any instructions that aren't also preprocessor directives.</span></span>  
  
 <span data-ttu-id="d4b1e-115">También se puede definir un símbolo con la opción del compilador [**DefineConstants**](../compiler-options/language.md#defineconstants).</span><span class="sxs-lookup"><span data-stu-id="d4b1e-115">You can also define a symbol with the [**DefineConstants**](../compiler-options/language.md#defineconstants) compiler option.</span></span> <span data-ttu-id="d4b1e-116">La definición de un símbolo se puede anular mediante [#undef](./preprocessor-undef.md).</span><span class="sxs-lookup"><span data-stu-id="d4b1e-116">You can undefine a symbol with [#undef](./preprocessor-undef.md).</span></span>  
  
 <span data-ttu-id="d4b1e-117">Un símbolo definido mediante `-define` o `#define` no debe entrar en conflicto con una variable del mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="d4b1e-117">A symbol that you define with `-define` or with `#define` does not conflict with a variable of the same name.</span></span> <span data-ttu-id="d4b1e-118">Es decir, no se debería pasar un nombre de variable a una directiva de preprocesador ni evaluar solo un símbolo mediante una directiva de preprocesador.</span><span class="sxs-lookup"><span data-stu-id="d4b1e-118">That is, a variable name should not be passed to a preprocessor directive and a symbol can only be evaluated by a preprocessor directive.</span></span>  
  
 <span data-ttu-id="d4b1e-119">El ámbito de un símbolo que se ha creado mediante `#define` corresponde al archivo en el que se ha definido.</span><span class="sxs-lookup"><span data-stu-id="d4b1e-119">The scope of a symbol that was created by using `#define` is the file in which the symbol was defined.</span></span>  
  
 <span data-ttu-id="d4b1e-120">Como se muestra en el siguiente ejemplo, debe colocar directivas `#define` en la parte superior del archivo.</span><span class="sxs-lookup"><span data-stu-id="d4b1e-120">As the following example shows, you must put `#define` directives at the top of the file.</span></span>  
  
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
  
 <span data-ttu-id="d4b1e-121">Para obtener un ejemplo de cómo anular la definición de un símbolo, vea [#undef](./preprocessor-undef.md).</span><span class="sxs-lookup"><span data-stu-id="d4b1e-121">For an example of how to undefine a symbol, see [#undef](./preprocessor-undef.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4b1e-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="d4b1e-122">See also</span></span>

- [<span data-ttu-id="d4b1e-123">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="d4b1e-123">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="d4b1e-124">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="d4b1e-124">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="d4b1e-125">Directivas de preprocesador de C#</span><span class="sxs-lookup"><span data-stu-id="d4b1e-125">C# Preprocessor Directives</span></span>](./index.md)
- [<span data-ttu-id="d4b1e-126">const</span><span class="sxs-lookup"><span data-stu-id="d4b1e-126">const</span></span>](../keywords/const.md)
- [<span data-ttu-id="d4b1e-127">Cómo: Compilación condicional con Trace y Debug</span><span class="sxs-lookup"><span data-stu-id="d4b1e-127">How to: Compile Conditionally with Trace and Debug</span></span>](../../../framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md)
- [<span data-ttu-id="d4b1e-128">#undef</span><span class="sxs-lookup"><span data-stu-id="d4b1e-128">#undef</span></span>](./preprocessor-undef.md)
- [<span data-ttu-id="d4b1e-129">#if</span><span class="sxs-lookup"><span data-stu-id="d4b1e-129">#if</span></span>](./preprocessor-if.md)
