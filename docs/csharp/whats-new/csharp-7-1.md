---
title: Novedades de C# 7.1
description: Información general sobre las nuevas características en C# 7.1.
ms.date: 08/16/2017
ms.openlocfilehash: 565db102284424f9d8f6fa04ec9c74b52c9da0e6
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2018
ms.locfileid: "34728659"
---
# <a name="whats-new-in-c-71"></a><span data-ttu-id="da270-103">Novedades de C# 7.1</span><span class="sxs-lookup"><span data-stu-id="da270-103">What's new in C# 7.1</span></span>

<span data-ttu-id="da270-104">C# 7.1 es la primera versión secundaria del lenguaje C#.</span><span class="sxs-lookup"><span data-stu-id="da270-104">C# 7.1 is the first point release to the C# language.</span></span> <span data-ttu-id="da270-105">Marca una cadencia de versión mayor en el lenguaje.</span><span class="sxs-lookup"><span data-stu-id="da270-105">It marks an increased release cadence for the language.</span></span> <span data-ttu-id="da270-106">Podrá usar las nuevas características más pronto, lo ideal es que cuando vayan estando listas.</span><span class="sxs-lookup"><span data-stu-id="da270-106">You can use the new features sooner, ideally when each new feature is ready.</span></span> <span data-ttu-id="da270-107">C# 7.1 incluye la posibilidad de configurar el compilador para que coincida con una versión especificada del lenguaje.</span><span class="sxs-lookup"><span data-stu-id="da270-107">C# 7.1 adds the ability to configure the compiler to match a specified version of the language.</span></span> <span data-ttu-id="da270-108">Ello permite aislar la decisión de actualizar las herramientas de la decisión de actualizar las versiones de lenguaje.</span><span class="sxs-lookup"><span data-stu-id="da270-108">That enables you to separate the decision to upgrade tools from the decision to upgrade language versions.</span></span>

<span data-ttu-id="da270-109">C# 7.1 incorpora el elemento de configuración de [selección de versión de lenguaje](../language-reference/configure-language-version.md), tres nuevas características de lenguaje y un nuevo comportamiento del compilador.</span><span class="sxs-lookup"><span data-stu-id="da270-109">C# 7.1 adds the [language version selection](../language-reference/configure-language-version.md) configuration element, three new language features and new compiler behavior.</span></span>

<span data-ttu-id="da270-110">Las nuevas características de lenguaje de esta versión son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="da270-110">The new language features in this release are:</span></span>

