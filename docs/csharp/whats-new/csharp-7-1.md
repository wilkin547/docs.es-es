---
title: Novedades de C# 7.1
description: "Información general sobre las nuevas características de C# 7.1."
keywords: "Diseño del lenguaje C#, 7.1, Visual Studio 2017"
author: billwagner
ms.author: wiwagn
ms.date: 08/16/2017
ms.topic: article
ms.prod: .net
ms.devlang: devlang-csharp
ms.openlocfilehash: 02f1f8fc8f0a3221e00e2a3c43ce06423ca43672
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="whats-new-in-c-71"></a><span data-ttu-id="ae05a-104">Novedades de C# 7.1</span><span class="sxs-lookup"><span data-stu-id="ae05a-104">What's new in C# 7.1</span></span>

<span data-ttu-id="ae05a-105">7.1 de C# es la primera versión de punto para el lenguaje C#.</span><span class="sxs-lookup"><span data-stu-id="ae05a-105">C# 7.1 is the first point release to the C# language.</span></span> <span data-ttu-id="ae05a-106">Marca una cadencia de versión mayor para el idioma.</span><span class="sxs-lookup"><span data-stu-id="ae05a-106">It marks an increased release cadence for the language.</span></span> <span data-ttu-id="ae05a-107">Puede utilizar las nuevas características más pronto, lo ideal es que cuando esté listo cada nueva característica.</span><span class="sxs-lookup"><span data-stu-id="ae05a-107">You can use the new features sooner, ideally when each new feature is ready.</span></span> <span data-ttu-id="ae05a-108">C# 7.1 incorpora la posibilidad de configurar el compilador para que coincida con una versión especificada del idioma.</span><span class="sxs-lookup"><span data-stu-id="ae05a-108">C# 7.1 adds the ability to configure the compiler to match a specified version of the language.</span></span> <span data-ttu-id="ae05a-109">Que permite separar la decisión de herramientas de actualización de la decisión de la actualización de versiones de idioma.</span><span class="sxs-lookup"><span data-stu-id="ae05a-109">That enables you to separate the decision to upgrade tools from the decision to upgrade language versions.</span></span>

<span data-ttu-id="ae05a-110">7.1 de C# agrega los [selección de la versión de idioma](#language-version-selection) elemento de configuración, tres nuevas características del lenguaje y comportamiento del compilador nuevo.</span><span class="sxs-lookup"><span data-stu-id="ae05a-110">C# 7.1 adds the [language version selection](#language-version-selection) configuration element, three new language features and new compiler behavior.</span></span>

<span data-ttu-id="ae05a-111">Las nuevas características de lenguaje en esta versión son:</span><span class="sxs-lookup"><span data-stu-id="ae05a-111">The new language features in this release are:</span></span>

