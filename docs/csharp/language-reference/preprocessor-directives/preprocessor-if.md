---
description: '#Directiva de preprocesador if: Referencia de C#'
title: '#Directiva de preprocesador if: Referencia de C#'
ms.date: 10/27/2019
f1_keywords:
- '#if'
helpviewer_keywords:
- '#if directive [C#]'
ms.assetid: 48cabbff-ca82-491f-a56a-eeccd528c7c2
ms.openlocfilehash: a3f72719ba4ce722aef33bbd5de338d3d06b2aa0
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2021
ms.locfileid: "103480377"
---
# <a name="if-c-reference"></a><span data-ttu-id="1a11c-103">#if (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="1a11c-103">#if (C# reference)</span></span>

<span data-ttu-id="1a11c-104">Cuando el compilador de C# encuentra una directiva `#if`, seguida finalmente por una directiva [#endif](preprocessor-endif.md), compila el código entre las directivas solo si se ha definido el símbolo especificado.</span><span class="sxs-lookup"><span data-stu-id="1a11c-104">When the C# compiler encounters an `#if` directive, followed eventually by an [#endif](preprocessor-endif.md) directive, it compiles the code between the directives only if the specified symbol is defined.</span></span> <span data-ttu-id="1a11c-105">A diferencia de C y C++, no se puede asignar un valor numérico a un símbolo.</span><span class="sxs-lookup"><span data-stu-id="1a11c-105">Unlike C and C++, you cannot assign a numeric value to a symbol.</span></span> <span data-ttu-id="1a11c-106">La instrucción `#if` en C# es booleana y solo comprueba si el símbolo se ha definido o no.</span><span class="sxs-lookup"><span data-stu-id="1a11c-106">The `#if` statement in C# is Boolean and only tests whether the symbol has been defined or not.</span></span> <span data-ttu-id="1a11c-107">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="1a11c-107">For example:</span></span>

```csharp
#if DEBUG
    Console.WriteLine("Debug version");
#endif
```

