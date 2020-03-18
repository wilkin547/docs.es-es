---
title: Novedades de C# 7.1
description: Información general sobre las nuevas características en C# 7.1.
ms.date: 04/09/2019
ms.openlocfilehash: 5d2d6f51b6422f5b4db5c6bd275b5ffce1f695f8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79398356"
---
# <a name="whats-new-in-c-71"></a><span data-ttu-id="d9bdf-103">Novedades de C# 7.1</span><span class="sxs-lookup"><span data-stu-id="d9bdf-103">What's new in C# 7.1</span></span>

<span data-ttu-id="d9bdf-104">C# 7.1 es la primera versión secundaria del lenguaje C#.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-104">C# 7.1 is the first point release to the C# language.</span></span> <span data-ttu-id="d9bdf-105">Marca una cadencia de versión mayor en el lenguaje.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-105">It marks an increased release cadence for the language.</span></span> <span data-ttu-id="d9bdf-106">Podrá usar las nuevas características más pronto, lo ideal es que cuando vayan estando listas.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-106">You can use the new features sooner, ideally when each new feature is ready.</span></span> <span data-ttu-id="d9bdf-107">C# 7.1 incluye la posibilidad de configurar el compilador para que coincida con una versión especificada del lenguaje.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-107">C# 7.1 adds the ability to configure the compiler to match a specified version of the language.</span></span> <span data-ttu-id="d9bdf-108">Ello permite aislar la decisión de actualizar las herramientas de la decisión de actualizar las versiones de lenguaje.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-108">That enables you to separate the decision to upgrade tools from the decision to upgrade language versions.</span></span>

<span data-ttu-id="d9bdf-109">C# 7.1 incorpora el elemento de configuración de [selección de versión de lenguaje](../language-reference/configure-language-version.md), tres nuevas características de lenguaje y un nuevo comportamiento del compilador.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-109">C# 7.1 adds the [language version selection](../language-reference/configure-language-version.md) configuration element, three new language features, and new compiler behavior.</span></span>

<span data-ttu-id="d9bdf-110">Las nuevas características de lenguaje de esta versión son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="d9bdf-110">The new language features in this release are:</span></span>

