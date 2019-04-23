---
title: Novedades de .NET Core 3.0
description: Obtenga información sobre las características nuevas de .NET Core 3.0.
dev_langs:
- csharp
- vb
author: thraka
ms.author: adegeo
ms.date: 12/31/2018
ms.openlocfilehash: 086be4649f4e7e27ff98df6f26d08856683865c8
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2019
ms.locfileid: "59611788"
---
# <a name="whats-new-in-net-core-30-preview-2"></a><span data-ttu-id="691fc-103">Novedades de .NET Core 3.0 (versión preliminar 2)</span><span class="sxs-lookup"><span data-stu-id="691fc-103">What's new in .NET Core 3.0 (Preview 2)</span></span>

<span data-ttu-id="691fc-104">En este artículo se describen las novedades de .NET Core 3.0 (versión preliminar 2).</span><span class="sxs-lookup"><span data-stu-id="691fc-104">This article describes what is new in .NET Core 3.0 (preview 2).</span></span> <span data-ttu-id="691fc-105">Una de las mejoras más importantes es la compatibilidad con las aplicaciones de Escritorio de Windows (solo Windows).</span><span class="sxs-lookup"><span data-stu-id="691fc-105">One of the biggest enhancements is support for Windows desktop applications (Windows only).</span></span> <span data-ttu-id="691fc-106">Mediante el uso de un componente de SDK de .NET Core 3.0 denominado "Escritorio de Windows", puede trasladar sus aplicaciones de Windows Presentation Foundation (WPF) y Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="691fc-106">By utilizing a .NET Core 3.0 SDK component called Windows Desktop, you can port your Windows Forms and Windows Presentation Foundation (WPF) applications.</span></span> <span data-ttu-id="691fc-107">Para ser más precisos, el componente Escritorio de Windows solo se admite e incluye en Windows.</span><span class="sxs-lookup"><span data-stu-id="691fc-107">To be clear, the Windows Desktop component is only supported and included on Windows.</span></span> <span data-ttu-id="691fc-108">Para obtener más información, vea la sección [Escritorio de Windows](#windows-desktop) de más adelante.</span><span class="sxs-lookup"><span data-stu-id="691fc-108">For more information, see the section [Windows desktop](#windows-desktop) below.</span></span>

<span data-ttu-id="691fc-109">.NET Core 3.0 agrega compatibilidad con C# 8.0.</span><span class="sxs-lookup"><span data-stu-id="691fc-109">.NET Core 3.0 adds support for C# 8.0.</span></span>

<span data-ttu-id="691fc-110">[Descargue .NET Core 3.0 (versión preliminar 2) y empiece a usarlo](https://aka.ms/netcore3download) ahora mismo en Windows, Mac y Linux.</span><span class="sxs-lookup"><span data-stu-id="691fc-110">[Download and get started with .NET Core 3.0 Preview 2](https://aka.ms/netcore3download) right now on Windows, Mac and Linux.</span></span> <span data-ttu-id="691fc-111">Puede ver los detalles completos de la versión en las [notas de la versión preliminar 2 de .NET Core 3.0](https://aka.ms/netcore3releasenotes).</span><span class="sxs-lookup"><span data-stu-id="691fc-111">You can see complete details of the release in the [.NET Core 3.0 Preview 2 release notes](https://aka.ms/netcore3releasenotes).</span></span>

<span data-ttu-id="691fc-112">Para más información sobre lo que se ha publicado con cada versión, vea los anuncios siguientes:</span><span class="sxs-lookup"><span data-stu-id="691fc-112">For more information about what was released with each version, see the following announcements:</span></span>

- [<span data-ttu-id="691fc-113">Anuncio de la versión preliminar 1 de .NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="691fc-113">.NET Core 3.0 Preview 1 announcement</span></span>](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-preview-1-and-open-sourcing-windows-desktop-frameworks/)
- [<span data-ttu-id="691fc-114">Anuncio de la versión preliminar 2 de .NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="691fc-114">.NET Core 3.0 Preview 2 announcement</span></span>](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-preview-2/)

## <a name="c-8"></a><span data-ttu-id="691fc-115">C# 8</span><span class="sxs-lookup"><span data-stu-id="691fc-115">C# 8</span></span>

<span data-ttu-id="691fc-116">.NET Core 3.0 admite C# 8 y, a partir de .NET Core 3.0 (versión preliminar 2), admite estas nuevas características.</span><span class="sxs-lookup"><span data-stu-id="691fc-116">.NET Core 3.0 supports C# 8, and as of .NET Core 3.0 Preview 2, supports these new features.</span></span> <span data-ttu-id="691fc-117">Para obtener más información sobre las características de C# 8.0, consulte las siguientes entradas de blog:</span><span class="sxs-lookup"><span data-stu-id="691fc-117">For more information about C# 8.0 features, see the following blog posts:</span></span>

- <span data-ttu-id="691fc-118">[Do more with patterns in C# 8.0](https://devblogs.microsoft.com/dotnet/do-more-with-patterns-in-c-8-0/) (Hacer más con patrones en C# 8.0)</span><span class="sxs-lookup"><span data-stu-id="691fc-118">[Do more with patterns in C# 8.0](https://devblogs.microsoft.com/dotnet/do-more-with-patterns-in-c-8-0/)</span></span>
- <span data-ttu-id="691fc-119">[Take C# 8.0 for a spin](https://devblogs.microsoft.com/dotnet/take-c-8-0-for-a-spin/) (Probar C# 8.0)</span><span class="sxs-lookup"><span data-stu-id="691fc-119">[Take C# 8.0 for a spin](https://devblogs.microsoft.com/dotnet/take-c-8-0-for-a-spin/)</span></span>
- <span data-ttu-id="691fc-120">[Building C# 8.0](https://devblogs.microsoft.com/dotnet/building-c-8-0/) (Compilación de C# 8.0)</span><span class="sxs-lookup"><span data-stu-id="691fc-120">[Building C# 8.0](https://devblogs.microsoft.com/dotnet/building-c-8-0/)</span></span>

### <a name="ranges-and-indices"></a><span data-ttu-id="691fc-121">Rangos e índices</span><span class="sxs-lookup"><span data-stu-id="691fc-121">Ranges and indices</span></span>

<span data-ttu-id="691fc-122">El nuevo tipo `Index` se puede utilizar para la indización.</span><span class="sxs-lookup"><span data-stu-id="691fc-122">The new `Index` type can be used for indexing.</span></span> <span data-ttu-id="691fc-123">Puede crear uno desde un índice `int` que cuente desde el principio o con un operador `^` de prefijo (C#) que cuente desde el final:</span><span class="sxs-lookup"><span data-stu-id="691fc-123">You can create one from an `int` that counts from the beginning, or with a prefix `^` operator (C#) that counts from the end:</span></span>

```csharp
Index i1 = 3;  // number 3 from beginning
Index i2 = ^4; // number 4 from end
int[] a = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };
Console.WriteLine($"{a[i1]}, {a[i2]}"); // "3, 6"
```

<span data-ttu-id="691fc-124">También hay un tipo `Range`, que consta de dos valores `Index`, uno para el inicio y otro para el final, y se puede escribir con una expresión de rango `x..y` (C#).</span><span class="sxs-lookup"><span data-stu-id="691fc-124">There is also a `Range` type, which consists of two `Index` values, one for the start and one for the end, and can be written with a `x..y` range expression (C#).</span></span> <span data-ttu-id="691fc-125">A continuación, puede crear un índice con un rango `Range` con el fin de generar un segmento:</span><span class="sxs-lookup"><span data-stu-id="691fc-125">You can then index with a `Range` in order to produce a slice:</span></span>

```csharp
var slice = a[i1..i2]; // { 3, 4, 5 }
```

### <a name="async-streams"></a><span data-ttu-id="691fc-126">Flujos asincrónicos</span><span class="sxs-lookup"><span data-stu-id="691fc-126">Async streams</span></span>

<span data-ttu-id="691fc-127">El tipo `IAsyncEnumerable<T>` es una nueva versión asincrónica de `IEnumerable<T>`.</span><span class="sxs-lookup"><span data-stu-id="691fc-127">The `IAsyncEnumerable<T>` type is a new asynchronous version of `IEnumerable<T>`.</span></span> <span data-ttu-id="691fc-128">El lenguaje permite ejecutar la instrucción `await foreach` en `IAsyncEnumerable<T>` para consumir sus elementos, y usar la instrucción `yield return` en ellos para generar los elementos.</span><span class="sxs-lookup"><span data-stu-id="691fc-128">The language lets you `await foreach` over `IAsyncEnumerable<T>` to consume their elements, and use `yield return` to them to produce elements.</span></span>

<span data-ttu-id="691fc-129">En el ejemplo siguiente se muestra la producción y el consumo de flujos asincrónicos.</span><span class="sxs-lookup"><span data-stu-id="691fc-129">The following example demonstrates both production and consumption of async streams.</span></span> <span data-ttu-id="691fc-130">La instrucción `foreach` es asincrónica y usa `yield return` para generar un flujo asincrónico para los llamadores.</span><span class="sxs-lookup"><span data-stu-id="691fc-130">The `foreach` statement is async and itself uses `yield return` to produce an async stream for callers.</span></span> <span data-ttu-id="691fc-131">Este patrón (que usa `yield return`) es el modelo recomendado para generar flujos asincrónicos.</span><span class="sxs-lookup"><span data-stu-id="691fc-131">This pattern (using `yield return`) is the recommended model for producing async streams.</span></span>

```csharp
async IAsyncEnumerable<int> GetBigResultsAsync()
{
    await foreach (var result in GetResultsAsync())
    {
        if (result > 20) yield return result;
    }
}
```

<span data-ttu-id="691fc-132">Además de poder ejecutar `await foreach`, también puede crear iteradores asincrónicos, por ejemplo, uno que devuelva un enumerador `IAsyncEnumerable/IAsyncEnumerator` en el que pueda ejecutar `await` y `yield`.</span><span class="sxs-lookup"><span data-stu-id="691fc-132">In addition to being able to `await foreach`, you can also create async iterators, for example, an iterator that returns an `IAsyncEnumerable/IAsyncEnumerator` that you can both `await` and `yield` in.</span></span> <span data-ttu-id="691fc-133">Para los objetos que deban eliminarse, puede usar `IAsyncDisposable`, que implementan varios tipos BCL, como `Stream` y `Timer`.</span><span class="sxs-lookup"><span data-stu-id="691fc-133">For objects that need to be disposed, you can use `IAsyncDisposable`, which various BCL types implement, such as `Stream` and `Timer`.</span></span>

> [!NOTE]
> <span data-ttu-id="691fc-134">Necesita .NET Core 3.0 (versión preliminar 2) para usar flujos asincrónicos si desea desarrollar con Visual Studio 2019 o la versión preliminar más reciente de la [extensión de C# para Visual Studio Code](https://github.com/OmniSharp/omnisharp-vscode/releases/tag/v1.18.0-beta5).</span><span class="sxs-lookup"><span data-stu-id="691fc-134">You need .NET Core 3.0 Preview 2 to use async streams if you want to develop with either Visual Studio 2019 or the latest preview of the [C# extension for Visual Studio Code](https://github.com/OmniSharp/omnisharp-vscode/releases/tag/v1.18.0-beta5).</span></span> <span data-ttu-id="691fc-135">Si usa .NET Core 3.0 (versión preliminar) en la línea de comandos, todo funcionará según lo previsto.</span><span class="sxs-lookup"><span data-stu-id="691fc-135">If you are using .NET Core 3.0 Preview 2 at the command line, then everything will work as expected.</span></span>

### <a name="using-declarations"></a><span data-ttu-id="691fc-136">Declaraciones using</span><span class="sxs-lookup"><span data-stu-id="691fc-136">Using Declarations</span></span>

<span data-ttu-id="691fc-137">Las *declaraciones using* son una nueva forma de garantizar que su objeto se elimine correctamente.</span><span class="sxs-lookup"><span data-stu-id="691fc-137">*Using declarations* are a new way to ensure your object is properly disposed.</span></span> <span data-ttu-id="691fc-138">Una *declaración using* mantiene activo el objeto mientras sigue en el ámbito.</span><span class="sxs-lookup"><span data-stu-id="691fc-138">A *using declaration* keeps the object alive while it is still in scope.</span></span> <span data-ttu-id="691fc-139">Una vez que el objeto deja de estar en el ámbito, se elimina automáticamente.</span><span class="sxs-lookup"><span data-stu-id="691fc-139">Once the object becomes out of scope, it is automatically disposed.</span></span> <span data-ttu-id="691fc-140">Esto reducirá las *instrucciones using* anidadas y hará que su código esté más limpio.</span><span class="sxs-lookup"><span data-stu-id="691fc-140">This will reduce nested *using statements* and make your code cleaner.</span></span>

```csharp
static void Main(string[] args)
{
    using var options = Parse(args);
    if (options["verbose"]) { WriteLine("Logging..."); }

} // options disposed here
```

### <a name="switch-expressions"></a><span data-ttu-id="691fc-141">Expresiones switch</span><span class="sxs-lookup"><span data-stu-id="691fc-141">Switch Expressions</span></span>

<span data-ttu-id="691fc-142">Las *expresiones switch* son una forma más limpia de hacer una *instrucción switch*, pero, al tratarse de una expresión, devuelve un valor.</span><span class="sxs-lookup"><span data-stu-id="691fc-142">*Switch expressions* are a cleaner way of doing a *switch statement* but, since it's an expression, returns a value.</span></span> <span data-ttu-id="691fc-143">Las *expresiones switch* también se integran completamente con la coincidencia de patrones y usan el patrón de descarte, `_`, para representar el valor `default`.</span><span class="sxs-lookup"><span data-stu-id="691fc-143">*Switch expressions* are also fully integrated with pattern matching, and use the discard pattern, `_`, to represent the `default` value.</span></span>

<span data-ttu-id="691fc-144">Puede ver la sintaxis de las *expresiones switch* en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="691fc-144">You can see the syntax for *switch expressions* in the following example:</span></span>

```csharp
static string Display(object o) => o switch
{
    Point { X: 0, Y: 0 }         => "origin",
    Point { X: var x, Y: var y } => $"({x}, {y})",
    _                            => "unknown"
};
```

<span data-ttu-id="691fc-145">Hay dos patrones en juego en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="691fc-145">There are two patterns at play in this example.</span></span> <span data-ttu-id="691fc-146">`o` coincide en primer lugar con el *patrón de tipo* `Point` y, a continuación, con el *patrón de propiedad* entre *{llaves}*.</span><span class="sxs-lookup"><span data-stu-id="691fc-146">`o` first matches with the `Point` *type pattern* and then with the *property pattern* inside the *{curly braces}*.</span></span> <span data-ttu-id="691fc-147">`_` describe `discard pattern`, que es igual a `default` para las *instrucciones switch*.</span><span class="sxs-lookup"><span data-stu-id="691fc-147">The `_` describes the `discard pattern`, which is the same as `default` for *switch statements*.</span></span>

<span data-ttu-id="691fc-148">Los patrones le permiten escribir código declarativo que captura su intención en lugar de código de procedimientos que implementa pruebas para esta.</span><span class="sxs-lookup"><span data-stu-id="691fc-148">Patterns enable you to write declarative code that captures your intent instead of procedural code that implements tests for it.</span></span> <span data-ttu-id="691fc-149">El compilador pasa a ser responsable de la implementación de ese aburrido código de procedimientos y se garantiza su correcta realización en todo momento.</span><span class="sxs-lookup"><span data-stu-id="691fc-149">The compiler becomes responsible for implementing that boring procedural code and is guaranteed to always do it correctly.</span></span>

<span data-ttu-id="691fc-150">Seguirá habiendo casos en los que las *instrucciones switch* sean una opción mejor que las *expresiones switch* y los patrones puedan usarse con ambos estilos de sintaxis.</span><span class="sxs-lookup"><span data-stu-id="691fc-150">There will still be cases where *switch statements* will be a better choice than *switch expressions* and patterns can be used with both syntax styles.</span></span>

<span data-ttu-id="691fc-151">Para obtener más información, consulte [Do more with patterns in C# 8.0](https://devblogs.microsoft.com/dotnet/do-more-with-patterns-in-c-8-0/) (Hacer más con patrones en C# 8.0).</span><span class="sxs-lookup"><span data-stu-id="691fc-151">For more information, see [Do more with patterns in C# 8.0](https://devblogs.microsoft.com/dotnet/do-more-with-patterns-in-c-8-0/).</span></span>

## <a name="ieee-floating-point-improvements"></a><span data-ttu-id="691fc-152">Mejoras de punto flotante de IEEE</span><span class="sxs-lookup"><span data-stu-id="691fc-152">IEEE Floating-point improvements</span></span>

<span data-ttu-id="691fc-153">Las API de punto flotante se están actualizando para cumplir la [revisión IEEE 754-2008](https://en.wikipedia.org/wiki/IEEE_754-2008_revision).</span><span class="sxs-lookup"><span data-stu-id="691fc-153">Floating point APIs are in the process of being updated to comply with [IEEE 754-2008 revision](https://en.wikipedia.org/wiki/IEEE_754-2008_revision).</span></span> <span data-ttu-id="691fc-154">El objetivo de estos cambios es exponer todas las operaciones "obligatorias" y garantizar que cumplan de forma conductual la especificación IEEE.</span><span class="sxs-lookup"><span data-stu-id="691fc-154">The goal of these changes is to expose all "required" operations and ensure that they are behaviorally compliant with the IEEE spec.</span></span>

<span data-ttu-id="691fc-155">Correcciones de análisis y formato:</span><span class="sxs-lookup"><span data-stu-id="691fc-155">Parsing and formatting fixes:</span></span>

* <span data-ttu-id="691fc-156">Analice y redondee entradas de cualquier longitud correctamente.</span><span class="sxs-lookup"><span data-stu-id="691fc-156">Correctly parse and round inputs of any length.</span></span>
* <span data-ttu-id="691fc-157">Analice y formatee el cero negativo correctamente.</span><span class="sxs-lookup"><span data-stu-id="691fc-157">Correctly parse and format negative zero.</span></span>
* <span data-ttu-id="691fc-158">Analice Infinity y NaN correctamente realizando una comprobación sin distinción entre mayúsculas y minúsculas, y permitiendo un `+` anterior opcional si procede.</span><span class="sxs-lookup"><span data-stu-id="691fc-158">Correctly parse Infinity and NaN by performing a case-insensitive check and allowing an optional preceding `+` where applicable.</span></span>

<span data-ttu-id="691fc-159">Las nuevas API matemáticas tienen:</span><span class="sxs-lookup"><span data-stu-id="691fc-159">New Math APIs have:</span></span>

* `BitIncrement/BitDecrement`\
<span data-ttu-id="691fc-160">Corresponde a las operaciones IEEE `nextUp` y `nextDown`.</span><span class="sxs-lookup"><span data-stu-id="691fc-160">Corresponds to the `nextUp` and `nextDown` IEEE operations.</span></span> <span data-ttu-id="691fc-161">Devuelven el número de punto flotante más pequeño que compara mayor o menor que la entrada (respectivamente).</span><span class="sxs-lookup"><span data-stu-id="691fc-161">They return the smallest floating-point number that compares greater or lesser than the input (respectively).</span></span> <span data-ttu-id="691fc-162">Por ejemplo, `Math.BitIncrement(0.0)` devolvería `double.Epsilon`.</span><span class="sxs-lookup"><span data-stu-id="691fc-162">For example, `Math.BitIncrement(0.0)` would return `double.Epsilon`.</span></span>

* `MaxMagnitude/MinMagnitude`\
<span data-ttu-id="691fc-163">Corresponde a las operaciones IEEE `maxNumMag` y `minNumMag`, que devuelven el valor que es mayor o menor en magnitud de las dos entradas (respectivamente).</span><span class="sxs-lookup"><span data-stu-id="691fc-163">Corresponds to the `maxNumMag` and `minNumMag` IEEE operations, they return the value that is greater or lesser in magnitude of the two inputs (respectively).</span></span> <span data-ttu-id="691fc-164">Por ejemplo, `Math.MaxMagnitude(2.0, -3.0)` devolvería `-3.0`.</span><span class="sxs-lookup"><span data-stu-id="691fc-164">For example, `Math.MaxMagnitude(2.0, -3.0)` would return `-3.0`.</span></span>

* `ILogB`\
<span data-ttu-id="691fc-165">Corresponde a la operación IEEE `logB` que devuelve un valor integral. Devuelve el registro de base 2 integral del parámetro de entrada.</span><span class="sxs-lookup"><span data-stu-id="691fc-165">Corresponds to the `logB` IEEE operation which returns an integral value, it returns the integral base-2 log of the input parameter.</span></span> <span data-ttu-id="691fc-166">Es, eficazmente, igual que `floor(log2(x))`, pero se hace con un error de redondeo mínimo.</span><span class="sxs-lookup"><span data-stu-id="691fc-166">This is effectively the same as `floor(log2(x))`, but done with minimal rounding error.</span></span>

* `ScaleB`\
<span data-ttu-id="691fc-167">Corresponde a la operación IEEE `scaleB` que toma un valor integral. Devuelve eficazmente `x * pow(2, n)`, pero se hace con un error de redondeo mínimo.</span><span class="sxs-lookup"><span data-stu-id="691fc-167">Corresponds to the `scaleB` IEEE operation which takes an integral value, it returns effectively `x * pow(2, n)`, but is done with minimal rounding error.</span></span>

* `Log2`\
<span data-ttu-id="691fc-168">Corresponde a la operación IEEE `log2`. Devuelve el logaritmo de base 2.</span><span class="sxs-lookup"><span data-stu-id="691fc-168">Corresponds to the `log2` IEEE operation, it returns the base-2 logarithm.</span></span> <span data-ttu-id="691fc-169">Minimiza el error de redondeo.</span><span class="sxs-lookup"><span data-stu-id="691fc-169">It minimizes rounding error.</span></span>

* `FusedMultiplyAdd`\
<span data-ttu-id="691fc-170">Corresponde a la operación IEEE `fma`. Realiza una multiplicación y suma fusionadas.</span><span class="sxs-lookup"><span data-stu-id="691fc-170">Corresponds to the `fma` IEEE operation, it performs a fused multiply add.</span></span> <span data-ttu-id="691fc-171">Es decir, realiza `(x * y) + z` como operación única, minimizando así el error de redondeo.</span><span class="sxs-lookup"><span data-stu-id="691fc-171">That is, it does `(x * y) + z` as a single operation, there-by minimizing the rounding error.</span></span> <span data-ttu-id="691fc-172">Un ejemplo sería `FusedMultiplyAdd(1e308, 2.0, -1e308)`, que devuelve `1e308`.</span><span class="sxs-lookup"><span data-stu-id="691fc-172">An example would be `FusedMultiplyAdd(1e308, 2.0, -1e308)` which returns `1e308`.</span></span> <span data-ttu-id="691fc-173">La operación `(1e308 * 2.0) - 1e308` regular devuelve `double.PositiveInfinity`.</span><span class="sxs-lookup"><span data-stu-id="691fc-173">The regular `(1e308 * 2.0) - 1e308` returns `double.PositiveInfinity`.</span></span>

* `CopySign`\
<span data-ttu-id="691fc-174">Corresponde a la operación IEEE `copySign`. Devuelve el valor de `x`, pero con el signo de `y`.</span><span class="sxs-lookup"><span data-stu-id="691fc-174">Corresponds to the `copySign` IEEE operation, it returns the value of `x`, but with the sign of `y`.</span></span>

## <a name="net-platform-dependent-intrinsics"></a><span data-ttu-id="691fc-175">Objetos intrínsecos dependientes de la plataforma .NET</span><span class="sxs-lookup"><span data-stu-id="691fc-175">.NET Platform Dependent Intrinsics</span></span>

<span data-ttu-id="691fc-176">Se han agregado API que permiten el acceso a determinadas instrucciones CPU orientadas al rendimiento, como los conjuntos de **instrucciones de manipulación de bits** o **SIMD**.</span><span class="sxs-lookup"><span data-stu-id="691fc-176">APIs have been added that allow access to certain perf-oriented CPU instructions, such as the **SIMD** or **Bit Manipulation instruction** sets.</span></span> <span data-ttu-id="691fc-177">Estas instrucciones pueden ayudar a lograr grandes mejoras en el rendimiento en situaciones determinadas, como el procesamiento de datos eficaz en paralelo.</span><span class="sxs-lookup"><span data-stu-id="691fc-177">These instructions can help achieve big performance improvements in certain scenarios, such as processing data efficiently in parallel.</span></span> <span data-ttu-id="691fc-178">Además de exponer las API para que sus programas las usen, las bibliotecas de .NET han empezado a utilizar estas instrucciones para mejorar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="691fc-178">In addition to exposing the APIs for your programs to use, the .NET libraries have begun using these instructions to improve performance.</span></span>

<span data-ttu-id="691fc-179">Las siguientes solicitudes de incorporación de cambios de CoreCLR muestran algunos de los objetos intrínsecos, a través de la implementación o el uso:</span><span class="sxs-lookup"><span data-stu-id="691fc-179">The following CoreCLR PRs demonstrate a few of the intrinsics, either via implementation or use:</span></span>

* <span data-ttu-id="691fc-180">[Implement simple SSE2 hardware intrinsics](https://github.com/dotnet/coreclr/pull/15585) (Implementar objetos intrínsecos de hardware SSE2 sencillos)</span><span class="sxs-lookup"><span data-stu-id="691fc-180">[Implement simple SSE2 hardware intrinsics](https://github.com/dotnet/coreclr/pull/15585)</span></span>
* <span data-ttu-id="691fc-181">[Implement the SSE hardware intrinsics](https://github.com/dotnet/coreclr/pull/15538) (Implementar los objetos intrínsecos de hardware SSE)</span><span class="sxs-lookup"><span data-stu-id="691fc-181">[Implement the SSE hardware intrinsics](https://github.com/dotnet/coreclr/pull/15538)</span></span>
* <span data-ttu-id="691fc-182">[Arm64 Base HW Intrinsics](https://github.com/dotnet/coreclr/pull/16822) (Objetos intrínsecos de hardware base Arm64)</span><span class="sxs-lookup"><span data-stu-id="691fc-182">[Arm64 Base HW Intrinsics](https://github.com/dotnet/coreclr/pull/16822)</span></span>
* <span data-ttu-id="691fc-183">[Use TZCNT and LZCNT for Locate{First|Last}Found{Byte|Char}](https://github.com/dotnet/coreclr/pull/21073) (Usar TZCNT y LZCNT para Locate{First|Last}Found{Byte|Char})</span><span class="sxs-lookup"><span data-stu-id="691fc-183">[Use TZCNT and LZCNT for Locate{First|Last}Found{Byte|Char}](https://github.com/dotnet/coreclr/pull/21073)</span></span>

<span data-ttu-id="691fc-184">Para obtener más información, consulte [Objetos intrínsecos dependientes de la plataforma .NET](https://github.com/dotnet/designs/blob/master/accepted/platform-intrinsics.md), que define un enfoque de definición de esta infraestructura de hardware, permitiendo a Microsoft, a los proveedores de chips o a cualquier otra empresa o persona definir API de chip/hardware que deben exponerse a código .NET.</span><span class="sxs-lookup"><span data-stu-id="691fc-184">For more information, see [.NET Platform Dependent Intrinsics](https://github.com/dotnet/designs/blob/master/accepted/platform-intrinsics.md), which defines an approach for defining this hardware infrastructure, allowing Microsoft, chip vendors, or any other company or individual to define hardware/chip APIs that should be exposed to .NET code.</span></span>

## <a name="default-executables"></a><span data-ttu-id="691fc-185">Archivos ejecutables predeterminados</span><span class="sxs-lookup"><span data-stu-id="691fc-185">Default executables</span></span>

<span data-ttu-id="691fc-186">.NET Core compilará ahora los [archivos ejecutables dependientes de marco de trabajo](../deploying/index.md#framework-dependent-executables-fde) de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="691fc-186">.NET Core will now build [framework-dependent executables](../deploying/index.md#framework-dependent-executables-fde) by default.</span></span> <span data-ttu-id="691fc-187">Se trata de una novedad en las aplicaciones que usan una versión de .NET Core instalada de forma global.</span><span class="sxs-lookup"><span data-stu-id="691fc-187">This is new for applications that use a globally installed version of .NET Core.</span></span> <span data-ttu-id="691fc-188">Hasta ahora, solo las [implementaciones autocontenidas](../deploying/index.md#self-contained-deployments-scd) producirían un archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="691fc-188">Until now, only [self-contained deployments](../deploying/index.md#self-contained-deployments-scd) would produce an executable.</span></span>

<span data-ttu-id="691fc-189">Durante `dotnet build` o `dotnet publish`, se crea un archivo ejecutable siempre que coincida con el entorno y la plataforma del SDK que usa.</span><span class="sxs-lookup"><span data-stu-id="691fc-189">During `dotnet build` or `dotnet publish`, an executable is created provided that matches the environment and platform of the SDK you are using.</span></span> <span data-ttu-id="691fc-190">Estos ejecutables funcionan de la misma forma que los ejecutables nativos:</span><span class="sxs-lookup"><span data-stu-id="691fc-190">You can expect the same things with these executables as you would other native executables, such as:</span></span>

* <span data-ttu-id="691fc-191">Haga doble clic en el archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="691fc-191">You can double-click on the executable.</span></span>
* <span data-ttu-id="691fc-192">También puede iniciar la aplicación desde un símbolo del sistema directamente, como `myapp.exe` en Windows y `./myapp` en Linux y macOS.</span><span class="sxs-lookup"><span data-stu-id="691fc-192">You can launch the application from a command prompt directly, such as `myapp.exe` on Windows, and `./myapp` on Linux and macOS.</span></span>

## <a name="build-copies-dependencies"></a><span data-ttu-id="691fc-193">Compilación de dependencias de copias</span><span class="sxs-lookup"><span data-stu-id="691fc-193">Build copies dependencies</span></span>

<span data-ttu-id="691fc-194">`dotnet build` ahora copia las dependencias de NuGet de la aplicación desde la caché de NuGet en la carpeta de salida de compilación.</span><span class="sxs-lookup"><span data-stu-id="691fc-194">`dotnet build` now copies NuGet dependencies for your application from the NuGet cache to the build output folder.</span></span> <span data-ttu-id="691fc-195">Anteriormente, las dependencias solo se copiaban como parte de `dotnet publish`.</span><span class="sxs-lookup"><span data-stu-id="691fc-195">Previously, dependencies were only copied as part of `dotnet publish`.</span></span>

<span data-ttu-id="691fc-196">Hay algunas operaciones, como la publicación de páginas Razor y la vinculación, que aún es necesario publicar.</span><span class="sxs-lookup"><span data-stu-id="691fc-196">There are some operations, like linking and razor page publishing that will still require publishing.</span></span>

## <a name="local-dotnet-tools"></a><span data-ttu-id="691fc-197">Herramientas de dotnet locales</span><span class="sxs-lookup"><span data-stu-id="691fc-197">Local dotnet tools</span></span>

> [!WARNING]
> <span data-ttu-id="691fc-198">Se ha producido un cambio en las herramientas locales de .NET Core entre .NET Core 3.0 (versión preliminar 1) y .NET Core 3.0 (versión preliminar 2).</span><span class="sxs-lookup"><span data-stu-id="691fc-198">There was a change in .NET Core Local Tools between .NET Core 3.0 Preview 1 and .NET Core 3.0 Preview 2.</span></span>  <span data-ttu-id="691fc-199">Si ha probado herramientas locales en la versión preliminar 1 ejecutando un comando como `dotnet tool restore` o `dotnet tool install`, debe eliminar su carpeta de la caché de las herramientas locales antes de que las herramientas locales funcionen correctamente en la versión preliminar 2.</span><span class="sxs-lookup"><span data-stu-id="691fc-199">If you tried out local tools in Preview 1 by running a command like `dotnet tool restore` or `dotnet tool install`, you need to delete your local tools cache folder before local tools will work correctly in Preview 2.</span></span> <span data-ttu-id="691fc-200">Esta carpeta se encuentra en:</span><span class="sxs-lookup"><span data-stu-id="691fc-200">This folder is located at:</span></span>
>
> <span data-ttu-id="691fc-201">En Mac, Linux: `rm -r $HOME/.dotnet/toolResolverCache`</span><span class="sxs-lookup"><span data-stu-id="691fc-201">On mac, Linux: `rm -r $HOME/.dotnet/toolResolverCache`</span></span>
>
> <span data-ttu-id="691fc-202">En Windows: `rmdir /s %USERPROFILE%\.dotnet\toolResolverCache`</span><span class="sxs-lookup"><span data-stu-id="691fc-202">On Windows: `rmdir /s %USERPROFILE%\.dotnet\toolResolverCache`</span></span>
>
> <span data-ttu-id="691fc-203">Si no elimina esta carpeta, recibirá un error.</span><span class="sxs-lookup"><span data-stu-id="691fc-203">If you do not delete this folder, you will receive an error.</span></span>

<span data-ttu-id="691fc-204">Aunque .NET Core 2.1 admitía herramientas globales, .NET Core 3.0 ahora cuenta con herramientas locales.</span><span class="sxs-lookup"><span data-stu-id="691fc-204">While .NET Core 2.1 supported global tools, .NET Core 3.0 now has local tools.</span></span> <span data-ttu-id="691fc-205">Las herramientas locales son similares a las globales, pero están asociadas a una ubicación concreta del disco.</span><span class="sxs-lookup"><span data-stu-id="691fc-205">Local tools are similar to global tools but are associated with a particular location on disk.</span></span> <span data-ttu-id="691fc-206">De este modo, se pueden usar herramientas por proyecto y por repositorio.</span><span class="sxs-lookup"><span data-stu-id="691fc-206">This enables per-project and per-repository tooling.</span></span> <span data-ttu-id="691fc-207">Las herramientas instaladas de forma local no están disponibles de manera global.</span><span class="sxs-lookup"><span data-stu-id="691fc-207">Any tool installed locally isn't available globally.</span></span> <span data-ttu-id="691fc-208">Las herramientas se distribuyen como paquetes NuGet.</span><span class="sxs-lookup"><span data-stu-id="691fc-208">Tools are distributed as NuGet packages.</span></span>

<span data-ttu-id="691fc-209">Las herramientas locales se basan en un nombre de archivo de manifiesto `dotnet-tools.json` del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="691fc-209">Local tools rely on a manifest file name `dotnet-tools.json` in your current directory.</span></span> <span data-ttu-id="691fc-210">Este archivo de manifiesto define las herramientas que estarán disponibles en esa carpeta y a continuación.</span><span class="sxs-lookup"><span data-stu-id="691fc-210">This manifest file defines the tools to be available at that folder and below.</span></span> <span data-ttu-id="691fc-211">Al crear este archivo de manifiesto en la raíz del repositorio, asegúrese de que cualquier usuario que clone el código pueda restaurar y usar las herramientas que se necesitan para trabajar correctamente con el código.</span><span class="sxs-lookup"><span data-stu-id="691fc-211">By creating this manifest file at the root of your repository, you ensure anyone cloning your code can restore and use the tools that are needed to successfully work with your code.</span></span>

<span data-ttu-id="691fc-212">Para crear un archivo de manifiesto `dotnet-tools.json`, use:</span><span class="sxs-lookup"><span data-stu-id="691fc-212">To create a `dotnet-tools.json` manifest file, use:</span></span>

```console
dotnet new tool-manifest
```

<span data-ttu-id="691fc-213">Agregue una nueva herramienta al manifiesto local con:</span><span class="sxs-lookup"><span data-stu-id="691fc-213">Add a new tool to the local manifest with:</span></span>

```console
dotnet tool install <packageId>
```

<span data-ttu-id="691fc-214">También puede enumerar las herramientas en el manifiesto local con:</span><span class="sxs-lookup"><span data-stu-id="691fc-214">You can also list the tools in the local manifest with:</span></span>

```console
dotnet tool list
```

<span data-ttu-id="691fc-215">Para ver qué herramientas se instalan globalmente, use:</span><span class="sxs-lookup"><span data-stu-id="691fc-215">To see what tools are installed globally, use:</span></span>

```console
dotnet tool list -g
```

<span data-ttu-id="691fc-216">Cuando el archivo de manifiesto de herramientas locales está disponible, pero las herramientas definidas en el manifiesto no se han instalado, use el comando siguiente para descargar e instalar automáticamente estas herramientas:</span><span class="sxs-lookup"><span data-stu-id="691fc-216">When the local tools manifest file is available, but the tools defined in the manifest have not been installed, use the following command to automatically download and install those tools:</span></span>

```console
dotnet tool restore
```

<span data-ttu-id="691fc-217">Ejecute una herramienta local con el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="691fc-217">Run a local tool with the following command:</span></span>

```console
dotnet tool run <tool-command-name>
```

<span data-ttu-id="691fc-218">Cuando se ejecuta una herramienta local, dotnet busca un manifiesto en la estructura de directorios actual.</span><span class="sxs-lookup"><span data-stu-id="691fc-218">When a local tool is run, dotnet searches for a manifest up the current directory structure.</span></span> <span data-ttu-id="691fc-219">Cuando se encuentra un archivo de manifiesto de herramientas, se busca la herramienta solicitada.</span><span class="sxs-lookup"><span data-stu-id="691fc-219">When a tool manifest file is found, it is searched for the requested tool.</span></span> <span data-ttu-id="691fc-220">Si la herramienta se encuentra en el manifiesto, pero no en la caché, el usuario recibe un error y debe ejecutar `dotnet tool restore`.</span><span class="sxs-lookup"><span data-stu-id="691fc-220">If the tool is found in the manifest, but not the cache, the user receives an error and needs to run `dotnet tool restore`.</span></span>

<span data-ttu-id="691fc-221">Para quitar una herramienta del archivo de manifiesto de herramientas locales, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="691fc-221">To remove a tool from the local tool manifest file, run the following command:</span></span>

```console
dotnet tool uninstall <packageId>
```

<span data-ttu-id="691fc-222">El archivo de manifiesto de herramientas está diseñado para poder modificarse manualmente (podría hacerlo para actualizar la versión necesaria para trabajar con el repositorio).</span><span class="sxs-lookup"><span data-stu-id="691fc-222">The tool manifest file is designed to allow hand editing – which you might do to update the required version for working with the repository.</span></span> <span data-ttu-id="691fc-223">A continuación, se muestra un archivo `dotnet-tools.json` de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="691fc-223">Here is an example `dotnet-tools.json` file:</span></span>

```json
{
  "version": 1,
  "isRoot": true,
  "tools": {
    "dotnetsay": {
      "version": "2.1.4",
      "commands": [
        "dotnetsay"
      ]
    },
    "t-rex": {
      "version": "1.0.103",
      "commands": [
        "t-rex"
      ]
    }
  }
}
```

<span data-ttu-id="691fc-224">Para las herramientas locales y globales, se requiere una versión compatible del entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="691fc-224">For both global and local tools, a compatible version of the runtime is required.</span></span> <span data-ttu-id="691fc-225">Actualmente, muchas herramientas de NuGet.org tienen como destino el entorno de ejecución de .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="691fc-225">Many tools currently on NuGet.org target .NET Core Runtime 2.1.</span></span> <span data-ttu-id="691fc-226">Para instalarlas de forma global o local, aún es necesario instalar el [entorno de ejecución de .NET Core 2.1](https://dotnet.microsoft.com/download/dotnet-core/2.1).</span><span class="sxs-lookup"><span data-stu-id="691fc-226">To install those globally or locally, you would still need to install the [NET Core 2.1 Runtime](https://dotnet.microsoft.com/download/dotnet-core/2.1).</span></span>

## <a name="windows-desktop"></a><span data-ttu-id="691fc-227">Escritorio de Windows</span><span class="sxs-lookup"><span data-stu-id="691fc-227">Windows desktop</span></span>

<span data-ttu-id="691fc-228">A partir de la versión preliminar 1 de .NET Core 3.0, puede compilar aplicaciones de Escritorio de Windows con WPF y Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="691fc-228">Starting with .NET Core 3.0 Preview 1, you can build Windows desktop applications using WPF and Windows Forms.</span></span> <span data-ttu-id="691fc-229">Estos marcos también admiten el uso de controles modernos y los estilos de Fluent de la biblioteca de XAML de la interfaz de usuario de Windows (WinUI) a través de [islas XAML](/windows/uwp/xaml-platform/xaml-host-controls).</span><span class="sxs-lookup"><span data-stu-id="691fc-229">These frameworks also support using modern controls and Fluent styling from the Windows UI XAML Library (WinUI) via [XAML islands](/windows/uwp/xaml-platform/xaml-host-controls).</span></span>

<span data-ttu-id="691fc-230">El componente Escritorio de Windows forma parte del SDK de Windows .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="691fc-230">The Windows Desktop component is part of the Windows .NET Core 3.0 SDK.</span></span>

<span data-ttu-id="691fc-231">Puede crear una aplicación de Windows Forms o WPF con los siguientes comandos `dotnet`:</span><span class="sxs-lookup"><span data-stu-id="691fc-231">You can create a new WPF or Windows Forms app with the following `dotnet` commands:</span></span>

```console
dotnet new wpf
dotnet new winforms
```

<span data-ttu-id="691fc-232">Visual Studio 2019 agrega plantillas de **nuevo proyecto** para WPF y Windows Forms de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="691fc-232">Visual Studio 2019 adds **New Project** templates for .NET Core 3.0 Windows Forms and WPF.</span></span> <span data-ttu-id="691fc-233">Los diseñadores aún no se admiten.</span><span class="sxs-lookup"><span data-stu-id="691fc-233">Designers are still not yet supported.</span></span> <span data-ttu-id="691fc-234">Y puede abrir, iniciar y depurar estos proyectos en Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="691fc-234">And you can open, launch, and debug these projects in Visual Studio 2019.</span></span>

<span data-ttu-id="691fc-235">Visual Studio 2017 15.9 agrega la capacidad de [habilitar versiones preliminares de .NET Core](https://devblogs.microsoft.com/dotnet/net-core-tooling-update-for-visual-studio-2017-version-15-9/), pero debe activar esa característica y no es un escenario admitido.</span><span class="sxs-lookup"><span data-stu-id="691fc-235">Visual Studio 2017 15.9 adds the ability to [enable .NET Core previews](https://devblogs.microsoft.com/dotnet/net-core-tooling-update-for-visual-studio-2017-version-15-9/), but you need to turn that feature on, and it's not a supported scenario.</span></span>

<span data-ttu-id="691fc-236">Los nuevos proyectos son los mismos que los existentes de .NET Core, con algunas adiciones.</span><span class="sxs-lookup"><span data-stu-id="691fc-236">The new projects are the same as existing .NET Core projects, with a couple additions.</span></span> <span data-ttu-id="691fc-237">Esta es la comparación del proyecto de consola de .NET Core básico y un proyecto básico de Windows Forms y WPF.</span><span class="sxs-lookup"><span data-stu-id="691fc-237">Here is the comparison of the basic .NET Core console project and a basic Windows Forms and WPF project.</span></span>

<span data-ttu-id="691fc-238">En un proyecto de consola de .NET Core, se usa el SDK `Microsoft.NET.Sdk` y se declara una dependencia en .NET Core 3.0 a través del marco de destino `netcoreapp3.0`.</span><span class="sxs-lookup"><span data-stu-id="691fc-238">In a .NET Core console project, the project uses the `Microsoft.NET.Sdk` SDK and declares a dependency on .NET Core 3.0 via the `netcoreapp3.0` target framework.</span></span> <span data-ttu-id="691fc-239">Para crear una aplicación de Escritorio de Windows, use el SDK `Microsoft.NET.Sdk.WindowsDesktop` y elija qué marco de interfaz de usuario usará:</span><span class="sxs-lookup"><span data-stu-id="691fc-239">To create a Windows Desktop app, use the `Microsoft.NET.Sdk.WindowsDesktop` SDK and choose which UI framework to use:</span></span>

```diff
-<Project Sdk="Microsoft.NET.Sdk">
+<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
+   <UseWPF>true</UseWPF>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="691fc-240">Para elegir Windows Forms en WPF, establezca `UseWindowsForms` en lugar de `UseWPF`:</span><span class="sxs-lookup"><span data-stu-id="691fc-240">To choose Windows Forms over WPF, set `UseWindowsForms` instead of `UseWPF`:</span></span>

```diff
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
-   <UseWPF>true</UseWPF>
+   <UseWindowsForms>true</UseWindowsForms>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="691fc-241">`UseWPF` y `UseWindowsForms` se puede establecer en `true` si la aplicación usa ambos marcos, por ejemplo, cuando un cuadro de diálogo de Windows Forms hospeda un control de WPF.</span><span class="sxs-lookup"><span data-stu-id="691fc-241">Both `UseWPF` and `UseWindowsForms` can be set to `true` if the app uses both frameworks, for example when a Windows Forms dialog is hosting a WPF control.</span></span>

<span data-ttu-id="691fc-242">Comparta sus comentarios en los repositorios [dotnet/winforms](https://github.com/dotnet/winforms/issues), [dotnet/wpf](https://github.com/dotnet/wpf/issues) y [dotnet/core](https://github.com/dotnet/core/issues).</span><span class="sxs-lookup"><span data-stu-id="691fc-242">Please share your feedback on the [dotnet/winforms](https://github.com/dotnet/winforms/issues),  [dotnet/wpf](https://github.com/dotnet/wpf/issues) and [dotnet/core](https://github.com/dotnet/core/issues) repos.</span></span>

## <a name="msix-deployment-for-windows-desktop"></a><span data-ttu-id="691fc-243">Implementación de MSIX para escritorio de Windows</span><span class="sxs-lookup"><span data-stu-id="691fc-243">MSIX Deployment for Windows Desktop</span></span>

<span data-ttu-id="691fc-244">[MSIX](https://docs.microsoft.com/windows/msix/) es un nuevo formato del paquete de la aplicación de Windows.</span><span class="sxs-lookup"><span data-stu-id="691fc-244">[MSIX](https://docs.microsoft.com/windows/msix/) is a new Windows app package format.</span></span> <span data-ttu-id="691fc-245">Se puede usar para implementar aplicaciones de escritorio de .NET Core 3.0 en Windows 10.</span><span class="sxs-lookup"><span data-stu-id="691fc-245">It can be used to deploy .NET Core 3.0 desktop applications to Windows 10.</span></span>

<span data-ttu-id="691fc-246">El [proyecto de paquete de aplicación de Windows](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-packaging-dot-net), disponible en Visual Studio 2019, le permite crear paquetes de MSIX con aplicaciones de .NET Core [independientes](../deploying/index.md#self-contained-deployments-scd).</span><span class="sxs-lookup"><span data-stu-id="691fc-246">The [Windows Application Packaging Project](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-packaging-dot-net), available in Visual Studio 2019, allows you to create MSIX packages with [self-contained](../deploying/index.md#self-contained-deployments-scd) .NET Core applications.</span></span>

> [!NOTE]
> <span data-ttu-id="691fc-247">El archivo del proyecto de .NET Core debe especificar los tiempos de ejecución admitidos en la propiedad `<RuntimeIdentifiers>`:</span><span class="sxs-lookup"><span data-stu-id="691fc-247">The .NET Core project file must specify the supported runtimes in the `<RuntimeIdentifiers>` property:</span></span>
>
> ```xml
> <RuntimeIdentifiers>win-x86;win-x64</RuntimeIdentifiers>
> ```

## <a name="fast-built-in-json-support"></a><span data-ttu-id="691fc-248">Compatibilidad con JSON integrada con rápido rendimiento</span><span class="sxs-lookup"><span data-stu-id="691fc-248">Fast built-in JSON support</span></span>

<span data-ttu-id="691fc-249">El ecosistema .NET depende de [**Json.NET**](https://www.newtonsoft.com/json) y otras bibliotecas populares de JSON, que siguen siendo buenas opciones.</span><span class="sxs-lookup"><span data-stu-id="691fc-249">The .NET ecosystem has relied on [**Json.NET**](https://www.newtonsoft.com/json) and other popular JSON libraries, which continue to be good choices.</span></span> <span data-ttu-id="691fc-250">**Json.NET** utiliza cadenas .NET como su tipo de datos base, que son UTF-16 en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="691fc-250">**Json.NET** uses .NET strings as its base datatype, which are UTF-16 under the hood.</span></span>

<span data-ttu-id="691fc-251">La nueva compatibilidad con JSON integrada es el alto rendimiento, una baja asignación y se basa en `Span<byte>`.</span><span class="sxs-lookup"><span data-stu-id="691fc-251">The new built-in JSON support is high-performance, low allocation, and based on `Span<byte>`.</span></span> <span data-ttu-id="691fc-252">Se han agregado tres nuevos tipos relacionados con JSON principales a .NET Core 3.0 y el espacio de nombres `System.Text.Json`.</span><span class="sxs-lookup"><span data-stu-id="691fc-252">Three new main JSON-related types have been added to .NET Core 3.0 the `System.Text.Json` namespace.</span></span>

### <a name="utf8jsonreader"></a><span data-ttu-id="691fc-253">Utf8JsonReader</span><span class="sxs-lookup"><span data-stu-id="691fc-253">Utf8JsonReader</span></span>

<span data-ttu-id="691fc-254">`System.Text.Json.Utf8JsonReader` es un lector de solo avance, de baja asignación y de alto rendimiento para texto JSON con codificación UTF-8 que se lee desde `ReadOnlySpan<byte>`.</span><span class="sxs-lookup"><span data-stu-id="691fc-254">`System.Text.Json.Utf8JsonReader` is a high-performance, low allocation, forward-only reader for UTF-8 encoded JSON text, read from a `ReadOnlySpan<byte>`.</span></span> <span data-ttu-id="691fc-255">`Utf8JsonReader` es un tipo fundamental de bajo nivel que puede utilizarse para crear analizadores y deserializadores personalizados.</span><span class="sxs-lookup"><span data-stu-id="691fc-255">The `Utf8JsonReader` is a foundational, low-level type, that can be leveraged to build custom parsers and deserializers.</span></span> <span data-ttu-id="691fc-256">La lectura a través de una carga JSON con el nuevo lector `Utf8JsonReader` es el doble de rápido que con el lector de **Json.NET**.</span><span class="sxs-lookup"><span data-stu-id="691fc-256">Reading through a JSON payload using the new `Utf8JsonReader` is 2x faster than using the reader from **Json.NET**.</span></span> <span data-ttu-id="691fc-257">No se realiza la asignación hasta que se necesite actualizar los tokens JSON como cadenas (UTF-16).</span><span class="sxs-lookup"><span data-stu-id="691fc-257">It does not allocate until you need to actualize JSON tokens as (UTF-16) strings.</span></span>

<span data-ttu-id="691fc-258">Esta nueva API incluirá los siguientes componentes:</span><span class="sxs-lookup"><span data-stu-id="691fc-258">This new API will include the following components:</span></span>

* <span data-ttu-id="691fc-259">En la versión preliminar 1: lector JSON (acceso secuencial)</span><span class="sxs-lookup"><span data-stu-id="691fc-259">In Preview 1: JSON reader (sequential access)</span></span>
* <span data-ttu-id="691fc-260">Próximamente: escritor JSON, DOM (acceso aleatorio), y serializador y deserializador poco</span><span class="sxs-lookup"><span data-stu-id="691fc-260">Coming next: JSON writer, DOM (random access), poco serializer, poco deserializer</span></span>

<span data-ttu-id="691fc-261">Este es el bucle de lectura básico para el lector `Utf8JsonReader` que puede utilizarse como punto inicial:</span><span class="sxs-lookup"><span data-stu-id="691fc-261">Here is the basic reader loop for the `Utf8JsonReader` that can be used as a starting point:</span></span>

```csharp
using System.Text.Json;

public static void Utf8JsonReaderLoop(ReadOnlySpan<byte> dataUtf8)
{
    var json = new Utf8JsonReader(dataUtf8, isFinalBlock: true, state: default);

    while (json.Read())
    {
        JsonTokenType tokenType = json.TokenType;
        ReadOnlySpan<byte> valueSpan = json.ValueSpan;
        switch (tokenType)
        {
            case JsonTokenType.StartObject:
            case JsonTokenType.EndObject:
                break;
            case JsonTokenType.StartArray:
            case JsonTokenType.EndArray:
                break;
            case JsonTokenType.PropertyName:
                break;
            case JsonTokenType.String:
                string valueString = json.GetStringValue();
                break;
            case JsonTokenType.Number:
                if (!json.TryGetInt32Value(out int valueInteger))
                {
                    throw new FormatException();
                }
                break;
            case JsonTokenType.True:
            case JsonTokenType.False:
                bool valueBool = json.GetBooleanValue();
                break;
            case JsonTokenType.Null:
                break;
            default:
                throw new ArgumentException();
        }
    }

    dataUtf8 = dataUtf8.Slice((int)json.BytesConsumed);
    JsonReaderState state = json.CurrentState;
}
```

### <a name="utf8jsonwriter"></a><span data-ttu-id="691fc-262">Utf8JsonWriter</span><span class="sxs-lookup"><span data-stu-id="691fc-262">Utf8JsonWriter</span></span>

<span data-ttu-id="691fc-263">`System.Text.Json.Utf8JsonWriter` proporciona una forma de escribir texto JSON con codificación UTF-8 de alto rendimiento, sin almacenar en caché y de solo avance a partir de tipos de .NET comunes como `String`, `Int32` y `DateTime`.</span><span class="sxs-lookup"><span data-stu-id="691fc-263">`System.Text.Json.Utf8JsonWriter` provides a high-performance, non-cached, forward-only way to write UTF-8 encoded JSON text from common .NET types like `String`, `Int32`, and `DateTime`.</span></span> <span data-ttu-id="691fc-264">Al igual que el lector, el escritor es un tipo fundamental de bajo nivel que puede utilizarse para crear serializadores personalizados.</span><span class="sxs-lookup"><span data-stu-id="691fc-264">Like the reader, the writer is a foundational, low-level type, that can be leveraged to build custom serializers.</span></span> <span data-ttu-id="691fc-265">Escribir una carga útil JSON con el nuevo `Utf8JsonWriter` es entre un 30 y un 80% más rápido que usar el escritor de **Json.NET** y no asigna.</span><span class="sxs-lookup"><span data-stu-id="691fc-265">Writing a JSON payload using the new `Utf8JsonWriter` is 30-80% faster than using the writer from **Json.NET** and does not allocate.</span></span>

<span data-ttu-id="691fc-266">A continuación se muestra un uso del ejemplo del `Utf8JsonWriter` que se puede utilizar como punto inicial:</span><span class="sxs-lookup"><span data-stu-id="691fc-266">Here is a sample usage of the `Utf8JsonWriter` that can be used as a starting point:</span></span>

```csharp
static int WriteJson(IBufferWriter<byte> output, long[] extraData)
{
    var json = new Utf8JsonWriter(output, state: default);

    json.WriteStartObject();

    json.WriteNumber("age", 15, escape: false);
    json.WriteString("date", DateTime.Now);
    json.WriteString("first", "John");
    json.WriteString("last", "Smith");

    json.WriteStartArray("phoneNumbers", escape: false);
    json.WriteStringValue("425-000-1212", escape: false);
    json.WriteStringValue("425-000-1213");
    json.WriteEndArray();

    json.WriteStartObject("address");
    json.WriteString("street", "1 Microsoft Way");
    json.WriteString("city", "Redmond");
    json.WriteNumber("zip", 98052);
    json.WriteEndObject();

    json.WriteStartArray("ExtraArray");
    for (var i = 0; i < extraData.Length; i++)
    {
        json.WriteNumberValue(extraData[i]);
    }
    json.WriteEndArray();

    json.WriteEndObject();

    json.Flush(isFinalBlock: true);

    return (int)json.BytesWritten;
}
```

<span data-ttu-id="691fc-267">El `Utf8JsonWriter` acepta `IBufferWriter<byte>` como la ubicación de resultados en la que se van a escribir de forma sincrónica los datos JSON y, usted, como autor de llamada, debe proporcionar una implementación concreta.</span><span class="sxs-lookup"><span data-stu-id="691fc-267">The `Utf8JsonWriter` accepts `IBufferWriter<byte>` as the output location to synchronously write the json data into, and you as the caller need to provide a concrete implementation.</span></span> <span data-ttu-id="691fc-268">La plataforma no incluye actualmente una implementación de esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="691fc-268">The platform does not currently include an implementation of this interface.</span></span> <span data-ttu-id="691fc-269">Para ver un ejemplo de `IBufferWriter<byte>`, consulte <https://gist.github.com/ahsonkhan/c76a1cc4dc7107537c3fdc0079a68b35>.</span><span class="sxs-lookup"><span data-stu-id="691fc-269">For an example of `IBufferWriter<byte>`, see <https://gist.github.com/ahsonkhan/c76a1cc4dc7107537c3fdc0079a68b35>.</span></span>

### <a name="jsondocument"></a><span data-ttu-id="691fc-270">JsonDocument</span><span class="sxs-lookup"><span data-stu-id="691fc-270">JsonDocument</span></span>

<span data-ttu-id="691fc-271">`System.Text.Json.JsonDocument` se basa en `Utf8JsonReader`.</span><span class="sxs-lookup"><span data-stu-id="691fc-271">`System.Text.Json.JsonDocument` is built on top of the `Utf8JsonReader`.</span></span> <span data-ttu-id="691fc-272">`JsonDocument` proporciona la capacidad de analizar datos JSON y crear un Document Object Model (DOM) de solo lectura que se puede consultar para admitir el acceso aleatorio y la enumeración.</span><span class="sxs-lookup"><span data-stu-id="691fc-272">The `JsonDocument` provides the ability to parse JSON data and build a read-only Document Object Model (DOM) that can be queried to support random access and enumeration.</span></span> <span data-ttu-id="691fc-273">Se puede obtener acceso a los elementos JSON que redactan los datos a través del tipo `JsonElement` expuesto por `JsonDocument` como una propiedad llamada `RootElement`.</span><span class="sxs-lookup"><span data-stu-id="691fc-273">The JSON elements that compose the data can be accessed via the `JsonElement` type which is exposed by the `JsonDocument` as a property called `RootElement`.</span></span> <span data-ttu-id="691fc-274">El `JsonElement` contiene la matriz de JSON y enumeradores del objeto junto con las API para convertir texto JSON en tipos de .NET comunes.</span><span class="sxs-lookup"><span data-stu-id="691fc-274">The `JsonElement` contains the JSON array and object enumerators along with APIs to convert JSON text to common .NET types.</span></span> <span data-ttu-id="691fc-275">El análisis de una carga útil JSON típica y el acceso a todos sus miembros con el `JsonDocument` son de dos a tres veces más rápidos que **Json.NET** con asignaciones muy pequeñas de datos redimensionados de forma razonable (p. ej., inferiores a 1 MB).</span><span class="sxs-lookup"><span data-stu-id="691fc-275">Parsing a typical JSON payload and accessing all its members using the `JsonDocument` is 2-3x faster than **Json.NET** with very little allocations for data that is reasonably sized (i.e. < 1 MB).</span></span>

<span data-ttu-id="691fc-276">A continuación se muestra un uso del ejemplo del `JsonDocument` y `JsonElement` que se puede utilizar como punto inicial:</span><span class="sxs-lookup"><span data-stu-id="691fc-276">Here is a sample usage of the `JsonDocument` and `JsonElement` that can be used as a starting point:</span></span>

```csharp
static double ParseJson()
{
    const string json = " [ { \"name\": \"John\" }, [ \"425-000-1212\", 15 ], { \"grades\": [ 90, 80, 100, 75 ] } ]";

    double average = -1;

    using (JsonDocument doc = JsonDocument.Parse(json))
    {
        JsonElement root = doc.RootElement;
        JsonElement info = root[1];

        string phoneNumber = info[0].GetString();
        int age = info[1].GetInt32();

        JsonElement grades = root[2].GetProperty("grades");

        double sum = 0;
        foreach (JsonElement grade in grades.EnumerateArray())
        {
            sum += grade.GetInt32();
        }

        int numberOfCourses = grades.GetArrayLength();
        average = sum / numberOfCourses;
    }

    return average;
}
```

## <a name="assembly-unloadability"></a><span data-ttu-id="691fc-277">Descargabilidad de ensamblado</span><span class="sxs-lookup"><span data-stu-id="691fc-277">Assembly Unloadability</span></span>

<span data-ttu-id="691fc-278">La descargabilidad de ensamblado es una nueva funcionalidad de `AssemblyLoadContext`.</span><span class="sxs-lookup"><span data-stu-id="691fc-278">Assembly unloadability is a new capability of `AssemblyLoadContext`.</span></span> <span data-ttu-id="691fc-279">Esta nueva característica es transparente en gran medida desde una perspectiva de la API, exponiéndose con solo algunas API nuevas.</span><span class="sxs-lookup"><span data-stu-id="691fc-279">This new feature is largely transparent from an API perspective, exposed with just a few new APIs.</span></span> <span data-ttu-id="691fc-280">Habilita un contexto de cargador que se va a descargar, liberando toda la memoria para tipos de los que se creó una instancia, campos estáticos y el propio ensamblado.</span><span class="sxs-lookup"><span data-stu-id="691fc-280">It enables a loader context to be unloaded, releasing all memory for instantiated types, static fields and for the assembly itself.</span></span> <span data-ttu-id="691fc-281">Una aplicación debe poder cargar y descargar ensamblados a través de este mecanismo para siempre sin experimentar una fuga de memoria.</span><span class="sxs-lookup"><span data-stu-id="691fc-281">An application should be able to load and unload assemblies via this mechanism forever without experiencing a memory leak.</span></span>

<span data-ttu-id="691fc-282">Esta nueva funcionalidad se puede usar para escenarios similares a:</span><span class="sxs-lookup"><span data-stu-id="691fc-282">This new capability can be used for scenarios similar to:</span></span>

* <span data-ttu-id="691fc-283">Escenarios de complemento donde se requiere la carga y descarga dinámica de complementos.</span><span class="sxs-lookup"><span data-stu-id="691fc-283">Plugin scenarios where dynamic plugin loading and unloading is required.</span></span>
* <span data-ttu-id="691fc-284">Compilación, ejecución y posterior vaciado dinámicos de código.</span><span class="sxs-lookup"><span data-stu-id="691fc-284">Dynamically compiling, running and then flushing code.</span></span> <span data-ttu-id="691fc-285">Útil para sitios web, motores de scripting, etc.</span><span class="sxs-lookup"><span data-stu-id="691fc-285">Useful for web sites, scripting engines, etc.</span></span>
* <span data-ttu-id="691fc-286">Carga de ensamblados para la introspección (como ReflectionOnlyLoad), aunque [MetadataLoadContext](#type-metadataloadcontext) (lanzado en la versión preliminar 1) será una mejor opción en muchos casos.</span><span class="sxs-lookup"><span data-stu-id="691fc-286">Loading assemblies for introspection (like ReflectionOnlyLoad), although [MetadataLoadContext](#type-metadataloadcontext) (released in Preview 1) will be a better choice in many cases.</span></span>

<span data-ttu-id="691fc-287">Para obtener más información, consulte el documento [Using Unloadability](https://github.com/dotnet/coreclr/pull/22221) (Uso de descargabilidad).</span><span class="sxs-lookup"><span data-stu-id="691fc-287">For more information, see the [Using Unloadability](https://github.com/dotnet/coreclr/pull/22221) document.</span></span>

<span data-ttu-id="691fc-288">La descargabilidad de ensamblado requiere una atención significativa para garantizar que todas las referencias a objetos administrados desde fuera de un contexto de cargador se entiendan y administren.</span><span class="sxs-lookup"><span data-stu-id="691fc-288">Assembly unloading requires significant care to ensure that all references to managed objects from outside a loader context are understood and managed.</span></span> <span data-ttu-id="691fc-289">Al solicitarse la descarga del contexto de cargador, es necesario que no se haya hecho referencia a ninguna referencia externa para que el contexto de cargador sea coherente solo consigo mismo.</span><span class="sxs-lookup"><span data-stu-id="691fc-289">When the loader context is requested to be unloaded, any outside references need to have been unreferenced so that the loader context is self-consistent only to itself.</span></span>

<span data-ttu-id="691fc-290">Los dominios de aplicación (AppDomains) proporcionaron la descargabilidad de ensamblado en .NET Framework. Estos no se admiten con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="691fc-290">Assembly unloadability was provided in the .NET Framework by Application Domains (AppDomains), which are not supported with .NET Core.</span></span> <span data-ttu-id="691fc-291">AppDomains contaban tanto con ventajas como con limitaciones en comparación con este nuevo modelo.</span><span class="sxs-lookup"><span data-stu-id="691fc-291">AppDomains had both benefits and limitations compared to this new model.</span></span> <span data-ttu-id="691fc-292">Considere la posibilidad de que este nuevo modelo de cargador sea más flexible y tenga un rendimiento más alto en comparación con AppDomains.</span><span class="sxs-lookup"><span data-stu-id="691fc-292">Consider this new loader model to be more flexible and higher performant when compared to AppDomains.</span></span>

## <a name="windows-native-interop"></a><span data-ttu-id="691fc-293">Interoperabilidad nativa de Windows</span><span class="sxs-lookup"><span data-stu-id="691fc-293">Windows Native Interop</span></span>

<span data-ttu-id="691fc-294">Windows ofrece una API nativa enriquecida con formato de API de C planas, COM y WinRT.</span><span class="sxs-lookup"><span data-stu-id="691fc-294">Windows offers a rich native API, in the form of flat C APIs, COM, and WinRT.</span></span> <span data-ttu-id="691fc-295">Desde .NET Core 1.0, se ha admitido **P/Invoke**.</span><span class="sxs-lookup"><span data-stu-id="691fc-295">Since .NET Core 1.0, **P/Invoke** has been supported.</span></span> <span data-ttu-id="691fc-296">Ahora con .NET Core 3.0, se ha agregado la compatibilidad con la capacidad de **CoCreate COM APIs** (Cocrear API de COM) y **Activate WinRT APIs** (Activar API de WinRT).</span><span class="sxs-lookup"><span data-stu-id="691fc-296">Now with .NET Core 3.0, support for the ability to **CoCreate COM APIs** and **Activate WinRT APIs** has been added.</span></span>

<span data-ttu-id="691fc-297">Puede ver un ejemplo de uso de COM con el [código fuente de demostración de Excel](https://github.com/dotnet/samples/tree/master/core/extensions/ExcelDemo).</span><span class="sxs-lookup"><span data-stu-id="691fc-297">You can see an example of using COM with the [Excel Demo source code](https://github.com/dotnet/samples/tree/master/core/extensions/ExcelDemo).</span></span>

## <a name="type-sequencereader"></a><span data-ttu-id="691fc-298">Tipo: SequenceReader</span><span class="sxs-lookup"><span data-stu-id="691fc-298">Type: SequenceReader</span></span>

<span data-ttu-id="691fc-299">En .NET Core 3.0, se ha agregado `System.Buffers.SequenceReader`, que se puede usar como lector de `ReadOnlySequence<T>`.</span><span class="sxs-lookup"><span data-stu-id="691fc-299">In .NET Core 3.0, `System.Buffers.SequenceReader` has been added which can be used as a reader for `ReadOnlySequence<T>`.</span></span> <span data-ttu-id="691fc-300">De este modo, se puede realizar un análisis de alto rendimiento y de asignación baja de los datos `System.IO.Pipelines` que pueden atravesar varios búferes de respaldo.</span><span class="sxs-lookup"><span data-stu-id="691fc-300">This allows easy, high performance, low allocation parsing of `System.IO.Pipelines` data that can cross multiple backing buffers.</span></span>

<span data-ttu-id="691fc-301">En el ejemplo siguiente, se interrumpe una entrada `Sequence` en las líneas delimitadas `CR/LF` válidas:</span><span class="sxs-lookup"><span data-stu-id="691fc-301">The following example breaks an input `Sequence` into valid `CR/LF` delimited lines:</span></span>

```csharp
private static ReadOnlySpan<byte> CRLF => new byte[] { (byte)'\r', (byte)'\n' };

public static void ReadLines(ReadOnlySequence<byte> sequence)
{
    SequenceReader<byte> reader = new SequenceReader<byte>(sequence);

    while (!reader.End)
    {
        if (!reader.TryReadToAny(out ReadOnlySpan<byte> line, CRLF, advancePastDelimiter:false))
        {
            // Couldn't find another delimiter
            // ...
        }

        if (!reader.IsNext(CRLF, advancePast: true))
        {
            // Not a good CR/LF pair
            // ...
        }

        // line is valid, process
        ProcessLine(line);
    }
}
```

## <a name="type-metadataloadcontext"></a><span data-ttu-id="691fc-302">Tipo: MetadataLoadContext</span><span class="sxs-lookup"><span data-stu-id="691fc-302">Type: MetadataLoadContext</span></span>

<span data-ttu-id="691fc-303">Se ha agregado el tipo `MetadataLoadContext` que permite leer los metadatos de ensamblado sin que afecte al dominio de aplicación del llamador.</span><span class="sxs-lookup"><span data-stu-id="691fc-303">The `MetadataLoadContext` type has been added that enables reading assembly metadata without affecting the caller’s application domain.</span></span> <span data-ttu-id="691fc-304">Los ensamblados se leen como datos, incluidos los ensamblados compilados para arquitecturas y plataformas distintas al entorno en tiempo de ejecución actual.</span><span class="sxs-lookup"><span data-stu-id="691fc-304">Assemblies are read as data, including assemblies built for different architectures and platforms than the current runtime environment.</span></span> <span data-ttu-id="691fc-305">`MetadataLoadContext` se superpone con <xref:System.Reflection.Assembly.ReflectionOnlyLoad*>, que solo está disponible en .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="691fc-305">`MetadataLoadContext` overlaps with the <xref:System.Reflection.Assembly.ReflectionOnlyLoad*>, which is only available in the .NET Framework.</span></span>

<span data-ttu-id="691fc-306">`MetdataLoadContext` está disponible en el paquete [System.Reflection.MetadataLoadContext](https://www.nuget.org/packages/System.Reflection.MetadataLoadContext).</span><span class="sxs-lookup"><span data-stu-id="691fc-306">`MetdataLoadContext` is available in the [System.Reflection.MetadataLoadContext package](https://www.nuget.org/packages/System.Reflection.MetadataLoadContext).</span></span> <span data-ttu-id="691fc-307">Se trata de un paquete de .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="691fc-307">It is a .NET Standard 2.0 package.</span></span>

<span data-ttu-id="691fc-308">`MetadataLoadContext`expone las API similares al tipo <xref:System.Runtime.Loader.AssemblyLoadContext>, pero no se basa en ese tipo.</span><span class="sxs-lookup"><span data-stu-id="691fc-308">The `MetadataLoadContext` exposes APIs similar to the <xref:System.Runtime.Loader.AssemblyLoadContext> type, but is not based on that type.</span></span> <span data-ttu-id="691fc-309">De forma similar a <xref:System.Runtime.Loader.AssemblyLoadContext>, `MetadataLoadContext` habilita la carga de ensamblados dentro del universo de carga de ensamblados aislados.</span><span class="sxs-lookup"><span data-stu-id="691fc-309">Much like <xref:System.Runtime.Loader.AssemblyLoadContext>, the `MetadataLoadContext` enables loading assemblies within an isolated assembly loading universe.</span></span> <span data-ttu-id="691fc-310">Las API de `MetdataLoadContext` devuelven objetos <xref:System.Reflection.Assembly>, lo que permite el uso de API de reflexión conocidas.</span><span class="sxs-lookup"><span data-stu-id="691fc-310">`MetdataLoadContext` APIs return <xref:System.Reflection.Assembly> objects, enabling the use of familiar reflection APIs.</span></span> <span data-ttu-id="691fc-311">Las API orientadas a la ejecución, como [MethodBase.Invoke](https://github.com/dotnet/corefx/blob/master/src/System.Reflection.MetadataLoadContext/src/System/Reflection/TypeLoading/Methods/RoMethod.cs#L127), no se permiten y generan la excepción InvalidOperationException.</span><span class="sxs-lookup"><span data-stu-id="691fc-311">Execution-oriented APIs, such as [MethodBase.Invoke](https://github.com/dotnet/corefx/blob/master/src/System.Reflection.MetadataLoadContext/src/System/Reflection/TypeLoading/Methods/RoMethod.cs#L127), are not allowed and will throw InvalidOperationException.</span></span>

<span data-ttu-id="691fc-312">El ejemplo siguiente muestra cómo buscar tipos concretos en un ensamblado que implementa una interfaz determinada:</span><span class="sxs-lookup"><span data-stu-id="691fc-312">The following sample demonstrates how to find concrete types in an assembly that implements a given interface:</span></span>

```csharp
var paths = new string[] {@"C:\myapp\mscorlib.dll", @"C:\myapp\myapp.dll"};
var resolver = new PathAssemblyResolver(paths);
using (var lc = new MetadataLoadContext(resolver))
{
    Assembly a = lc.LoadFromAssemblyName("myapp");
    Type myInterface = a.GetType("MyApp.IPluginInterface");
    foreach (Type t in a.GetTypes())
    {
        if (t.IsClass && myInterface.IsAssignableFrom(t))
            Console.WriteLine($"Class {t.FullName} implements IPluginInterface");
    }
}
```

<span data-ttu-id="691fc-313">Los escenarios para `MetadataLoadContext` incluyen características de tiempo de diseño, herramientas de tiempo de compilación y características de alumbrado en tiempo de ejecución que necesitan inspeccionar un conjunto de ensamblados como datos y que tienen todos los bloqueos de archivo y la memoria liberada después de la inspección.</span><span class="sxs-lookup"><span data-stu-id="691fc-313">Scenarios for `MetadataLoadContext` include design-time features, build-time tooling, and runtime light-up features that need to inspect a set of assemblies as data and have all file locks and memory freed after inspection is performed.</span></span>

<span data-ttu-id="691fc-314">`MetadataLoadContext` tiene una clase de resolución que se transmite a su constructor.</span><span class="sxs-lookup"><span data-stu-id="691fc-314">The `MetadataLoadContext` has a resolver class passed to its constructor.</span></span> <span data-ttu-id="691fc-315">El trabajo de la resolución consiste en cargar un ensamblado `Assembly` dado su `AssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="691fc-315">The resolver's job is to load an `Assembly` given its `AssemblyName`.</span></span> <span data-ttu-id="691fc-316">La clase de la resolución se deriva de la clase abstracta `MetadataAssemblyResolver`.</span><span class="sxs-lookup"><span data-stu-id="691fc-316">The resolver class derives from the abstract `MetadataAssemblyResolver` class.</span></span> <span data-ttu-id="691fc-317">Se proporciona una implementación de la resolución para escenarios basados en rutas de acceso con `PathAssemblyResolver`.</span><span class="sxs-lookup"><span data-stu-id="691fc-317">An implementation of the resolver for path-based scenarios is provided with `PathAssemblyResolver`.</span></span>

<span data-ttu-id="691fc-318">[MetadataLoadContext pruebas](https://github.com/dotnet/corefx/tree/master/src/System.Reflection.MetadataLoadContext/tests/src/Tests) muestra muchos casos de uso.</span><span class="sxs-lookup"><span data-stu-id="691fc-318">The [MetadataLoadContext tests](https://github.com/dotnet/corefx/tree/master/src/System.Reflection.MetadataLoadContext/tests/src/Tests) demonstrate many use cases.</span></span> <span data-ttu-id="691fc-319">Las [pruebas de ensamblado](https://github.com/dotnet/corefx/blob/master/src/System.Reflection.MetadataLoadContext/tests/src/Tests/Assembly/AssemblyTests.cs) son un buen punto inicial.</span><span class="sxs-lookup"><span data-stu-id="691fc-319">The [Assembly tests](https://github.com/dotnet/corefx/blob/master/src/System.Reflection.MetadataLoadContext/tests/src/Tests/Assembly/AssemblyTests.cs) are a good place to start.</span></span>

## <a name="tls-13--openssl-111-on-linux"></a><span data-ttu-id="691fc-320">TLS 1.3 y OpenSSL 1.1.1 en Linux</span><span class="sxs-lookup"><span data-stu-id="691fc-320">TLS 1.3 & OpenSSL 1.1.1 on Linux</span></span>

<span data-ttu-id="691fc-321">.NET Core ahora usará la [compatibilidad con TLS 1.3 en OpenSSL 1.1.1](https://www.openssl.org/blog/blog/2018/09/11/release111/) cuando esté disponible en un entorno determinado.</span><span class="sxs-lookup"><span data-stu-id="691fc-321">.NET Core will now take advantage of [TLS 1.3 support in OpenSSL 1.1.1](https://www.openssl.org/blog/blog/2018/09/11/release111/), when it is available in a given environment.</span></span> <span data-ttu-id="691fc-322">TLS 1.3 aporta varias ventajas, según el [equipo de OpenSSL](https://www.openssl.org/blog/blog/2018/09/11/release111/):</span><span class="sxs-lookup"><span data-stu-id="691fc-322">There are multiple benefits of TLS 1.3, per the [OpenSSL team](https://www.openssl.org/blog/blog/2018/09/11/release111/):</span></span>

* <span data-ttu-id="691fc-323">Mejora de los tiempos de conexión gracias a una reducción del número de recorridos de ida y vuelta necesario entre el cliente y servidor.</span><span class="sxs-lookup"><span data-stu-id="691fc-323">Improved connection times due to a reduction in the number of round trips required between the client and server.</span></span>

* <span data-ttu-id="691fc-324">Mejora de la seguridad gracias a la eliminación de varios algoritmos criptográficos obsoletos y no seguros y al mayor cifrado del protocolo de enlace de la conexión.</span><span class="sxs-lookup"><span data-stu-id="691fc-324">Improved security due to the removal of various obsolete and insecure cryptographic algorithms and encryption of more of the connection handshake.</span></span>

<span data-ttu-id="691fc-325">La versión preliminar 1 de .NET Core 3.0 puede usar **OpenSSL 1.1.1**, **OpenSSL 1.1.0** o **OpenSSL 1.0.2** (la mejor versión que se encuentre en un sistema Linux).</span><span class="sxs-lookup"><span data-stu-id="691fc-325">.NET Core 3.0 Preview 1 is capable of utilizing **OpenSSL 1.1.1**, **OpenSSL 1.1.0**, or **OpenSSL 1.0.2** (whatever the best version found is, on a Linux system).</span></span>  <span data-ttu-id="691fc-326">Cuando **OpenSSL 1.1.1** está disponible, los tipos SslStream y HttpClient usarán **TLS 1.3** al usar `SslProtocols.None` (protocolos predeterminados del sistema), dando por sentado que el cliente y el servidor admiten **TLS 1.3**.</span><span class="sxs-lookup"><span data-stu-id="691fc-326">When **OpenSSL 1.1.1** is available the SslStream and HttpClient types will use **TLS 1.3** when using `SslProtocols.None` (system default protocols), assuming both the client and server support **TLS 1.3**.</span></span>

<span data-ttu-id="691fc-327">En el siguiente ejemplo se muestra la versión preliminar 1 de .NET Core 3.0 en Ubuntu 18.10 con conexión a <https://www.cloudflare.com>:</span><span class="sxs-lookup"><span data-stu-id="691fc-327">The following sample demonstrates .NET Core 3.0 Preview 1 on Ubuntu 18.10 connecting to <https://www.cloudflare.com>:</span></span>

```csharp
using System;
using System.Net.Security;
using System.Net.Sockets;
using System.Threading.Tasks;

namespace tlstest
{
    class Program
    {
        static async Task Main()
        {
            using (TcpClient tcpClient = new TcpClient())
            {
                string targetHost = "www.cloudflare.com";

                await tcpClient.ConnectAsync(targetHost, 443);

                using (SslStream sslStream = new SslStream(tcpClient.GetStream()))
                {
                    await sslStream.AuthenticateAsClientAsync(targetHost);
                    await Console.Out.WriteLineAsync($"Connected to {targetHost} with {sslStream.SslProtocol}");
                }
            }
        }
    }
}
```

```console
user@comp-ubuntu1810:~/tlstest$ dotnet run
Connected to www.cloudflare.com with Tls13
user@comp-ubuntu1810:~/tlstest$ openssl version
OpenSSL 1.1.1  11 Sep 2018
```

>[!IMPORTANT]
><span data-ttu-id="691fc-328">Windows y macOS aún no admiten **TLS 1.3**.</span><span class="sxs-lookup"><span data-stu-id="691fc-328">Windows and macOS do not yet support **TLS 1.3**.</span></span> <span data-ttu-id="691fc-329">.NET Core 3.0 será compatible con **TLS 1.3** en estos sistemas operativos cuando haya disponible soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="691fc-329">.NET Core 3.0 will support **TLS 1.3** on these operating systems when support becomes available.</span></span>

## <a name="cryptography"></a><span data-ttu-id="691fc-330">Criptografía</span><span class="sxs-lookup"><span data-stu-id="691fc-330">Cryptography</span></span>

<span data-ttu-id="691fc-331">Se ha agregado compatibilidad con los cifrados **AES-GCM** y **AES-CCM**, que se implementan a través de `System.Security.Cryptography.AesGcm` y `System.Security.Cryptography.AesCcm`.</span><span class="sxs-lookup"><span data-stu-id="691fc-331">Support has been added for **AES-GCM** and **AES-CCM** ciphers, implemented via `System.Security.Cryptography.AesGcm` and `System.Security.Cryptography.AesCcm`.</span></span> <span data-ttu-id="691fc-332">Estos algoritmos son el [cifrado autenticado con algoritmos de datos de asociación (AEAD)](https://en.wikipedia.org/wiki/Authenticated_encryption) y los primeros algoritmos de cifrado autenticado (AE) agregados a .NET Core.</span><span class="sxs-lookup"><span data-stu-id="691fc-332">These algorithms are both [Authenticated Encryption with Association Data (AEAD) algorithms](https://en.wikipedia.org/wiki/Authenticated_encryption), and the first Authenticated Encryption (AE) algorithms added to .NET Core.</span></span>

<span data-ttu-id="691fc-333">En el código siguiente se muestra cómo utilizar el cifrado **AesGcm** para cifrar y descifrar datos aleatorios.</span><span class="sxs-lookup"><span data-stu-id="691fc-333">The following code demonstrates using **AesGcm** cipher to encrypt and decrypt random data.</span></span>

<span data-ttu-id="691fc-334">El código de **AesCcm** sería casi idéntico (solo los nombres de variables de clase serían diferentes).</span><span class="sxs-lookup"><span data-stu-id="691fc-334">The code for **AesCcm** would look almost identical (only the class variable names would be different).</span></span>

```csharp
// key should be: pre-known, derived, or transported via another channel, such as RSA encryption
byte[] key = new byte[16];
RandomNumberGenerator.Fill(key);

byte[] nonce = new byte[12];
RandomNumberGenerator.Fill(nonce);

// normally this would be your data
byte[] dataToEncrypt = new byte[1234];
byte[] associatedData = new byte[333];
RandomNumberGenerator.Fill(dataToEncrypt);
RandomNumberGenerator.Fill(associatedData);

// these will be filled during the encryption
byte[] tag = new byte[16];
byte[] ciphertext = new byte[dataToEncrypt.Length];

using (AesGcm aesGcm = new AesGcm(key))
{
    aesGcm.Encrypt(nonce, dataToEncrypt, ciphertext, tag, associatedData);
}

// tag, nonce, ciphertext, associatedData should be sent to the other part

byte[] decryptedData = new byte[ciphertext.Length];

using (AesGcm aesGcm = new AesGcm(key))
{
    aesGcm.Decrypt(nonce, ciphertext, tag, decryptedData, associatedData);
}

// do something with the data
// this should always print that data is the same
Console.WriteLine($"AES-GCM: Decrypted data is{(dataToEncrypt.SequenceEqual(decryptedData) ? "the same as" : "different than")} original data.");
```

## <a name="cryptographic-key-importexport"></a><span data-ttu-id="691fc-335">Importación y exportación de claves criptográfica</span><span class="sxs-lookup"><span data-stu-id="691fc-335">Cryptographic Key Import/Export</span></span>

<span data-ttu-id="691fc-336">La versión preliminar 1 de .NET Core 3.0 admite la importación y exportación de claves asimétricas públicas y privadas de los formatos estándar, sin necesidad de usar un certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="691fc-336">.NET Core 3.0 Preview 1 supports the import and export of asymmetric public and private keys from standard formats, without needing to use an X.509 certificate.</span></span>

<span data-ttu-id="691fc-337">Todos los tipos de clave (RSA, DSA, ECDsa y ECDiffieHellman) son compatibles con el formato **X.509 SubjectPublicKeyInfo** de las claves públicas, y con los formatos **PKCS #8 PrivateKeyInfo** y **EncryptedPrivateKeyInfo de PKCS #8**  de las claves privadas.</span><span class="sxs-lookup"><span data-stu-id="691fc-337">All key types (RSA, DSA, ECDsa, ECDiffieHellman) support the **X.509 SubjectPublicKeyInfo** format for public keys, and the **PKCS#8 PrivateKeyInfo** and **PKCS#8 EncryptedPrivateKeyInfo** formats for private keys.</span></span> <span data-ttu-id="691fc-338">Además, RSA admite **PKCS #1 RSAPublicKey** y **PKCS #1 RSAPrivateKey**.</span><span class="sxs-lookup"><span data-stu-id="691fc-338">RSA additionally supports **PKCS#1 RSAPublicKey** and **PKCS#1 RSAPrivateKey**.</span></span> <span data-ttu-id="691fc-339">Todos los métodos de exportación e importación generan datos binarios con codificación DER.</span><span class="sxs-lookup"><span data-stu-id="691fc-339">The export methods all produce DER-encoded binary data, and the import methods expect the same.</span></span> <span data-ttu-id="691fc-340">Si una clave se almacena en el formato PEM de texto descriptivo, el llamador debe descodificar en base64 el contenido antes de llamar a un método de importación.</span><span class="sxs-lookup"><span data-stu-id="691fc-340">If a key is stored in the text-friendly PEM format, the caller will need to base64-decode the content before calling an import method.</span></span>

```csharp
using System;
using System.IO;
using System.Security.Cryptography;

namespace rsakeyprint
{
    class Program
    {
        static void Main(string[] args)
        {
            using (RSA rsa = RSA.Create())
            {
                byte[] keyBytes = File.ReadAllBytes(args[0]);
                rsa.ImportRSAPrivateKey(keyBytes, out int bytesRead);

                Console.WriteLine($"Read {bytesRead} bytes, {keyBytes.Length-bytesRead} extra byte(s) in file.");
                RSAParameters rsaParameters = rsa.ExportParameters(true);
                Console.WriteLine(BitConverter.ToString(rsaParameters.D));
            }
        }
    }
}
```

```console
user@comp-ubuntu1810:~/rsakeyprint$ echo Making a small key to save on screen space.
Making a small key to save on screen space.
user@comp-ubuntu1810:~/rsakeyprint$ openssl genrsa 768 | openssl rsa -outform der -out rsa.key
Generating RSA private key, 768 bit long modulus (2 primes)
..+++++++
........+++++++
e is 65537 (0x010001)
writing RSA key
user@comp-ubuntu1810:~/rsakeyprint$ dotnet run rsa.key
Read 461 bytes, 0 extra byte(s) in file.
0F-D0-82-34-F8-13-38-4A-7F-C7-52-4A-F6-93-F8-FB-6D-98-7A-6A-04-3B-BC-35-8C-7D-AC-A5-A3-6E-AD-C1-66-30-81-2C-2A-DE-DA-60-03-6A-2C-D9-76-15-7F-61-97-57-
79-E1-6E-45-62-C3-83-04-97-CB-32-EF-C5-17-5F-99-60-92-AE-B6-34-6F-30-06-03-AC-BF-15-24-43-84-EB-83-60-EF-4D-3B-BD-D9-5D-56-26-F0-51-CE-F1
user@comp-ubuntu1810:~/rsakeyprint$ openssl rsa -in rsa.key -inform der -text -noout | grep -A7 private
privateExponent:
    0f:d0:82:34:f8:13:38:4a:7f:c7:52:4a:f6:93:f8:
    fb:6d:98:7a:6a:04:3b:bc:35:8c:7d:ac:a5:a3:6e:
    ad:c1:66:30:81:2c:2a:de:da:60:03:6a:2c:d9:76:
    15:7f:61:97:57:79:e1:6e:45:62:c3:83:04:97:cb:
    32:ef:c5:17:5f:99:60:92:ae:b6:34:6f:30:06:03:
    ac:bf:15:24:43:84:eb:83:60:ef:4d:3b:bd:d9:5d:
    56:26:f0:51:ce:f1
```

<span data-ttu-id="691fc-341">Los archivos PKCS#8 pueden inspeccionarse con la clase `System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo`.</span><span class="sxs-lookup"><span data-stu-id="691fc-341">PKCS#8 files can be inspected with the `System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo` class.</span></span>

<span data-ttu-id="691fc-342">Los archivos PFX/PKCS#12 se pueden inspeccionar y manipular con `System.Security.Cryptography.Pkcs.Pkcs12Info` y `System.Security.Cryptography.Pkcs.Pkcs12Builder`, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="691fc-342">PFX/PKCS#12 files can be inspected and manipulated with `System.Security.Cryptography.Pkcs.Pkcs12Info` and `System.Security.Cryptography.Pkcs.Pkcs12Builder`, respectively.</span></span>

## <a name="serialport-for-linux"></a><span data-ttu-id="691fc-343">SerialPort para Linux</span><span class="sxs-lookup"><span data-stu-id="691fc-343">SerialPort for Linux</span></span>

<span data-ttu-id="691fc-344">.NET Core 3.0 ahora admite <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType> en Linux.</span><span class="sxs-lookup"><span data-stu-id="691fc-344">.NET Core 3.0 now supports <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType> on Linux.</span></span>

<span data-ttu-id="691fc-345">Anteriormente, .NET Core solo admite el uso del tipo `SerialPort` en Windows.</span><span class="sxs-lookup"><span data-stu-id="691fc-345">Previously, .NET Core only supported using the `SerialPort` type on Windows.</span></span>

## <a name="more-bcl-improvements"></a><span data-ttu-id="691fc-346">Más mejoras de BCL</span><span class="sxs-lookup"><span data-stu-id="691fc-346">More BCL Improvements</span></span>

<span data-ttu-id="691fc-347">`Span<T>`, `Memory<T>` y los tipos relacionados que se introdujeron en .NET Core 2.1 se han optimizado en .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="691fc-347">The `Span<T>`, `Memory<T>`, and related types that were introduced in .NET Core 2.1, have been optimized in .NET Core 3.0.</span></span> <span data-ttu-id="691fc-348">Operaciones comunes, como la construcción de intervalos, la segmentación, el análisis y la aplicación de formato funcionan mejor ahora.</span><span class="sxs-lookup"><span data-stu-id="691fc-348">Common operations such as span construction, slicing, parsing, and formatting now perform better.</span></span>

<span data-ttu-id="691fc-349">Además, los tipos como `String` se han mejorado para que sean más eficaces cuando se utilizan como claves con `Dictionary<TKey, TValue>` y otras colecciones.</span><span class="sxs-lookup"><span data-stu-id="691fc-349">Additionally, types like `String` have seen under-the-cover improvements to make them more efficient when used as keys with `Dictionary<TKey, TValue>` and other collections.</span></span> <span data-ttu-id="691fc-350">No se requiere ningún cambio de código para aprovechar estas mejoras.</span><span class="sxs-lookup"><span data-stu-id="691fc-350">No code changes are required to benefit from these improvements.</span></span>

<span data-ttu-id="691fc-351">Las mejoras siguientes también son nuevas en la versión preliminar 1 de .NET Core 3:</span><span class="sxs-lookup"><span data-stu-id="691fc-351">The following improvements are also new in .NET Core 3 Preview 1:</span></span>

* <span data-ttu-id="691fc-352">Compatibilidad con Brotli integrada en HttpClient</span><span class="sxs-lookup"><span data-stu-id="691fc-352">Brotli support built in to HttpClient</span></span>
* <span data-ttu-id="691fc-353">ThreadPool.UnsafeQueueWorkItem(IThreadPoolWorkItem)</span><span class="sxs-lookup"><span data-stu-id="691fc-353">ThreadPool.UnsafeQueueWorkItem(IThreadPoolWorkItem)</span></span>
* <span data-ttu-id="691fc-354">Unsafe.Unbox</span><span class="sxs-lookup"><span data-stu-id="691fc-354">Unsafe.Unbox</span></span>
* <span data-ttu-id="691fc-355">CancellationToken.Unregister</span><span class="sxs-lookup"><span data-stu-id="691fc-355">CancellationToken.Unregister</span></span>
* <span data-ttu-id="691fc-356">Operadores aritméticos complejos</span><span class="sxs-lookup"><span data-stu-id="691fc-356">Complex arithmetic operators</span></span>
* <span data-ttu-id="691fc-357">API de socket para TCP persistente</span><span class="sxs-lookup"><span data-stu-id="691fc-357">Socket APIs for TCP keep alive</span></span>
* <span data-ttu-id="691fc-358">StringBuilder.GetChunks</span><span class="sxs-lookup"><span data-stu-id="691fc-358">StringBuilder.GetChunks</span></span>
* <span data-ttu-id="691fc-359">Análisis de IPEndPoint</span><span class="sxs-lookup"><span data-stu-id="691fc-359">IPEndPoint parsing</span></span>
* <span data-ttu-id="691fc-360">RandomNumberGenerator.GetInt32</span><span class="sxs-lookup"><span data-stu-id="691fc-360">RandomNumberGenerator.GetInt32</span></span>

## <a name="tiered-compilation"></a><span data-ttu-id="691fc-361">Compilación en niveles</span><span class="sxs-lookup"><span data-stu-id="691fc-361">Tiered compilation</span></span>

<span data-ttu-id="691fc-362">La [compilación en niveles](https://devblogs.microsoft.com/dotnet/tiered-compilation-preview-in-net-core-2-1/) está activada de forma predeterminada con .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="691fc-362">[Tiered compilation](https://devblogs.microsoft.com/dotnet/tiered-compilation-preview-in-net-core-2-1/) is on by default with .NET Core 3.0.</span></span> <span data-ttu-id="691fc-363">Se trata de una característica que permite que el entorno de ejecución use de forma más adaptable el compilador Just-In-Time (JIT) para obtener un mejor rendimiento, tanto en el inicio como al maximizar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="691fc-363">It is a feature that enables the runtime to more adaptively use the Just-In-Time (JIT) compiler to get better performance, both at startup and to maximize throughput.</span></span>

<span data-ttu-id="691fc-364">Se agregó como una característica opcional en [.NET Core 2.1](https://devblogs.microsoft.com/dotnet/announcing-net-core-2-1/) y, más tarde, se habilitó de forma predeterminada en la [versión preliminar 2 de .NET Core 2.2](https://devblogs.microsoft.com/dotnet/announcing-net-core-2-2-preview-2/).</span><span class="sxs-lookup"><span data-stu-id="691fc-364">This feature was added as an opt-in feature in [.NET Core 2.1](https://devblogs.microsoft.com/dotnet/announcing-net-core-2-1/) and then was enabled by default in [.NET Core 2.2 Preview 2](https://devblogs.microsoft.com/dotnet/announcing-net-core-2-2-preview-2/).</span></span> <span data-ttu-id="691fc-365">Posteriormente, se revirtió a opcional con .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="691fc-365">Subsequently, it has been reverted back to opt in with the .NET Core 2.2 release.</span></span>

## <a name="arm64-linux-support"></a><span data-ttu-id="691fc-366">Compatibilidad con ARM64 para Linux</span><span class="sxs-lookup"><span data-stu-id="691fc-366">ARM64 Linux support</span></span>

<span data-ttu-id="691fc-367">Se ha agregado compatibilidad con ARM64 para Linux.</span><span class="sxs-lookup"><span data-stu-id="691fc-367">Support has been added for ARM64 for Linux.</span></span> <span data-ttu-id="691fc-368">El principal caso de uso de ARM64 son escenarios de IoT.</span><span class="sxs-lookup"><span data-stu-id="691fc-368">The primary use case for ARM64 is currently with IoT scenarios.</span></span>

<span data-ttu-id="691fc-369">Las [imágenes de Docker de Alpine, Debian y Ubuntu están disponibles en .NET Core para ARM64](https://hub.docker.com/r/microsoft/dotnet/).</span><span class="sxs-lookup"><span data-stu-id="691fc-369">Alpine, Debian and Ubuntu [Docker images are available for .NET Core for ARM64](https://hub.docker.com/r/microsoft/dotnet/).</span></span>

<span data-ttu-id="691fc-370">Consulte la página sobre el [estado de ARM64 para .NET Core](https://github.com/dotnet/announcements/issues/82) si desea obtener más información.</span><span class="sxs-lookup"><span data-stu-id="691fc-370">Please check [.NET Core ARM64 Status](https://github.com/dotnet/announcements/issues/82) for more information.</span></span>

>[!NOTE]
> <span data-ttu-id="691fc-371">Windows aún no ofrece soporte técnico para **ARM64**.</span><span class="sxs-lookup"><span data-stu-id="691fc-371">**ARM64** Windows support isn't yet available.</span></span>

## <a name="install-net-core-30-previews-on-linux-with-snap"></a><span data-ttu-id="691fc-372">Instalar versiones preliminares de .NET Core 3.0 en Linux con Snap</span><span class="sxs-lookup"><span data-stu-id="691fc-372">Install .NET Core 3.0 Previews on Linux with Snap</span></span>

<span data-ttu-id="691fc-373">Snap es la forma preferida de instalar y probar versiones preliminares de .NET Core en [distribuciones de Linux que admiten Snap](https://docs.snapcraft.io/installing-snapd/6735).</span><span class="sxs-lookup"><span data-stu-id="691fc-373">Snap is the preferred way to install and try .NET Core previews on [Linux distributions that support Snap](https://docs.snapcraft.io/installing-snapd/6735).</span></span>

<span data-ttu-id="691fc-374">Después de configurar Snap en su sistema, ejecute el comando siguiente para instalar el [SDK de versión preliminar de .NET Core 3.0](https://snapcraft.io/dotnet-sdk).</span><span class="sxs-lookup"><span data-stu-id="691fc-374">After configuring Snap on your system, run the following command to install the [.NET Core SDK 3.0 Preview SDK](https://snapcraft.io/dotnet-sdk).</span></span>

```console
sudo snap install dotnet-sdk --beta --classic
```

<span data-ttu-id="691fc-375">Cuando se instale .NET Core con el paquete Snap, el comando de .NET Core predeterminado será `dotnet-sdk.dotnet`, en lugar de solo `dotnet`.</span><span class="sxs-lookup"><span data-stu-id="691fc-375">When .NET Core in installed using the Snap package, the default .NET Core command is `dotnet-sdk.dotnet`, as opposed to just `dotnet`.</span></span> <span data-ttu-id="691fc-376">La ventaja del comando con espacio de nombres es que no entrará en conflicto con una versión de .NET Core instalada globalmente que pueda tener.</span><span class="sxs-lookup"><span data-stu-id="691fc-376">The benefit of the namespaced command is that it will not conflict with a globally installed .NET Core version you may have.</span></span> <span data-ttu-id="691fc-377">A este comando se le puede llamar `dotnet` con:</span><span class="sxs-lookup"><span data-stu-id="691fc-377">This command can be aliased to `dotnet` with:</span></span>

```console
sudo snap alias dotnet-sdk.dotnet dotnet
```

<span data-ttu-id="691fc-378">Algunas distribuciones requieren un paso adicional para habilitar acceso al certificado SSL.</span><span class="sxs-lookup"><span data-stu-id="691fc-378">Some distros require an additional step to enable access to the SSL certificate.</span></span> <span data-ttu-id="691fc-379">Consulte nuestra [Instalación de Linux](https://github.com/dotnet/core/blob/master/Documentation/linux-setup.md) para obtener detalles.</span><span class="sxs-lookup"><span data-stu-id="691fc-379">See our [Linux Setup](https://github.com/dotnet/core/blob/master/Documentation/linux-setup.md) for details.</span></span>

## <a name="gpio-support-for-raspberry-pi"></a><span data-ttu-id="691fc-380">Compatibilidad de GPIO con Raspberry Pi</span><span class="sxs-lookup"><span data-stu-id="691fc-380">GPIO Support for Raspberry Pi</span></span>

<span data-ttu-id="691fc-381">Se han publicado en NuGet dos nuevos paquetes que puede usar para la programación GPIO.</span><span class="sxs-lookup"><span data-stu-id="691fc-381">Two new packages have been released to NuGet that you can use for GPIO programming.</span></span>

* [<span data-ttu-id="691fc-382">System.Device.Gpio</span><span class="sxs-lookup"><span data-stu-id="691fc-382">System.Device.Gpio</span></span>](https://www.nuget.org/packages/System.Device.Gpio/0.1.0-prerelease.19078.2)
* [<span data-ttu-id="691fc-383">Iot.Device.Bindings</span><span class="sxs-lookup"><span data-stu-id="691fc-383">Iot.Device.Bindings</span></span>](https://www.nuget.org/packages/Iot.Device.Bindings/0.1.0-prerelease.19078.2)

<span data-ttu-id="691fc-384">Los paquetes GPIO incluyen API para dispositivos GPIO, SPI, I2C y PWM.</span><span class="sxs-lookup"><span data-stu-id="691fc-384">The GPIO Packages includes APIs for GPIO, SPI, I2C and PWM devices.</span></span> <span data-ttu-id="691fc-385">El paquete de enlaces de IoT incluye [enlaces de dispositivo](https://github.com/dotnet/iot/blob/master/src/devices/README.md) para diversos chips y sensores, los mismos disponibles en [dotnet/iot - src/devices](https://github.com/dotnet/iot/tree/master/src/devices).</span><span class="sxs-lookup"><span data-stu-id="691fc-385">The IoT bindings package includes [device bindings](https://github.com/dotnet/iot/blob/master/src/devices/README.md) for various chips and sensors, the same ones available at [dotnet/iot - src/devices](https://github.com/dotnet/iot/tree/master/src/devices).</span></span>

<span data-ttu-id="691fc-386">Las API de puerto serie actualizadas que se anunciaron como parte de .NET Core 3.0 (versión preliminar 1) no forman parte de estos paquetes, pero están disponibles como parte de la plataforma .NET Core.</span><span class="sxs-lookup"><span data-stu-id="691fc-386">The updated serial port APIs that were announced as part of .NET Core 3.0 Preview 1 are not part of these packages but are available as part of the .NET Core platform.</span></span>

## <a name="platform-support"></a><span data-ttu-id="691fc-387">Compatibilidad de la plataforma</span><span class="sxs-lookup"><span data-stu-id="691fc-387">Platform Support</span></span>

<span data-ttu-id="691fc-388">Los siguientes sistemas operativos admitirán .NET Core 3:</span><span class="sxs-lookup"><span data-stu-id="691fc-388">.NET Core 3 will be supported on the following operating systems:</span></span>

* <span data-ttu-id="691fc-389">Cliente de Windows: 7, 8.1, 10 (1607+)</span><span class="sxs-lookup"><span data-stu-id="691fc-389">Windows Client: 7, 8.1, 10 (1607+)</span></span>
* <span data-ttu-id="691fc-390">Windows Server: 2012 R2 SP1+</span><span class="sxs-lookup"><span data-stu-id="691fc-390">Windows Server: 2012 R2 SP1+</span></span>
* <span data-ttu-id="691fc-391">macOS: 10.12+</span><span class="sxs-lookup"><span data-stu-id="691fc-391">macOS: 10.12+</span></span>
* <span data-ttu-id="691fc-392">RHEL: 6+</span><span class="sxs-lookup"><span data-stu-id="691fc-392">RHEL: 6+</span></span>
* <span data-ttu-id="691fc-393">Fedora: 26+</span><span class="sxs-lookup"><span data-stu-id="691fc-393">Fedora: 26+</span></span>
* <span data-ttu-id="691fc-394">Ubuntu: 16.04+</span><span class="sxs-lookup"><span data-stu-id="691fc-394">Ubuntu: 16.04+</span></span>
* <span data-ttu-id="691fc-395">Debian: 9+</span><span class="sxs-lookup"><span data-stu-id="691fc-395">Debian: 9+</span></span>
* <span data-ttu-id="691fc-396">SLES: 12+</span><span class="sxs-lookup"><span data-stu-id="691fc-396">SLES: 12+</span></span>
* <span data-ttu-id="691fc-397">openSUSE: 42.3+</span><span class="sxs-lookup"><span data-stu-id="691fc-397">openSUSE: 42.3+</span></span>
* <span data-ttu-id="691fc-398">Alpine: 3.8+</span><span class="sxs-lookup"><span data-stu-id="691fc-398">Alpine: 3.8+</span></span>

<span data-ttu-id="691fc-399">La compatibilidad con el chip sigue:</span><span class="sxs-lookup"><span data-stu-id="691fc-399">Chip support follows:</span></span>

* <span data-ttu-id="691fc-400">x64 en Windows, macOS y Linux</span><span class="sxs-lookup"><span data-stu-id="691fc-400">x64 on Windows, macOS, and Linux</span></span>
* <span data-ttu-id="691fc-401">x86 en Windows</span><span class="sxs-lookup"><span data-stu-id="691fc-401">x86 on Windows</span></span>
* <span data-ttu-id="691fc-402">ARM32 en Windows y Linux</span><span class="sxs-lookup"><span data-stu-id="691fc-402">ARM32 on Windows and Linux</span></span>
* <span data-ttu-id="691fc-403">ARM64 en Linux</span><span class="sxs-lookup"><span data-stu-id="691fc-403">ARM64 on Linux</span></span>

<span data-ttu-id="691fc-404">En Linux, ARM32 se admite en Debian 9+ y Ubuntu 16.04+.</span><span class="sxs-lookup"><span data-stu-id="691fc-404">For Linux, ARM32 is supported on Debian 9+ and Ubuntu 16.04+.</span></span> <span data-ttu-id="691fc-405">En ARM64, es igual que ARM32 con la adición de Alpine 3.8.</span><span class="sxs-lookup"><span data-stu-id="691fc-405">For ARM64, it is the same as ARM32 with the addition of Alpine 3.8.</span></span> <span data-ttu-id="691fc-406">Estas son las mismas versiones de esas distribuciones tal cual compatibles con X64.</span><span class="sxs-lookup"><span data-stu-id="691fc-406">These are the same versions of those distros as is supported for X64.</span></span>

<span data-ttu-id="691fc-407">Las imágenes de Docker para .NET Core 3.0 están disponibles en [microsoft/dotnet en Docker Hub](https://hub.docker.com/r/microsoft/dotnet/).</span><span class="sxs-lookup"><span data-stu-id="691fc-407">Docker images for .NET Core 3.0 are available at [microsoft/dotnet on Docker Hub](https://hub.docker.com/r/microsoft/dotnet/).</span></span> <span data-ttu-id="691fc-408">Microsoft se encuentra actualmente en proceso de adopción de [Registro de contenedor de Microsoft (MCR)](https://cloudblogs.microsoft.com/opensource/2019/01/17/improved-discovery-experience-microsoft-containers-docker-hub/) y se espera que las imágenes de .NET Core 3.0 finales se publiquen solo en MCR.</span><span class="sxs-lookup"><span data-stu-id="691fc-408">Microsoft is currently in the process of adopting [Microsoft Container Registry (MCR)](https://cloudblogs.microsoft.com/opensource/2019/01/17/improved-discovery-experience-microsoft-containers-docker-hub/) and it is expected that the final .NET Core 3.0 images will only be published to MCR.</span></span>
