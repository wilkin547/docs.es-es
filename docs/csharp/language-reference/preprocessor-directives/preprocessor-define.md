---
title: '#<a name="define-c-reference"></a>define (Referencia de C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#define'
dev_langs:
- CSharp
helpviewer_keywords:
- '#define directive [C#]'
ms.assetid: 23638b8f-779c-450e-b600-d55682de7d01
caps.latest.revision: 22
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 8ace15f79480c9aeb0fcb4c7d46c207d4904cef0
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="define-c-reference"></a><span data-ttu-id="ef324-102">#define (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="ef324-102">#define (C# Reference)</span></span>
<span data-ttu-id="ef324-103">Usa `#define` para definir un símbolo.</span><span class="sxs-lookup"><span data-stu-id="ef324-103">You use `#define` to define a symbol.</span></span> <span data-ttu-id="ef324-104">Si usa el símbolo como expresión que se pasa a la directiva [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md), la expresión se evaluará como `true`, como se muestra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="ef324-104">When you use the symbol as the expression that's passed to the [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) directive, the expression will evaluate to `true`, as the following example shows:</span></span>  
  
 <span data-ttu-id="ef324-105">`#`  `define`   `DEBUG`</span><span class="sxs-lookup"><span data-stu-id="ef324-105">`#`  `define`   `DEBUG`</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ef324-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ef324-106">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ef324-107">La directiva `#define` no puede usarse para declarar valores constantes como suele hacerse en C y C++.</span><span class="sxs-lookup"><span data-stu-id="ef324-107">The `#define` directive cannot be used to declare constant values as is typically done in C and C++.</span></span> <span data-ttu-id="ef324-108">En C#, las constantes se definen mejor como miembros estáticos de una clase o struct.</span><span class="sxs-lookup"><span data-stu-id="ef324-108">Constants in C# are best defined as static members of a class or struct.</span></span> <span data-ttu-id="ef324-109">Si tiene varias constantes de este tipo, puede considerar la posibilidad de crear una clase "Constants" independiente donde incluirlas.</span><span class="sxs-lookup"><span data-stu-id="ef324-109">If you have several such constants, consider creating a separate "Constants" class to hold them.</span></span>  
  
 <span data-ttu-id="ef324-110">Los símbolos se pueden usar para especificar condiciones de compilación.</span><span class="sxs-lookup"><span data-stu-id="ef324-110">Symbols can be used to specify conditions for compilation.</span></span> <span data-ttu-id="ef324-111">Puede comprobar el símbolo tanto con [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) como con [#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md).</span><span class="sxs-lookup"><span data-stu-id="ef324-111">You can test for the symbol with either [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) or [#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md).</span></span> <span data-ttu-id="ef324-112">También se puede usar el atributo `conditional` para realizar una compilación condicional.</span><span class="sxs-lookup"><span data-stu-id="ef324-112">You can also use the `conditional` attribute to perform conditional compilation.</span></span>  
  
 <span data-ttu-id="ef324-113">Es posible definir un símbolo, pero no asignar un valor a un símbolo.</span><span class="sxs-lookup"><span data-stu-id="ef324-113">You can define a symbol, but you cannot assign a value to a symbol.</span></span> <span data-ttu-id="ef324-114">La directiva `#define` debe aparecer en el archivo antes de que use cualquier instrucción que tampoco sea una directiva del preprocesador.</span><span class="sxs-lookup"><span data-stu-id="ef324-114">The `#define` directive must appear in the file before you use any instructions that aren't also preprocessor directives.</span></span>  
  
 <span data-ttu-id="ef324-115">También puede definir un símbolo con la opción [/define](../../../csharp/language-reference/compiler-options/define-compiler-option.md) del compilador.</span><span class="sxs-lookup"><span data-stu-id="ef324-115">You can also define a symbol with the [/define](../../../csharp/language-reference/compiler-options/define-compiler-option.md) compiler option.</span></span> <span data-ttu-id="ef324-116">La definición de un símbolo se puede anular mediante [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md).</span><span class="sxs-lookup"><span data-stu-id="ef324-116">You can undefine a symbol with [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md).</span></span>  
  
 <span data-ttu-id="ef324-117">Un símbolo definido mediante `/define` o `#define` no debe entrar en conflicto con una variable del mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="ef324-117">A symbol that you define with `/define` or with `#define` does not conflict with a variable of the same name.</span></span> <span data-ttu-id="ef324-118">Es decir, no se debería pasar un nombre de variable a una directiva de preprocesador ni evaluar solo un símbolo mediante una directiva de preprocesador.</span><span class="sxs-lookup"><span data-stu-id="ef324-118">That is, a variable name should not be passed to a preprocessor directive and a symbol can only be evaluated by a preprocessor directive.</span></span>  
  
 <span data-ttu-id="ef324-119">El ámbito de un símbolo que se ha creado mediante `#define` corresponde al archivo en el que se ha definido.</span><span class="sxs-lookup"><span data-stu-id="ef324-119">The scope of a symbol that was created by using `#define` is the file in which the symbol was defined.</span></span>  
  
 <span data-ttu-id="ef324-120">Como se muestra en el siguiente ejemplo, debe colocar directivas `#define` en la parte superior del archivo.</span><span class="sxs-lookup"><span data-stu-id="ef324-120">As the following example shows, you must put `#define` directives at the top of the file.</span></span>  
  
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
  
 <span data-ttu-id="ef324-121">Para obtener un ejemplo de cómo anular la definición de un símbolo, vea [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md).</span><span class="sxs-lookup"><span data-stu-id="ef324-121">For an example of how to undefine a symbol, see [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef324-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="ef324-122">See Also</span></span>  
 <span data-ttu-id="ef324-123">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="ef324-123">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="ef324-124">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="ef324-124">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="ef324-125">[Directivas de preprocesador de C#](../../../csharp/language-reference/preprocessor-directives/index.md) </span><span class="sxs-lookup"><span data-stu-id="ef324-125">[C# Preprocessor Directives](../../../csharp/language-reference/preprocessor-directives/index.md) </span></span>  
 <span data-ttu-id="ef324-126">[const](../../../csharp/language-reference/keywords/const.md) </span><span class="sxs-lookup"><span data-stu-id="ef324-126">[const](../../../csharp/language-reference/keywords/const.md) </span></span>  
 <span data-ttu-id="ef324-127">[Cómo: Realizar compilación condicional con Trace y Debug](../../../framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md) </span><span class="sxs-lookup"><span data-stu-id="ef324-127">[How to: Compile Conditionally with Trace and Debug](../../../framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md) </span></span>  
 <span data-ttu-id="ef324-128">[#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md) </span><span class="sxs-lookup"><span data-stu-id="ef324-128">[#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md) </span></span>  
 [<span data-ttu-id="ef324-129">#if</span><span class="sxs-lookup"><span data-stu-id="ef324-129">#if</span></span>](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md)

