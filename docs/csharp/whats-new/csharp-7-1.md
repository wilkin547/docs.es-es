---
title: Novedades de C# 7.1
description: Información general sobre las nuevas características en C# 7.1.
ms.date: 08/16/2017
ms.openlocfilehash: 00baec45d7582d3ac12c7b0865241f5cd8159246
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="whats-new-in-c-71"></a><span data-ttu-id="184f4-103">Novedades de C# 7.1</span><span class="sxs-lookup"><span data-stu-id="184f4-103">What's new in C# 7.1</span></span>

<span data-ttu-id="184f4-104">C# 7.1 es la primera versión secundaria del lenguaje C#.</span><span class="sxs-lookup"><span data-stu-id="184f4-104">C# 7.1 is the first point release to the C# language.</span></span> <span data-ttu-id="184f4-105">Marca una cadencia de versión mayor en el lenguaje.</span><span class="sxs-lookup"><span data-stu-id="184f4-105">It marks an increased release cadence for the language.</span></span> <span data-ttu-id="184f4-106">Podrá usar las nuevas características más pronto, lo ideal es que cuando vayan estando listas.</span><span class="sxs-lookup"><span data-stu-id="184f4-106">You can use the new features sooner, ideally when each new feature is ready.</span></span> <span data-ttu-id="184f4-107">C# 7.1 incluye la posibilidad de configurar el compilador para que coincida con una versión especificada del lenguaje.</span><span class="sxs-lookup"><span data-stu-id="184f4-107">C# 7.1 adds the ability to configure the compiler to match a specified version of the language.</span></span> <span data-ttu-id="184f4-108">Ello permite aislar la decisión de actualizar las herramientas de la decisión de actualizar las versiones de lenguaje.</span><span class="sxs-lookup"><span data-stu-id="184f4-108">That enables you to separate the decision to upgrade tools from the decision to upgrade language versions.</span></span>

<span data-ttu-id="184f4-109">C# 7.1 incorpora el elemento de configuración de [selección de versión de lenguaje](#language-version-selection), tres nuevas características de lenguaje y un nuevo comportamiento del compilador.</span><span class="sxs-lookup"><span data-stu-id="184f4-109">C# 7.1 adds the [language version selection](#language-version-selection) configuration element, three new language features and new compiler behavior.</span></span>

<span data-ttu-id="184f4-110">Las nuevas características de lenguaje de esta versión son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="184f4-110">The new language features in this release are:</span></span>