* [<span data-ttu-id="ae05a-112">`async``Main` (método)</span><span class="sxs-lookup"><span data-stu-id="ae05a-112">`async` `Main` method</span></span>](#async-main)
  - <span data-ttu-id="ae05a-113">El punto de entrada para una aplicación puede tener la `async` modificador.</span><span class="sxs-lookup"><span data-stu-id="ae05a-113">The entry point for an application can have the `async` modifier.</span></span>
* [<span data-ttu-id="ae05a-114">`default`expresiones literales</span><span class="sxs-lookup"><span data-stu-id="ae05a-114">`default` literal expressions</span></span>](#default-literal-expressions)
  - <span data-ttu-id="ae05a-115">Puede usar expresiones literales de forma predeterminada en las expresiones de valor predeterminado cuando se puede inferir el tipo de destino.</span><span class="sxs-lookup"><span data-stu-id="ae05a-115">You can use default literal expressions in default value expressions when the target type can be inferred.</span></span>
* [<span data-ttu-id="ae05a-116">Nombres de elementos de tupla deducido</span><span class="sxs-lookup"><span data-stu-id="ae05a-116">Inferred tuple element names</span></span>](#inferred-tuple-element-names)
  - <span data-ttu-id="ae05a-117">Los nombres de elementos de tupla pueden deducirse de la inicialización de la tupla en muchos casos.</span><span class="sxs-lookup"><span data-stu-id="ae05a-117">The names of tuple elements can be inferred from tuple initialization in many cases.</span></span>

<span data-ttu-id="ae05a-118">Por último, el compilador tiene dos opciones `/refout` y `/refonly` ese control [hacen referencia a generación del ensamblado](#reference-assembly-generation).</span><span class="sxs-lookup"><span data-stu-id="ae05a-118">Finally, the compiler has two options `/refout` and `/refonly` that control [reference assembly generation](#reference-assembly-generation).</span></span>

## <a name="language-version-selection"></a><span data-ttu-id="ae05a-119">Selección de la versión de idioma</span><span class="sxs-lookup"><span data-stu-id="ae05a-119">Language version selection</span></span>

<span data-ttu-id="ae05a-120">El compilador de C# admite 7.1 de C# a partir de Visual Studio 2017 versión 15.3 o .NET Core SDK 2.0.</span><span class="sxs-lookup"><span data-stu-id="ae05a-120">The C# compiler supports C# 7.1 starting with Visual Studio 2017 version 15.3, or the .NET Core SDK 2.0.</span></span> <span data-ttu-id="ae05a-121">Sin embargo, las 7.1 características están desactivadas de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="ae05a-121">However, the 7.1 features are turned off by default.</span></span> <span data-ttu-id="ae05a-122">Para habilitar las 7.1 características, debe cambiar la configuración de la versión de idioma para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="ae05a-122">To enable the 7.1 features, you need to change the language version setting for your project.</span></span>

<span data-ttu-id="ae05a-123">En Visual Studio, haga doble clic en el nodo del proyecto en el Explorador de soluciones y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="ae05a-123">In Visual Studio, right-click on the project node in Solution Explorer and select **Properties**.</span></span> <span data-ttu-id="ae05a-124">Seleccione el **generar** pestaña y seleccione la **avanzadas** botón.</span><span class="sxs-lookup"><span data-stu-id="ae05a-124">Select the **Build** tab and select the **Advanced** button.</span></span> <span data-ttu-id="ae05a-125">En la lista desplegable, seleccione **C# versión secundaria más reciente (más reciente)**, o una versión específica **C# 7.1** tal y como se muestra en la siguiente imagen.</span><span class="sxs-lookup"><span data-stu-id="ae05a-125">In the dropdown, select **C# latest minor version (latest)**, or the specific version **C# 7.1** as shown in the image following.</span></span> <span data-ttu-id="ae05a-126">El `latest` valor significa que va a utilizar la versión secundaria más reciente en la máquina actual.</span><span class="sxs-lookup"><span data-stu-id="ae05a-126">The `latest` value means you want to use the latest minor version on the current machine.</span></span> <span data-ttu-id="ae05a-127">La `C# 7.1` significa que desea usar C# 7.1, incluso después de que se liberan las versiones secundarias más recientes.</span><span class="sxs-lookup"><span data-stu-id="ae05a-127">The `C# 7.1` means that you want to use C# 7.1, even after newer minor versions are released.</span></span>

![Configuración de la versión de idioma](./media/csharp-7-1/advanced-build-settings.png)

<span data-ttu-id="ae05a-129">Como alternativa, puede editar el archivo "csproj" y agregar o modificar las siguientes líneas:</span><span class="sxs-lookup"><span data-stu-id="ae05a-129">Alternatively, you can edit the "csproj" file and add or modify the following lines:</span></span>

```xml
<PropertyGroup>
  <LangVersion>latest</LangVersion>
</PropertyGroup>
```

> [!NOTE]
> <span data-ttu-id="ae05a-130">Si usa el IDE de Visual Studio para actualizar los archivos csproj, el IDE crea nodos independientes para cada configuración de compilación.</span><span class="sxs-lookup"><span data-stu-id="ae05a-130">If you use the Visual Studio IDE to update your csproj files, the IDE creates separate nodes for each build configuration.</span></span> <span data-ttu-id="ae05a-131">Podrá normalmente establece el valor igual en todas las configuraciones de compilación, pero debe establecer de forma explícita para cada configuración de compilación, o seleccione "Todas las configuraciones" cuando se modifica este valor.</span><span class="sxs-lookup"><span data-stu-id="ae05a-131">You'll typically set the value the same in all build configurations, but you need to set it explicitly for each build configuration, or select "All Configurations" when you modify this setting.</span></span> <span data-ttu-id="ae05a-132">Verá lo siguiente en el archivo csproj:</span><span class="sxs-lookup"><span data-stu-id="ae05a-132">You'll see the following in your csproj file:</span></span>

```xml
<PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Release|AnyCPU'">
  <LangVersion>latest</LangVersion>
</PropertyGroup>

<PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Debug|AnyCPU'">
  <LangVersion>latest</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="ae05a-133">Valores válidos para el `LangVersion` elemento son:</span><span class="sxs-lookup"><span data-stu-id="ae05a-133">Valid settings for the `LangVersion` element are:</span></span>

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

<span data-ttu-id="ae05a-134">Las cadenas especiales `default` y `latest` resolver en las últimas versiones de idioma principal y secundaria instaladas en el equipo de compilación, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="ae05a-134">The special strings `default` and `latest` resolve to the latest major and minor language versions installed on the build machine, respectively.</span></span>

<span data-ttu-id="ae05a-135">Esta configuración desacopla instalar nuevas versiones del SDK y herramientas en el entorno de desarrollo de la elección de incorporar nuevas características del lenguaje en un proyecto.</span><span class="sxs-lookup"><span data-stu-id="ae05a-135">This setting decouples installing new versions of the SDK and tools in your development environment from choosing to incorporate new language features in a project.</span></span> <span data-ttu-id="ae05a-136">Puede instalar el SDK y herramientas más recientes en el equipo de compilación.</span><span class="sxs-lookup"><span data-stu-id="ae05a-136">You can install the latest SDK and tools on your build machine.</span></span> <span data-ttu-id="ae05a-137">Cada proyecto puede configurarse para usar una versión específica del idioma para su compilación.</span><span class="sxs-lookup"><span data-stu-id="ae05a-137">Each project can be configured to use a specific version of the language for its build.</span></span>

## <a name="async-main"></a><span data-ttu-id="ae05a-138">Async principal</span><span class="sxs-lookup"><span data-stu-id="ae05a-138">Async main</span></span>

<span data-ttu-id="ae05a-139">Un *async principal* método le permite usar `await` en su `Main` método.</span><span class="sxs-lookup"><span data-stu-id="ae05a-139">An *async main* method enables you to use `await` in your `Main` method.</span></span>
<span data-ttu-id="ae05a-140">Anteriormente tendría que escribir:</span><span class="sxs-lookup"><span data-stu-id="ae05a-140">Previously you would need to write:</span></span>

```csharp
static int Main()
{
    return DoAsyncWork().GetAwaiter().GetResult();
}
```

<span data-ttu-id="ae05a-141">Ahora puede escribir:</span><span class="sxs-lookup"><span data-stu-id="ae05a-141">You can now write:</span></span>

```csharp
static async Task<int> Main()
{
    // This could also be replaced with the body
    // DoAsyncWork, including its await expressions:
    return await DoAsyncWork();
}
```

<span data-ttu-id="ae05a-142">Si el programa no devuelve un código de salida, puede declarar un `Main` método que devuelve un <xref:System.Threading.Tasks.Task>:</span><span class="sxs-lookup"><span data-stu-id="ae05a-142">If your program doesn't return an exit code, you can declare a `Main` method that returns a <xref:System.Threading.Tasks.Task>:</span></span>

```csharp
static async Task Main()
{
    await SomeAsyncMethod();
}
```

<span data-ttu-id="ae05a-143">Puede leer más acerca de los detalles en el [async principal](../programming-guide/main-and-command-args/index.md) tema en la Guía de programación.</span><span class="sxs-lookup"><span data-stu-id="ae05a-143">You can read more about the details in the [async main](../programming-guide/main-and-command-args/index.md) topic in the programming guide.</span></span>

## <a name="default-literal-expressions"></a><span data-ttu-id="ae05a-144">Expresiones literales de forma predeterminada</span><span class="sxs-lookup"><span data-stu-id="ae05a-144">Default literal expressions</span></span>

<span data-ttu-id="ae05a-145">Expresiones literales predeterminados constituyen una mejora en expresiones de valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="ae05a-145">Default literal expressions are an enhancement to default value expressions.</span></span>
<span data-ttu-id="ae05a-146">Estas expresiones inicializan una variable en el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="ae05a-146">These expressions initialize a variable to the default value.</span></span> <span data-ttu-id="ae05a-147">Donde anteriormente habría que escribir:</span><span class="sxs-lookup"><span data-stu-id="ae05a-147">Where you previously would write:</span></span>

```csharp
Func<string, bool> whereClause = default(Func<string, bool>);
```

<span data-ttu-id="ae05a-148">Ahora se puede omitir el tipo en el lado derecho de la inicialización:</span><span class="sxs-lookup"><span data-stu-id="ae05a-148">You can now omit the type on the right-hand side of the initialization:</span></span>

```csharp
Func<string, bool> whereClause = default;
```

<span data-ttu-id="ae05a-149">Se puede obtener más información acerca de esta mejora en el tema de la Guía de programación de C# en [predeterminado expresiones de valor](../programming-guide/statements-expressions-operators/default-value-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="ae05a-149">You can learn more about this enhancement in the C# Programming Guide topic on [default value expressions](../programming-guide/statements-expressions-operators/default-value-expressions.md).</span></span>

<span data-ttu-id="ae05a-150">Esta mejora también cambia algunas de las reglas de análisis de la [palabra clave predeterminada](../language-reference/keywords/default.md).</span><span class="sxs-lookup"><span data-stu-id="ae05a-150">This enhancement also changes some of the parsing rules for the [default keyword](../language-reference/keywords/default.md).</span></span>

## <a name="inferred-tuple-element-names"></a><span data-ttu-id="ae05a-151">Nombres de elementos de tupla deducido</span><span class="sxs-lookup"><span data-stu-id="ae05a-151">Inferred tuple element names</span></span>

<span data-ttu-id="ae05a-152">Esta característica es una pequeña mejora la característica de tuplas que se introdujo en C# 7.0.</span><span class="sxs-lookup"><span data-stu-id="ae05a-152">This feature is a small enhancement to the tuples feature introduced in C# 7.0.</span></span> <span data-ttu-id="ae05a-153">Muchas veces cuando se inicializa una tupla, las variables utilizadas para el lado derecho de la asignación son los mismos que los nombres que desea para los elementos de tupla:</span><span class="sxs-lookup"><span data-stu-id="ae05a-153">Many times when you initialize a tuple, the variables used for the right side of the assignment are the same as the names you'd like for the tuple elements:</span></span>

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count: count, label: label);
```

<span data-ttu-id="ae05a-154">Los nombres de elementos de tupla se pueden inferir a partir de las variables que se utiliza para inicializar la tupla en C# 7.1:</span><span class="sxs-lookup"><span data-stu-id="ae05a-154">The names of tuple elements can be inferred from the variables used to initialize the tuple in C# 7.1:</span></span>

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count, label); // element names are "count" and "label"
```

<span data-ttu-id="ae05a-155">Puede aprender más acerca de esta característica en el [tuplas](../tuples.md) tema.</span><span class="sxs-lookup"><span data-stu-id="ae05a-155">You can learn more about this feature in the [Tuples](../tuples.md) topic.</span></span>

## <a name="reference-assembly-generation"></a><span data-ttu-id="ae05a-156">Generación del ensamblado de referencia</span><span class="sxs-lookup"><span data-stu-id="ae05a-156">Reference assembly generation</span></span>

<span data-ttu-id="ae05a-157">Hay dos nuevas opciones de compilador que generen *ensamblados de referencia*: [/refout](../language-reference/compiler-options/refout-compiler-option.md) y [/refonly](../language-reference/compiler-options/refonly-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="ae05a-157">There are two new compiler options that generate *reference-only assemblies*: [/refout](../language-reference/compiler-options/refout-compiler-option.md) and [/refonly](../language-reference/compiler-options/refonly-compiler-option.md).</span></span>
<span data-ttu-id="ae05a-158">Los temas vinculados explican estas opciones y los ensamblados de referencia con más detalle.</span><span class="sxs-lookup"><span data-stu-id="ae05a-158">The linked topics explain these options and reference assemblies in more detail.</span></span>