<span data-ttu-id="1a11c-108">Puede usar los operadores [==](../operators/equality-operators.md#equality-operator-) (igualdad) y [!=](../operators/equality-operators.md#inequality-operator-) (desigualdad) solo para comprobar los valores [booleanos](../builtin-types/bool.md)`true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="1a11c-108">You can use the operators [==](../operators/equality-operators.md#equality-operator-) (equality) and [!=](../operators/equality-operators.md#inequality-operator-) (inequality) only to test for the [bool](../builtin-types/bool.md) values `true` or `false`.</span></span> <span data-ttu-id="1a11c-109">`true` significa que el símbolo está definido.</span><span class="sxs-lookup"><span data-stu-id="1a11c-109">`true` means the symbol is defined.</span></span> <span data-ttu-id="1a11c-110">La instrucción `#if DEBUG` tiene el mismo significado que `#if (DEBUG == true)`.</span><span class="sxs-lookup"><span data-stu-id="1a11c-110">The statement `#if DEBUG` has the same meaning as `#if (DEBUG == true)`.</span></span> <span data-ttu-id="1a11c-111">Puede usar los operadores [&& (AND)](../operators/boolean-logical-operators.md#conditional-logical-and-operator-), [&#124;&#124; (OR)](../operators/boolean-logical-operators.md#conditional-logical-or-operator-) y [! (NOT)](../operators/boolean-logical-operators.md#logical-negation-operator-) para evaluar si se han definido varios símbolos.</span><span class="sxs-lookup"><span data-stu-id="1a11c-111">You can use the [&& (and)](../operators/boolean-logical-operators.md#conditional-logical-and-operator-), [&#124;&#124; (or)](../operators/boolean-logical-operators.md#conditional-logical-or-operator-), and [! (not)](../operators/boolean-logical-operators.md#logical-negation-operator-) operators to evaluate whether multiple symbols have been defined.</span></span> <span data-ttu-id="1a11c-112">Es posible agrupar símbolos y operadores mediante paréntesis.</span><span class="sxs-lookup"><span data-stu-id="1a11c-112">You can also group symbols and operators with parentheses.</span></span>

## <a name="remarks"></a><span data-ttu-id="1a11c-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1a11c-113">Remarks</span></span>

<span data-ttu-id="1a11c-114">`#if`, junto con las directivas [#else](preprocessor-else.md), [#elif](preprocessor-elif.md), [#endif](preprocessor-endif.md), [#define](preprocessor-define.md) y [#undef](preprocessor-undef.md), permite incluir o excluir código basado en la existencia de uno o varios símbolos.</span><span class="sxs-lookup"><span data-stu-id="1a11c-114">`#if`, along with the [#else](preprocessor-else.md), [#elif](preprocessor-elif.md), [#endif](preprocessor-endif.md), [#define](preprocessor-define.md), and [#undef](preprocessor-undef.md) directives, lets you include or exclude code based on the existence of one or more symbols.</span></span> <span data-ttu-id="1a11c-115">Esto puede resultar útil al compilar código para una compilación de depuración o al compilar para una configuración específica.</span><span class="sxs-lookup"><span data-stu-id="1a11c-115">This can be useful when compiling code for a debug build or when compiling for a specific configuration.</span></span>

<span data-ttu-id="1a11c-116">Una directiva condicional que empieza con una directiva `#if` debe terminar de forma explícita con una directiva `#endif`.</span><span class="sxs-lookup"><span data-stu-id="1a11c-116">A conditional directive beginning with a `#if` directive must explicitly be terminated with a `#endif` directive.</span></span>

<span data-ttu-id="1a11c-117">`#define` permite definir un símbolo.</span><span class="sxs-lookup"><span data-stu-id="1a11c-117">`#define` lets you define a symbol.</span></span> <span data-ttu-id="1a11c-118">Si luego se usa el símbolo como la expresión pasada a la directiva `#if`, la expresión se evalúa como `true`.</span><span class="sxs-lookup"><span data-stu-id="1a11c-118">By then using the symbol as the expression passed to the `#if` directive, the expression evaluates to `true`.</span></span>

<span data-ttu-id="1a11c-119">También se puede definir un símbolo con la opción del compilador [**DefineConstants**](../compiler-options/language.md#defineconstants).</span><span class="sxs-lookup"><span data-stu-id="1a11c-119">You can also define a symbol with the [**DefineConstants**](../compiler-options/language.md#defineconstants) compiler option.</span></span> <span data-ttu-id="1a11c-120">La definición de un símbolo se puede anular mediante [#undef](preprocessor-undef.md).</span><span class="sxs-lookup"><span data-stu-id="1a11c-120">You can undefine a symbol with [#undef](preprocessor-undef.md).</span></span>

<span data-ttu-id="1a11c-121">Un símbolo definido con `-define` o `#define` no debe entrar en conflicto con una variable del mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="1a11c-121">A symbol that you define with `-define` or with `#define` doesn't conflict with a variable of the same name.</span></span> <span data-ttu-id="1a11c-122">Es decir, un nombre de variable no debe pasarse a una directiva de preprocesador y un símbolo solo puede ser evaluado por una directiva de preprocesador.</span><span class="sxs-lookup"><span data-stu-id="1a11c-122">That is, a variable name should not be passed to a preprocessor directive, and a symbol can only be evaluated by a preprocessor directive.</span></span>

<span data-ttu-id="1a11c-123">El ámbito de un símbolo creado con `#define` es el archivo en que se ha definido.</span><span class="sxs-lookup"><span data-stu-id="1a11c-123">The scope of a symbol created with `#define` is the file in which it was defined.</span></span>

<span data-ttu-id="1a11c-124">El sistema de compilación también tiene en cuenta los símbolos de preprocesador predefinidos que representan distintos [marcos de destino](../../../standard/frameworks.md) en proyectos de estilo SDK.</span><span class="sxs-lookup"><span data-stu-id="1a11c-124">The build system is also aware of predefined preprocessor symbols representing different [target frameworks](../../../standard/frameworks.md) in SDK-style projects.</span></span> <span data-ttu-id="1a11c-125">Resultan útiles al crear aplicaciones que pueden tener como destino más de una versión de .NET.</span><span class="sxs-lookup"><span data-stu-id="1a11c-125">They're useful when creating applications that can target more than one .NET version.</span></span>

[!INCLUDE [Preprocessor symbols](~/includes/preprocessor-symbols.md)]

> [!NOTE]
> <span data-ttu-id="1a11c-126">En el caso de los proyectos que no son de estilo SDK, tendrá que configurar manualmente los símbolos de compilación condicional para las diferentes plataformas de destino en Visual Studio a través de las páginas de propiedades del proyecto.</span><span class="sxs-lookup"><span data-stu-id="1a11c-126">For traditional, non-SDK-style projects, you have to manually configure the conditional compilation symbols for the different target frameworks in Visual Studio via the project's properties pages.</span></span>

<span data-ttu-id="1a11c-127">Otros símbolos predefinidos incluyen las constantes DEBUG y TRACE.</span><span class="sxs-lookup"><span data-stu-id="1a11c-127">Other predefined symbols include the DEBUG and TRACE constants.</span></span> <span data-ttu-id="1a11c-128">Puede invalidar los valores establecidos para el proyecto con `#define`.</span><span class="sxs-lookup"><span data-stu-id="1a11c-128">You can override the values set for the project using `#define`.</span></span> <span data-ttu-id="1a11c-129">Por ejemplo, el símbolo DEBUG se establece automáticamente según las propiedades de configuración de compilación (modo de "depuración" o de "versión").</span><span class="sxs-lookup"><span data-stu-id="1a11c-129">The DEBUG symbol, for example, is automatically set depending on your build configuration properties ("Debug" or "Release" mode).</span></span>

## <a name="examples"></a><span data-ttu-id="1a11c-130">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="1a11c-130">Examples</span></span>

<span data-ttu-id="1a11c-131">En el ejemplo siguiente se muestra cómo definir un símbolo MYTEST en un archivo y luego probar los valores de los símbolos MYTEST y DEBUG.</span><span class="sxs-lookup"><span data-stu-id="1a11c-131">The following example shows you how to define a MYTEST symbol on a file and then test the values of the MYTEST and DEBUG symbols.</span></span> <span data-ttu-id="1a11c-132">El resultado de este ejemplo depende de si ha compilado el proyecto en modo de configuración de depuración o de versión.</span><span class="sxs-lookup"><span data-stu-id="1a11c-132">The output of this example depends on whether you built the project on Debug or Release configuration mode.</span></span>

```csharp
#define MYTEST
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

<span data-ttu-id="1a11c-133">En el ejemplo siguiente se muestra cómo probar distintos marcos de destino para que se puedan usar las API más recientes cuando sea posible:</span><span class="sxs-lookup"><span data-stu-id="1a11c-133">The following example shows you how to test for different target frameworks so you can use newer APIs when possible:</span></span>

```csharp
public class MyClass
{
    static void Main()
    {
#if NET40
        WebClient _client = new WebClient();
#else
        HttpClient _client = new HttpClient();
#endif
    }
    //...
}
```

## <a name="see-also"></a><span data-ttu-id="1a11c-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="1a11c-134">See also</span></span>

- [<span data-ttu-id="1a11c-135">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="1a11c-135">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="1a11c-136">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="1a11c-136">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="1a11c-137">Directivas de preprocesador de C#</span><span class="sxs-lookup"><span data-stu-id="1a11c-137">C# Preprocessor Directives</span></span>](index.md)
- [<span data-ttu-id="1a11c-138">Cómo: Compilación condicional con Trace y Debug</span><span class="sxs-lookup"><span data-stu-id="1a11c-138">How to: Compile Conditionally with Trace and Debug</span></span>](../../../framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md)