* [<span data-ttu-id="184f4-111">Método `async` `Main`</span><span class="sxs-lookup"><span data-stu-id="184f4-111">`async` `Main` method</span></span>](#async-main)
  - <span data-ttu-id="184f4-112">El punto de entrada de una aplicación puede tener el modificador `async`.</span><span class="sxs-lookup"><span data-stu-id="184f4-112">The entry point for an application can have the `async` modifier.</span></span>
* [<span data-ttu-id="184f4-113">Expresiones literales `default`</span><span class="sxs-lookup"><span data-stu-id="184f4-113">`default` literal expressions</span></span>](#default-literal-expressions)
  - <span data-ttu-id="184f4-114">Se pueden usar expresiones literales predeterminadas en expresiones de valor predeterminadas cuando el tipo de destino se pueda inferir.</span><span class="sxs-lookup"><span data-stu-id="184f4-114">You can use default literal expressions in default value expressions when the target type can be inferred.</span></span>
* [<span data-ttu-id="184f4-115">Nombres de elementos de tupla inferidos</span><span class="sxs-lookup"><span data-stu-id="184f4-115">Inferred tuple element names</span></span>](#inferred-tuple-element-names)
  - <span data-ttu-id="184f4-116">En muchos casos, los nombres de elementos de tupla se pueden deducir de la inicialización de la tupla.</span><span class="sxs-lookup"><span data-stu-id="184f4-116">The names of tuple elements can be inferred from tuple initialization in many cases.</span></span>

<span data-ttu-id="184f4-117">Por último, el compilador tiene dos opciones, `/refout` y `/refonly`, que controlan la [generación de ensamblados de referencia](#reference-assembly-generation).</span><span class="sxs-lookup"><span data-stu-id="184f4-117">Finally, the compiler has two options `/refout` and `/refonly` that control [reference assembly generation](#reference-assembly-generation).</span></span>

## <a name="language-version-selection"></a><span data-ttu-id="184f4-118">Selección de versión del lenguaje</span><span class="sxs-lookup"><span data-stu-id="184f4-118">Language version selection</span></span>

<span data-ttu-id="184f4-119">El compilador de C# admite C# 7.1 desde Visual Studio 2017 versión 15.3 o el SDK de .NET Core 2.0.</span><span class="sxs-lookup"><span data-stu-id="184f4-119">The C# compiler supports C# 7.1 starting with Visual Studio 2017 version 15.3, or the .NET Core SDK 2.0.</span></span> <span data-ttu-id="184f4-120">Las siguientes características de 7.1, en cambio, están deshabilitadas de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="184f4-120">However, the 7.1 features are turned off by default.</span></span> <span data-ttu-id="184f4-121">Para habilitarlas, debe cambiar la configuración de la versión de lenguaje del proyecto.</span><span class="sxs-lookup"><span data-stu-id="184f4-121">To enable the 7.1 features, you need to change the language version setting for your project.</span></span>

<span data-ttu-id="184f4-122">En el Explorador de soluciones de Visual Studio, haga clic con el botón derecho en el nodo de proyecto y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="184f4-122">In Visual Studio, right-click on the project node in Solution Explorer and select **Properties**.</span></span> <span data-ttu-id="184f4-123">Seleccione la pestaña **Compilar** y, después, el botón **Opciones avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="184f4-123">Select the **Build** tab and select the **Advanced** button.</span></span> <span data-ttu-id="184f4-124">En la lista desplegable, seleccione **C# latest minor version (latest)** (última versión secundaria de C# [más reciente]) o la versión específica **C# 7.1**, tal y como se muestra en la siguiente imagen.</span><span class="sxs-lookup"><span data-stu-id="184f4-124">In the dropdown, select **C# latest minor version (latest)**, or the specific version **C# 7.1** as shown in the image following.</span></span> <span data-ttu-id="184f4-125">El valor `latest` indica que se va a usar la versión secundaria más reciente en el equipo actual.</span><span class="sxs-lookup"><span data-stu-id="184f4-125">The `latest` value means you want to use the latest minor version on the current machine.</span></span> <span data-ttu-id="184f4-126">`C# 7.1` señala que se quiere usar C# 7.1, aun cuando posteriormente se lancen versiones secundarias más recientes.</span><span class="sxs-lookup"><span data-stu-id="184f4-126">The `C# 7.1` means that you want to use C# 7.1, even after newer minor versions are released.</span></span>

![Establecer la versión de lenguaje](./media/csharp-7-1/advanced-build-settings.png)

<span data-ttu-id="184f4-128">También puede editar el archivo "csproj" y agregar o modificar las siguientes líneas:</span><span class="sxs-lookup"><span data-stu-id="184f4-128">Alternatively, you can edit the "csproj" file and add or modify the following lines:</span></span>

```xml
<PropertyGroup>
  <LangVersion>latest</LangVersion>
</PropertyGroup>
```

> [!NOTE]
> <span data-ttu-id="184f4-129">Si usa el IDE de Visual Studio para actualizar los archivos csproj, este creará nodos independientes por cada configuración de compilación existente.</span><span class="sxs-lookup"><span data-stu-id="184f4-129">If you use the Visual Studio IDE to update your csproj files, the IDE creates separate nodes for each build configuration.</span></span> <span data-ttu-id="184f4-130">Normalmente, se establece el mismo valor en todas las configuraciones de compilación, pero deberá establecerse de forma explícita en cada configuración de compilación, o bien seleccionar "All Configurations" (Todas las configuraciones) cuando este valor se modifique.</span><span class="sxs-lookup"><span data-stu-id="184f4-130">You'll typically set the value the same in all build configurations, but you need to set it explicitly for each build configuration, or select "All Configurations" when you modify this setting.</span></span> <span data-ttu-id="184f4-131">Verá lo siguiente en el archivo csproj:</span><span class="sxs-lookup"><span data-stu-id="184f4-131">You'll see the following in your csproj file:</span></span>

```xml
<PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Release|AnyCPU'">
  <LangVersion>latest</LangVersion>
</PropertyGroup>

<PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Debug|AnyCPU'">
  <LangVersion>latest</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="184f4-132">Estos son los valores válidos en el elemento `LangVersion`:</span><span class="sxs-lookup"><span data-stu-id="184f4-132">Valid settings for the `LangVersion` element are:</span></span>

* `ISO-1`
* `ISO-2`
* `3`
* `4`
* `5`
* `6`
* `7`
* `7.1`
* `default`
* `latest`

<span data-ttu-id="184f4-133">Las cadenas especiales `default` y `latest` se resuelven en las versiones de lenguaje principal y secundaria respectivamente más recientes que haya instaladas en el equipo de compilación.</span><span class="sxs-lookup"><span data-stu-id="184f4-133">The special strings `default` and `latest` resolve to the latest major and minor language versions installed on the build machine, respectively.</span></span>

<span data-ttu-id="184f4-134">Esta configuración hace que no haya conexión entre la instalación de nuevas versiones del SDK y herramientas en el entorno de desarrollo y la decisión de incorporar nuevas características del lenguaje en un proyecto.</span><span class="sxs-lookup"><span data-stu-id="184f4-134">This setting decouples installing new versions of the SDK and tools in your development environment from choosing to incorporate new language features in a project.</span></span> <span data-ttu-id="184f4-135">Puede instalar el SDK y las herramientas más recientes en el equipo de compilación.</span><span class="sxs-lookup"><span data-stu-id="184f4-135">You can install the latest SDK and tools on your build machine.</span></span> <span data-ttu-id="184f4-136">Cada proyecto se puede configurar para que, durante su compilación, se use una versión de lenguaje específica.</span><span class="sxs-lookup"><span data-stu-id="184f4-136">Each project can be configured to use a specific version of the language for its build.</span></span>

## <a name="async-main"></a><span data-ttu-id="184f4-137">Async main</span><span class="sxs-lookup"><span data-stu-id="184f4-137">Async main</span></span>

<span data-ttu-id="184f4-138">Un método *async main* permite usar `await` en el método `Main`.</span><span class="sxs-lookup"><span data-stu-id="184f4-138">An *async main* method enables you to use `await` in your `Main` method.</span></span>
<span data-ttu-id="184f4-139">Anteriormente, hubiera sido necesario escribir lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="184f4-139">Previously you would need to write:</span></span>

```csharp
static int Main()
{
    return DoAsyncWork().GetAwaiter().GetResult();
}
```

<span data-ttu-id="184f4-140">Ahora se puede escribir esto:</span><span class="sxs-lookup"><span data-stu-id="184f4-140">You can now write:</span></span>

```csharp
static async Task<int> Main()
{
    // This could also be replaced with the body
    // DoAsyncWork, including its await expressions:
    return await DoAsyncWork();
}
```

<span data-ttu-id="184f4-141">Si el programa no devuelve un código de salida, puede declarar un método `Main` que devuelva una <xref:System.Threading.Tasks.Task>:</span><span class="sxs-lookup"><span data-stu-id="184f4-141">If your program doesn't return an exit code, you can declare a `Main` method that returns a <xref:System.Threading.Tasks.Task>:</span></span>

```csharp
static async Task Main()
{
    await SomeAsyncMethod();
}
```

<span data-ttu-id="184f4-142">En el tema sobre [async main](../programming-guide/main-and-command-args/index.md) de la guía de programación puede leer más detalles al respecto.</span><span class="sxs-lookup"><span data-stu-id="184f4-142">You can read more about the details in the [async main](../programming-guide/main-and-command-args/index.md) topic in the programming guide.</span></span>

## <a name="default-literal-expressions"></a><span data-ttu-id="184f4-143">Expresiones literales predeterminadas</span><span class="sxs-lookup"><span data-stu-id="184f4-143">Default literal expressions</span></span>

<span data-ttu-id="184f4-144">Las expresiones literales predeterminadas constituyen una mejora con respecto a las expresiones de valor predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="184f4-144">Default literal expressions are an enhancement to default value expressions.</span></span>
<span data-ttu-id="184f4-145">Estas expresiones inicializan una variable en el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="184f4-145">These expressions initialize a variable to the default value.</span></span> <span data-ttu-id="184f4-146">Donde anteriormente habría que escribir:</span><span class="sxs-lookup"><span data-stu-id="184f4-146">Where you previously would write:</span></span>

```csharp
Func<string, bool> whereClause = default(Func<string, bool>);
```

<span data-ttu-id="184f4-147">Ahora, se puede pasar por alto el tipo del lado derecho de la inicialización:</span><span class="sxs-lookup"><span data-stu-id="184f4-147">You can now omit the type on the right-hand side of the initialization:</span></span>

```csharp
Func<string, bool> whereClause = default;
```

<span data-ttu-id="184f4-148">Encontrará más información sobre esta mejora en el tema sobre las [expresiones de valor predeterminadas](../programming-guide/statements-expressions-operators/default-value-expressions.md) de la guía de programación de C#.</span><span class="sxs-lookup"><span data-stu-id="184f4-148">You can learn more about this enhancement in the C# Programming Guide topic on [default value expressions](../programming-guide/statements-expressions-operators/default-value-expressions.md).</span></span>

<span data-ttu-id="184f4-149">Esta mejora cambia también algunas de las reglas de análisis de [palabras claves predeterminadas](../language-reference/keywords/default.md).</span><span class="sxs-lookup"><span data-stu-id="184f4-149">This enhancement also changes some of the parsing rules for the [default keyword](../language-reference/keywords/default.md).</span></span>

## <a name="inferred-tuple-element-names"></a><span data-ttu-id="184f4-150">Nombres de elementos de tupla inferidos</span><span class="sxs-lookup"><span data-stu-id="184f4-150">Inferred tuple element names</span></span>

<span data-ttu-id="184f4-151">Esta característica supone una pequeña mejora con respecto a la característica de tuplas incluida en C# 7.0.</span><span class="sxs-lookup"><span data-stu-id="184f4-151">This feature is a small enhancement to the tuples feature introduced in C# 7.0.</span></span> <span data-ttu-id="184f4-152">Muchas veces, cuando se inicializa una tupla, las variables usadas en el lado derecho de la asignación son las mismas que los nombres que querríamos dar a los elementos de tupla:</span><span class="sxs-lookup"><span data-stu-id="184f4-152">Many times when you initialize a tuple, the variables used for the right side of the assignment are the same as the names you'd like for the tuple elements:</span></span>

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count: count, label: label);
```

<span data-ttu-id="184f4-153">Ahora, los nombres de los elementos de tupla se pueden deducir de las variables empleadas para inicializar la tupla en C# 7.1:</span><span class="sxs-lookup"><span data-stu-id="184f4-153">The names of tuple elements can be inferred from the variables used to initialize the tuple in C# 7.1:</span></span>

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count, label); // element names are "count" and "label"
```

<span data-ttu-id="184f4-154">Encontrará más información sobre esta característica en el tema sobre [tuplas](../tuples.md).</span><span class="sxs-lookup"><span data-stu-id="184f4-154">You can learn more about this feature in the [Tuples](../tuples.md) topic.</span></span>

## <a name="reference-assembly-generation"></a><span data-ttu-id="184f4-155">Generación de ensamblados de referencia</span><span class="sxs-lookup"><span data-stu-id="184f4-155">Reference assembly generation</span></span>

<span data-ttu-id="184f4-156">Existen dos nuevas opciones del compilador con las que se generan *ensamblados solo de referencia*: [/refout](../language-reference/compiler-options/refout-compiler-option.md) y [/refonly](../language-reference/compiler-options/refonly-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="184f4-156">There are two new compiler options that generate *reference-only assemblies*: [/refout](../language-reference/compiler-options/refout-compiler-option.md) and [/refonly](../language-reference/compiler-options/refonly-compiler-option.md).</span></span>
<span data-ttu-id="184f4-157">En los temas de los vínculos se explican estas opciones y los ensamblados de referencia de manera más pormenorizada.</span><span class="sxs-lookup"><span data-stu-id="184f4-157">The linked topics explain these options and reference assemblies in more detail.</span></span>