* [<span data-ttu-id="da270-111">Método `async` `Main`</span><span class="sxs-lookup"><span data-stu-id="da270-111">`async` `Main` method</span></span>](#async-main)
  - <span data-ttu-id="da270-112">El punto de entrada de una aplicación puede tener el modificador `async`.</span><span class="sxs-lookup"><span data-stu-id="da270-112">The entry point for an application can have the `async` modifier.</span></span>
* [<span data-ttu-id="da270-113">Expresiones literales `default`</span><span class="sxs-lookup"><span data-stu-id="da270-113">`default` literal expressions</span></span>](#default-literal-expressions)
  - <span data-ttu-id="da270-114">Se pueden usar expresiones literales predeterminadas en expresiones de valor predeterminadas cuando el tipo de destino se pueda inferir.</span><span class="sxs-lookup"><span data-stu-id="da270-114">You can use default literal expressions in default value expressions when the target type can be inferred.</span></span>
* [<span data-ttu-id="da270-115">Nombres de elementos de tupla inferidos</span><span class="sxs-lookup"><span data-stu-id="da270-115">Inferred tuple element names</span></span>](#inferred-tuple-element-names)
  - <span data-ttu-id="da270-116">En muchos casos, los nombres de elementos de tupla se pueden deducir de la inicialización de la tupla.</span><span class="sxs-lookup"><span data-stu-id="da270-116">The names of tuple elements can be inferred from tuple initialization in many cases.</span></span>

<span data-ttu-id="da270-117">Por último, el compilador tiene dos opciones, `/refout` y `/refonly`, que controlan la [generación de ensamblados de referencia](#reference-assembly-generation).</span><span class="sxs-lookup"><span data-stu-id="da270-117">Finally, the compiler has two options `/refout` and `/refonly` that control [reference assembly generation](#reference-assembly-generation).</span></span>

<span data-ttu-id="da270-118">Para usar las características más recientes en una versión secundaria, tendrá que [configurar la versión del idioma de compilador](../language-reference/configure-language-version.md) y seleccionar la versión.</span><span class="sxs-lookup"><span data-stu-id="da270-118">To use the latest features in a point release, you need to [configure the compiler language version](../language-reference/configure-language-version.md) and select the version.</span></span>

## <a name="async-main"></a><span data-ttu-id="da270-119">Async main</span><span class="sxs-lookup"><span data-stu-id="da270-119">Async main</span></span>

<span data-ttu-id="da270-120">Un método *async main* permite usar `await` en el método `Main`.</span><span class="sxs-lookup"><span data-stu-id="da270-120">An *async main* method enables you to use `await` in your `Main` method.</span></span>
<span data-ttu-id="da270-121">Anteriormente, hubiera sido necesario escribir lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="da270-121">Previously you would need to write:</span></span>

```csharp
static int Main()
{
    return DoAsyncWork().GetAwaiter().GetResult();
}
```

<span data-ttu-id="da270-122">Ahora se puede escribir esto:</span><span class="sxs-lookup"><span data-stu-id="da270-122">You can now write:</span></span>

```csharp
static async Task<int> Main()
{
    // This could also be replaced with the body
    // DoAsyncWork, including its await expressions:
    return await DoAsyncWork();
}
```

<span data-ttu-id="da270-123">Si el programa no devuelve un código de salida, puede declarar un método `Main` que devuelva una <xref:System.Threading.Tasks.Task>:</span><span class="sxs-lookup"><span data-stu-id="da270-123">If your program doesn't return an exit code, you can declare a `Main` method that returns a <xref:System.Threading.Tasks.Task>:</span></span>

```csharp
static async Task Main()
{
    await SomeAsyncMethod();
}
```

<span data-ttu-id="da270-124">En el tema sobre [async main](../programming-guide/main-and-command-args/index.md) de la guía de programación puede leer más detalles al respecto.</span><span class="sxs-lookup"><span data-stu-id="da270-124">You can read more about the details in the [async main](../programming-guide/main-and-command-args/index.md) topic in the programming guide.</span></span>

## <a name="default-literal-expressions"></a><span data-ttu-id="da270-125">Expresiones literales predeterminadas</span><span class="sxs-lookup"><span data-stu-id="da270-125">Default literal expressions</span></span>

<span data-ttu-id="da270-126">Las expresiones literales predeterminadas constituyen una mejora con respecto a las expresiones de valor predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="da270-126">Default literal expressions are an enhancement to default value expressions.</span></span>
<span data-ttu-id="da270-127">Estas expresiones inicializan una variable en el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="da270-127">These expressions initialize a variable to the default value.</span></span> <span data-ttu-id="da270-128">Donde anteriormente habría que escribir:</span><span class="sxs-lookup"><span data-stu-id="da270-128">Where you previously would write:</span></span>

```csharp
Func<string, bool> whereClause = default(Func<string, bool>);
```

<span data-ttu-id="da270-129">Ahora, se puede pasar por alto el tipo del lado derecho de la inicialización:</span><span class="sxs-lookup"><span data-stu-id="da270-129">You can now omit the type on the right-hand side of the initialization:</span></span>

```csharp
Func<string, bool> whereClause = default;
```

<span data-ttu-id="da270-130">Encontrará más información sobre esta mejora en el tema sobre las [expresiones de valor predeterminadas](../programming-guide/statements-expressions-operators/default-value-expressions.md) de la guía de programación de C#.</span><span class="sxs-lookup"><span data-stu-id="da270-130">You can learn more about this enhancement in the C# Programming Guide topic on [default value expressions](../programming-guide/statements-expressions-operators/default-value-expressions.md).</span></span>

<span data-ttu-id="da270-131">Esta mejora cambia también algunas de las reglas de análisis de [palabras claves predeterminadas](../language-reference/keywords/default.md).</span><span class="sxs-lookup"><span data-stu-id="da270-131">This enhancement also changes some of the parsing rules for the [default keyword](../language-reference/keywords/default.md).</span></span>

## <a name="inferred-tuple-element-names"></a><span data-ttu-id="da270-132">Nombres de elementos de tupla inferidos</span><span class="sxs-lookup"><span data-stu-id="da270-132">Inferred tuple element names</span></span>

<span data-ttu-id="da270-133">Esta característica supone una pequeña mejora con respecto a la característica de tuplas incluida en C# 7.0.</span><span class="sxs-lookup"><span data-stu-id="da270-133">This feature is a small enhancement to the tuples feature introduced in C# 7.0.</span></span> <span data-ttu-id="da270-134">Muchas veces, cuando se inicializa una tupla, las variables usadas en el lado derecho de la asignación son las mismas que los nombres que querríamos dar a los elementos de tupla:</span><span class="sxs-lookup"><span data-stu-id="da270-134">Many times when you initialize a tuple, the variables used for the right side of the assignment are the same as the names you'd like for the tuple elements:</span></span>

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count: count, label: label);
```

<span data-ttu-id="da270-135">Ahora, los nombres de los elementos de tupla se pueden deducir de las variables empleadas para inicializar la tupla en C# 7.1:</span><span class="sxs-lookup"><span data-stu-id="da270-135">The names of tuple elements can be inferred from the variables used to initialize the tuple in C# 7.1:</span></span>

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count, label); // element names are "count" and "label"
```

<span data-ttu-id="da270-136">Encontrará más información sobre esta característica en el tema sobre [tuplas](../tuples.md).</span><span class="sxs-lookup"><span data-stu-id="da270-136">You can learn more about this feature in the [Tuples](../tuples.md) topic.</span></span>

## <a name="reference-assembly-generation"></a><span data-ttu-id="da270-137">Generación de ensamblados de referencia</span><span class="sxs-lookup"><span data-stu-id="da270-137">Reference assembly generation</span></span>

<span data-ttu-id="da270-138">Existen dos nuevas opciones del compilador con las que se generan *ensamblados solo de referencia*: [/refout](../language-reference/compiler-options/refout-compiler-option.md) y [/refonly](../language-reference/compiler-options/refonly-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="da270-138">There are two new compiler options that generate *reference-only assemblies*: [/refout](../language-reference/compiler-options/refout-compiler-option.md) and [/refonly](../language-reference/compiler-options/refonly-compiler-option.md).</span></span>
<span data-ttu-id="da270-139">En los temas de los vínculos se explican estas opciones y los ensamblados de referencia de manera más pormenorizada.</span><span class="sxs-lookup"><span data-stu-id="da270-139">The linked topics explain these options and reference assemblies in more detail.</span></span>
