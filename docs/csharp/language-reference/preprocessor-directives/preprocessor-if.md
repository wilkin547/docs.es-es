---
title: '#<a name="if-c-reference"></a>if (Referencia de C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#if'
dev_langs:
- CSharp
helpviewer_keywords:
- '#if directive [C#]'
ms.assetid: 48cabbff-ca82-491f-a56a-eeccd528c7c2
caps.latest.revision: 17
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
ms.openlocfilehash: f70dac98d5731370ae961f795b08a71946867d9b
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="if-c-reference"></a><span data-ttu-id="2b993-102">#if (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="2b993-102">#if (C# Reference)</span></span>
<span data-ttu-id="2b993-103">Cuando el compilador de C# encuentra una directiva `#if`, seguida finalmente por una directiva [#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md), compilará el código entre las directivas solo si se ha definido el símbolo especificado.</span><span class="sxs-lookup"><span data-stu-id="2b993-103">When the C# compiler encounters an `#if` directive, followed eventually by an [#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md) directive, it will compile the code between the directives only if the specified symbol is defined.</span></span>  <span data-ttu-id="2b993-104">A diferencia de C y C++, no puede asignar un valor numérico a un símbolo; la instrucción #if en C# es booleana y solo comprueba si el símbolo se ha definido o no.</span><span class="sxs-lookup"><span data-stu-id="2b993-104">Unlike C and C++, you cannot assign a numeric value to a symbol; the #if statement in C# is Boolean and only tests whether the symbol has been defined or not.</span></span> <span data-ttu-id="2b993-105">Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="2b993-105">For example,</span></span>  
  