- [<span data-ttu-id="d9bdf-111">Método `async` `Main`</span><span class="sxs-lookup"><span data-stu-id="d9bdf-111">`async` `Main` method</span></span>](#async-main)
  - <span data-ttu-id="d9bdf-112">El punto de entrada de una aplicación puede tener el modificador `async`.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-112">The entry point for an application can have the `async` modifier.</span></span>
- [<span data-ttu-id="d9bdf-113">Expresiones literales `default`</span><span class="sxs-lookup"><span data-stu-id="d9bdf-113">`default` literal expressions</span></span>](#default-literal-expressions)
  - <span data-ttu-id="d9bdf-114">Se pueden usar expresiones literales predeterminadas en expresiones de valor predeterminadas cuando el tipo de destino se pueda inferir.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-114">You can use default literal expressions in default value expressions when the target type can be inferred.</span></span>
- [<span data-ttu-id="d9bdf-115">Nombres de elementos de tupla inferidos</span><span class="sxs-lookup"><span data-stu-id="d9bdf-115">Inferred tuple element names</span></span>](#inferred-tuple-element-names)
  - <span data-ttu-id="d9bdf-116">En muchos casos, los nombres de elementos de tupla se pueden deducir de la inicialización de la tupla.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-116">The names of tuple elements can be inferred from tuple initialization in many cases.</span></span>
- [<span data-ttu-id="d9bdf-117">Coincidencia de patrones en parámetros de tipo genérico</span><span class="sxs-lookup"><span data-stu-id="d9bdf-117">Pattern matching on generic type parameters</span></span>](#pattern-matching-on-generic-type-parameters)
  - <span data-ttu-id="d9bdf-118">Puede usar expresiones de coincidencia de patrones en variables cuyo tipo es un parámetro de tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-118">You can use pattern match expressions on variables whose type is a generic type parameter.</span></span>

<span data-ttu-id="d9bdf-119">Por último, el compilador tiene dos opciones, `-refout` y `-refonly`, que controlan la [generación de ensamblados de referencia](#reference-assembly-generation).</span><span class="sxs-lookup"><span data-stu-id="d9bdf-119">Finally, the compiler has two options `-refout` and `-refonly` that control [reference assembly generation](#reference-assembly-generation).</span></span>

<span data-ttu-id="d9bdf-120">Para usar las características más recientes en una versión secundaria, tendrá que [configurar la versión del idioma de compilador](../language-reference/configure-language-version.md) y seleccionar la versión.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-120">To use the latest features in a point release, you need to [configure the compiler language version](../language-reference/configure-language-version.md) and select the version.</span></span>

<span data-ttu-id="d9bdf-121">En el resto de este artículo se proporciona información general sobre cada característica.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-121">The remainder of this article provides an overview of each feature.</span></span> <span data-ttu-id="d9bdf-122">Para cada característica, conocerá el razonamiento subyacente.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-122">For each feature, you'll learn the reasoning behind it.</span></span> <span data-ttu-id="d9bdf-123">Aprenderá la sintaxis.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-123">You'll learn the syntax.</span></span> <span data-ttu-id="d9bdf-124">Puede explorar estas características en su entorno mediante la herramienta global `dotnet try`:</span><span class="sxs-lookup"><span data-stu-id="d9bdf-124">You can explore these features in your environment using the `dotnet try` global tool:</span></span>

1. <span data-ttu-id="d9bdf-125">Instale la herramienta global [dotnet-try](https://github.com/dotnet/try/blob/master/README.md#setup).</span><span class="sxs-lookup"><span data-stu-id="d9bdf-125">Install the [dotnet-try](https://github.com/dotnet/try/blob/master/README.md#setup) global tool.</span></span>
1. <span data-ttu-id="d9bdf-126">Clone el repositorio [dotnet/try-samples](https://github.com/dotnet/try-samples).</span><span class="sxs-lookup"><span data-stu-id="d9bdf-126">Clone the [dotnet/try-samples](https://github.com/dotnet/try-samples) repository.</span></span>
1. <span data-ttu-id="d9bdf-127">Establezca el directorio actual en el subdirectorio *csharp7* para el repositorio *try-samples*.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-127">Set the current directory to the *csharp7* subdirectory for the *try-samples* repository.</span></span>
1. <span data-ttu-id="d9bdf-128">Ejecute `dotnet try`.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-128">Run `dotnet try`.</span></span>

## <a name="async-main"></a><span data-ttu-id="d9bdf-129">Async main</span><span class="sxs-lookup"><span data-stu-id="d9bdf-129">Async main</span></span>

<span data-ttu-id="d9bdf-130">Un método *async main* permite usar `await` en el método `Main`.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-130">An *async main* method enables you to use `await` in your `Main` method.</span></span>
<span data-ttu-id="d9bdf-131">Anteriormente, hubiera sido necesario escribir lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d9bdf-131">Previously you would need to write:</span></span>

```csharp
static int Main()
{
    return DoAsyncWork().GetAwaiter().GetResult();
}
```

<span data-ttu-id="d9bdf-132">Ahora se puede escribir esto:</span><span class="sxs-lookup"><span data-stu-id="d9bdf-132">You can now write:</span></span>

```csharp
static async Task<int> Main()
{
    // This could also be replaced with the body
    // DoAsyncWork, including its await expressions:
    return await DoAsyncWork();
}
```

<span data-ttu-id="d9bdf-133">Si el programa no devuelve un código de salida, puede declarar un método `Main` que devuelva una <xref:System.Threading.Tasks.Task>:</span><span class="sxs-lookup"><span data-stu-id="d9bdf-133">If your program doesn't return an exit code, you can declare a `Main` method that returns a <xref:System.Threading.Tasks.Task>:</span></span>

```csharp
static async Task Main()
{
    await SomeAsyncMethod();
}
```

<span data-ttu-id="d9bdf-134">En el artículo sobre [async main](../programming-guide/main-and-command-args/index.md) de la guía de programación puede leer más detalles al respecto.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-134">You can read more about the details in the [async main](../programming-guide/main-and-command-args/index.md) article in the programming guide.</span></span>

## <a name="default-literal-expressions"></a><span data-ttu-id="d9bdf-135">Expresiones literales predeterminadas</span><span class="sxs-lookup"><span data-stu-id="d9bdf-135">Default literal expressions</span></span>

<span data-ttu-id="d9bdf-136">Las expresiones literales predeterminadas constituyen una mejora con respecto a las expresiones de valor predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-136">Default literal expressions are an enhancement to default value expressions.</span></span>
<span data-ttu-id="d9bdf-137">Estas expresiones inicializan una variable en el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-137">These expressions initialize a variable to the default value.</span></span> <span data-ttu-id="d9bdf-138">Donde anteriormente habría que escribir:</span><span class="sxs-lookup"><span data-stu-id="d9bdf-138">Where you previously would write:</span></span>

```csharp
Func<string, bool> whereClause = default(Func<string, bool>);
```

<span data-ttu-id="d9bdf-139">Ahora, se puede pasar por alto el tipo del lado derecho de la inicialización:</span><span class="sxs-lookup"><span data-stu-id="d9bdf-139">You can now omit the type on the right-hand side of the initialization:</span></span>

```csharp
Func<string, bool> whereClause = default;
```

<span data-ttu-id="d9bdf-140">Para más información, consulte la sección [Literal default](../language-reference/operators/default.md#default-literal) del artículo [Operador default](../language-reference/operators/default.md).</span><span class="sxs-lookup"><span data-stu-id="d9bdf-140">For more information, see the [default literal](../language-reference/operators/default.md#default-literal) section of the [default operator](../language-reference/operators/default.md) article.</span></span>

## <a name="inferred-tuple-element-names"></a><span data-ttu-id="d9bdf-141">Nombres de elementos de tupla inferidos</span><span class="sxs-lookup"><span data-stu-id="d9bdf-141">Inferred tuple element names</span></span>

<span data-ttu-id="d9bdf-142">Esta característica supone una pequeña mejora con respecto a la característica de tuplas incluida en C# 7.0.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-142">This feature is a small enhancement to the tuples feature introduced in C# 7.0.</span></span> <span data-ttu-id="d9bdf-143">Muchas veces, cuando se inicializa una tupla, las variables usadas en el lado derecho de la asignación son las mismas que los nombres que querríamos dar a los elementos de tupla:</span><span class="sxs-lookup"><span data-stu-id="d9bdf-143">Many times when you initialize a tuple, the variables used for the right side of the assignment are the same as the names you'd like for the tuple elements:</span></span>

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count: count, label: label);
```

<span data-ttu-id="d9bdf-144">Ahora, los nombres de los elementos de tupla se pueden deducir de las variables empleadas para inicializar la tupla en C# 7.1:</span><span class="sxs-lookup"><span data-stu-id="d9bdf-144">The names of tuple elements can be inferred from the variables used to initialize the tuple in C# 7.1:</span></span>

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count, label); // element names are "count" and "label"
```

<span data-ttu-id="d9bdf-145">Encontrará más información sobre esta característica en el artículo sobre [tuplas](../tuples.md).</span><span class="sxs-lookup"><span data-stu-id="d9bdf-145">You can learn more about this feature in the [Tuples](../tuples.md) article.</span></span>

## <a name="pattern-matching-on-generic-type-parameters"></a><span data-ttu-id="d9bdf-146">Coincidencia de patrones en parámetros de tipo genérico</span><span class="sxs-lookup"><span data-stu-id="d9bdf-146">Pattern matching on generic type parameters</span></span>

<span data-ttu-id="d9bdf-147">A partir de C# 7.1, la expresión de patrón para `is` y el patrón de tipo `switch` pueden tener el tipo de un parámetro de tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-147">Beginning with C# 7.1, the pattern expression for `is` and the `switch` type pattern may have the type of a generic type parameter.</span></span> <span data-ttu-id="d9bdf-148">Esto puede ser especialmente útil al comprobar los tipos que pueden ser tipos `struct` o `class` y si quiere evitar la conversión boxing.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-148">This can be most useful when checking types that may be either `struct` or `class` types, and you want to avoid boxing.</span></span>

## <a name="reference-assembly-generation"></a><span data-ttu-id="d9bdf-149">Generación de ensamblados de referencia</span><span class="sxs-lookup"><span data-stu-id="d9bdf-149">Reference assembly generation</span></span>

<span data-ttu-id="d9bdf-150">Existen dos nuevas opciones del compilador con las que se generan *ensamblados solo de referencia*: [-refout](../language-reference/compiler-options/refout-compiler-option.md) y [-refonly](../language-reference/compiler-options/refonly-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="d9bdf-150">There are two new compiler options that generate *reference-only assemblies*: [-refout](../language-reference/compiler-options/refout-compiler-option.md) and [-refonly](../language-reference/compiler-options/refonly-compiler-option.md).</span></span>
<span data-ttu-id="d9bdf-151">En los artículos de los vínculos se explican estas opciones y los ensamblados de referencia de manera más pormenorizada.</span><span class="sxs-lookup"><span data-stu-id="d9bdf-151">The linked articles explain these options and reference assemblies in more detail.</span></span>