```csharp
#define DEBUG  
// ...  
#if DEBUG  
    Console.WriteLine("Debug version");  
#endif  
```  
  
 <span data-ttu-id="2b993-106">Puede usar los operadores [==](../../../csharp/language-reference/operators/equality-comparison-operator.md) (igualdad), [!=](../../../csharp/language-reference/operators/not-equal-operator.md) (desigualdad) solo para comprobar los valores [true](../../../csharp/language-reference/keywords/true.md) o [false](../../../csharp/language-reference/keywords/false.md) .</span><span class="sxs-lookup"><span data-stu-id="2b993-106">You can use the operators [==](../../../csharp/language-reference/operators/equality-comparison-operator.md) (equality), [!=](../../../csharp/language-reference/operators/not-equal-operator.md) (inequality) only to test for [true](../../../csharp/language-reference/keywords/true.md) or [false](../../../csharp/language-reference/keywords/false.md) .</span></span> <span data-ttu-id="2b993-107">True significa que el símbolo está definido.</span><span class="sxs-lookup"><span data-stu-id="2b993-107">True means the symbol is defined.</span></span> <span data-ttu-id="2b993-108">La instrucción `#if DEBUG` tiene el mismo significado que `#if (DEBUG == true)`.</span><span class="sxs-lookup"><span data-stu-id="2b993-108">The statement `#if DEBUG` has the same meaning as `#if (DEBUG == true)`.</span></span> <span data-ttu-id="2b993-109">Puede usar los operadores [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) (y), [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md) (o) y [!](../../../csharp/language-reference/operators/logical-negation-operator.md)</span><span class="sxs-lookup"><span data-stu-id="2b993-109">You can use the operators [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) (and), [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md) (or), and [!](../../../csharp/language-reference/operators/logical-negation-operator.md)</span></span> <span data-ttu-id="2b993-110">(no) para evaluar si se han definido varios símbolos.</span><span class="sxs-lookup"><span data-stu-id="2b993-110">(not) to evaluate whether multiple symbols have been defined.</span></span> <span data-ttu-id="2b993-111">Es posible agrupar símbolos y operadores mediante paréntesis.</span><span class="sxs-lookup"><span data-stu-id="2b993-111">You can also group symbols and operators with parentheses.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2b993-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2b993-112">Remarks</span></span>  
 <span data-ttu-id="2b993-113">`#if`, junto con las directivas [#else](../../../csharp/language-reference/preprocessor-directives/preprocessor-else.md), [#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md), [#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md), [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md) y [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md), permite incluir o excluir código basado en la existencia de uno o varios símbolos.</span><span class="sxs-lookup"><span data-stu-id="2b993-113">`#if`, along with the [#else](../../../csharp/language-reference/preprocessor-directives/preprocessor-else.md), [#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md), [#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md), [#define](../../../csharp/language-reference/preprocessor-directives/preprocessor-define.md), and [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md) directives, lets you include or exclude code based on the existence of one or more symbols.</span></span> <span data-ttu-id="2b993-114">Esto puede resultar útil al compilar código para una compilación de depuración o al compilar para una configuración específica.</span><span class="sxs-lookup"><span data-stu-id="2b993-114">This can be useful when compiling code for a debug build or when compiling for a specific configuration.</span></span>  
  
 <span data-ttu-id="2b993-115">Una directiva condicional que empieza con una directiva `#if` debe terminar de forma explícita con una directiva `#endif`.</span><span class="sxs-lookup"><span data-stu-id="2b993-115">A conditional directive beginning with a `#if` directive must explicitly be terminated with a `#endif` directive.</span></span>  
  
 <span data-ttu-id="2b993-116">`#define` permite definir un símbolo, de tal forma que, si se usa como la expresión pasada a la directiva `#if`, la expresión se evaluará el valor `true`.</span><span class="sxs-lookup"><span data-stu-id="2b993-116">`#define` lets you define a symbol, such that, by using the symbol as the expression passed to the `#if` directive, the expression will evaluate to `true`.</span></span>  
  
 <span data-ttu-id="2b993-117">También puede definir un símbolo con la opción [/define](../../../csharp/language-reference/compiler-options/define-compiler-option.md) del compilador.</span><span class="sxs-lookup"><span data-stu-id="2b993-117">You can also define a symbol with the [/define](../../../csharp/language-reference/compiler-options/define-compiler-option.md) compiler option.</span></span> <span data-ttu-id="2b993-118">La definición de un símbolo se puede anular mediante [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md).</span><span class="sxs-lookup"><span data-stu-id="2b993-118">You can undefine a symbol with [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md).</span></span>  
  
 <span data-ttu-id="2b993-119">Un símbolo definido mediante `/define` o `#define` no debe entrar en conflicto con una variable del mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="2b993-119">A symbol that you define with `/define` or with `#define` does not conflict with a variable of the same name.</span></span> <span data-ttu-id="2b993-120">Es decir, no se debería pasar un nombre de variable a una directiva de preprocesador ni evaluar solo un símbolo mediante una directiva de preprocesador.</span><span class="sxs-lookup"><span data-stu-id="2b993-120">That is, a variable name should not be passed to a preprocessor directive and a symbol can only be evaluated by a preprocessor directive.</span></span>  
  
 <span data-ttu-id="2b993-121">El ámbito de un símbolo creado con `#define` es el archivo en que se ha definido.</span><span class="sxs-lookup"><span data-stu-id="2b993-121">The scope of a symbol created with `#define` is the file in which it was defined.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b993-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2b993-122">Example</span></span>  
  
```csharp
// preprocessor_if.cs  
#define DEBUG#define MYTEST  
using System;  
public class MyClass   
{  
    static void Main()   
    {  
#if (DEBUG && !MYTEST)  
        Console.WriteLine("DEBUG is defined");  
#elif (!DEBUG && MYTEST)  
        Console.WriteLine("MYTEST is defined");  
#elif (DEBUG && MYTEST)  
        Console.WriteLine("DEBUG and MYTEST are defined");  
#else  
        Console.WriteLine("DEBUG and MYTEST are not defined");  
#endif  
    }  
}  
```  
  
 <span data-ttu-id="2b993-123">**Se definen DEBUG y MYTEST**</span><span class="sxs-lookup"><span data-stu-id="2b993-123">**DEBUG and MYTEST are defined**</span></span>   
## <a name="see-also"></a><span data-ttu-id="2b993-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="2b993-124">See Also</span></span>  
 <span data-ttu-id="2b993-125">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="2b993-125">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="2b993-126">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="2b993-126">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="2b993-127">Directivas de preprocesador de C#</span><span class="sxs-lookup"><span data-stu-id="2b993-127">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)

