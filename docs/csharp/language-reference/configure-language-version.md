---
title: 'Control de versiones del lenguaje C#: Guía de C#'
description: Obtenga información sobre cómo se determina la versión del lenguaje C# en función del proyecto y los motivos de esa decisión. Obtenga información sobre cómo invalidar el valor predeterminado de forma manual.
ms.date: 05/20/2020
ms.openlocfilehash: bbe5b12e378cf47b7c9b2c8576088e949e526a9a
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803004"
---
# <a name="c-language-versioning"></a><span data-ttu-id="00444-104">Control de versiones del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="00444-104">C# language versioning</span></span>

<span data-ttu-id="00444-105">El compilador de C# más actualizado determina una versión de lenguaje predeterminada basada en los marcos o las plataformas de destino del proyecto.</span><span class="sxs-lookup"><span data-stu-id="00444-105">The latest C# compiler determines a default language version based on your project's target framework or frameworks.</span></span> <span data-ttu-id="00444-106">Visual Studio no proporciona una interfaz de usuario para cambiar el valor, pero se puede cambiar si se modifica el archivo *csproj*.</span><span class="sxs-lookup"><span data-stu-id="00444-106">Visual Studio doesn't provide a UI to change the value, but you can change it by editing the *csproj* file.</span></span> <span data-ttu-id="00444-107">La opción predeterminada garantiza que se use la versión del lenguaje más reciente compatible con el marco de trabajo de destino.</span><span class="sxs-lookup"><span data-stu-id="00444-107">The choice of default ensures that you use the latest language version compatible with your target framework.</span></span> <span data-ttu-id="00444-108">Se beneficia del acceso a las características de lenguaje más recientes compatibles con el destino del proyecto.</span><span class="sxs-lookup"><span data-stu-id="00444-108">You benefit from access to the latest language features compatible with your project's target.</span></span> <span data-ttu-id="00444-109">Esta opción predeterminada también garantiza que no se use un lenguaje que requiera tipos o el comportamiento en tiempo de ejecución no esté disponible en la plataforma de destino.</span><span class="sxs-lookup"><span data-stu-id="00444-109">This default choice also ensures you don't use a language that requires types or runtime behavior not available in your target framework.</span></span> <span data-ttu-id="00444-110">La elección de una versión del lenguaje más reciente que la predeterminada puede provocar errores en tiempo de compilación y en tiempo de ejecución difíciles de diagnosticar.</span><span class="sxs-lookup"><span data-stu-id="00444-110">Choosing a language version newer than the default can cause hard to diagnose compile-time and runtime errors.</span></span>

<span data-ttu-id="00444-111">Las reglas de este artículo se aplican al compilador ofrecido con Visual Studio 2019 o al SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="00444-111">The rules in this article apply to the compiler delivered with Visual Studio 2019 or the .NET Core 3.0 SDK.</span></span> <span data-ttu-id="00444-112">Los compiladores de C# que forman parte de la instalación de Visual Studio 2017 o versiones anteriores del SDK de .NET Core tienen como destino C# 7.0 de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="00444-112">The C# compilers that are part of the Visual Studio 2017 installation or earlier .NET Core SDK versions target C# 7.0 by default.</span></span>

<span data-ttu-id="00444-113">C# 8.0 (y versiones posteriores) solo se admite en .NET Core 3.x y versiones más recientes.</span><span class="sxs-lookup"><span data-stu-id="00444-113">C# 8.0 (and higher) is supported only on .NET Core 3.x and newer versions.</span></span> <span data-ttu-id="00444-114">Muchas de las características más recientes requieren características de biblioteca y runtime introducidas en .NET Core 3.x:</span><span class="sxs-lookup"><span data-stu-id="00444-114">Many of the newest features require library and runtime features introduced in .NET Core 3.x:</span></span>

- <span data-ttu-id="00444-115">[La implementación de interfaz predeterminada](../whats-new/csharp-8.md#default-interface-methods) requiere nuevas características en el CLR de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="00444-115">[Default interface implementation](../whats-new/csharp-8.md#default-interface-methods) requires new features in the .NET Core 3.0 CLR.</span></span>
- <span data-ttu-id="00444-116">Las [secuencias asincrónicas](../whats-new/csharp-8.md#asynchronous-streams) requieren los nuevos tipos <xref:System.IAsyncDisposable?displayProperty=nameWithType>, <xref:System.Collections.Generic.IAsyncEnumerable%601?displayProperty=nameWithType> y <xref:System.Collections.Generic.IAsyncEnumerator%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="00444-116">[Async streams](../whats-new/csharp-8.md#asynchronous-streams) require the new types <xref:System.IAsyncDisposable?displayProperty=nameWithType>, <xref:System.Collections.Generic.IAsyncEnumerable%601?displayProperty=nameWithType>, and <xref:System.Collections.Generic.IAsyncEnumerator%601?displayProperty=nameWithType>.</span></span>
- <span data-ttu-id="00444-117">Los [índices y los intervalos](../whats-new/csharp-8.md#indices-and-ranges) requieren los nuevos tipos <xref:System.Index?displayProperty=nameWithType>y <xref:System.Range?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="00444-117">[Indices and ranges](../whats-new/csharp-8.md#indices-and-ranges) require the new types <xref:System.Index?displayProperty=nameWithType> and <xref:System.Range?displayProperty=nameWithType>.</span></span>
- <span data-ttu-id="00444-118">Los [tipos de referencia que admiten un valor NULL](../whats-new/csharp-8.md#nullable-reference-types) hacen uso de varios [atributos](attributes/nullable-analysis.md) para proporcionar mejores advertencias.</span><span class="sxs-lookup"><span data-stu-id="00444-118">[Nullable reference types](../whats-new/csharp-8.md#nullable-reference-types) make use of several [attributes](attributes/nullable-analysis.md) to provide better warnings.</span></span> <span data-ttu-id="00444-119">Esos atributos se han agregado en .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="00444-119">Those attributes were added in .NET Core 3.0.</span></span> <span data-ttu-id="00444-120">Otras plataformas de destino no se han anotado con ninguno de estos atributos.</span><span class="sxs-lookup"><span data-stu-id="00444-120">Other target frameworks haven't been annotated with any of these attributes.</span></span> <span data-ttu-id="00444-121">Esto significa que es posible que las advertencias que admiten un valor NULL no reflejen con precisión los posibles problemas.</span><span class="sxs-lookup"><span data-stu-id="00444-121">That means nullable warnings may not accurately reflect potential issues.</span></span>

## <a name="defaults"></a><span data-ttu-id="00444-122">Valores predeterminados</span><span class="sxs-lookup"><span data-stu-id="00444-122">Defaults</span></span>

<span data-ttu-id="00444-123">El compilador determina un valor predeterminado según estas reglas:</span><span class="sxs-lookup"><span data-stu-id="00444-123">The compiler determines a default based on these rules:</span></span>

| <span data-ttu-id="00444-124">Marco de destino</span><span class="sxs-lookup"><span data-stu-id="00444-124">Target framework</span></span> | <span data-ttu-id="00444-125">version</span><span class="sxs-lookup"><span data-stu-id="00444-125">version</span></span> | <span data-ttu-id="00444-126">Versión predeterminada del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="00444-126">C# language version default</span></span> |
|------------------|---------|-----------------------------|
| <span data-ttu-id="00444-127">.NET Core</span><span class="sxs-lookup"><span data-stu-id="00444-127">.NET Core</span></span>        | <span data-ttu-id="00444-128">3.x</span><span class="sxs-lookup"><span data-stu-id="00444-128">3.x</span></span>     | <span data-ttu-id="00444-129">C# 8.0</span><span class="sxs-lookup"><span data-stu-id="00444-129">C# 8.0</span></span>                      |
| <span data-ttu-id="00444-130">.NET Core</span><span class="sxs-lookup"><span data-stu-id="00444-130">.NET Core</span></span>        | <span data-ttu-id="00444-131">2.x</span><span class="sxs-lookup"><span data-stu-id="00444-131">2.x</span></span>     | <span data-ttu-id="00444-132">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="00444-132">C# 7.3</span></span>                      |
| <span data-ttu-id="00444-133">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="00444-133">.NET Standard</span></span>    | <span data-ttu-id="00444-134">2.1</span><span class="sxs-lookup"><span data-stu-id="00444-134">2.1</span></span>     | <span data-ttu-id="00444-135">C# 8.0</span><span class="sxs-lookup"><span data-stu-id="00444-135">C# 8.0</span></span>                      |
| <span data-ttu-id="00444-136">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="00444-136">.NET Standard</span></span>    | <span data-ttu-id="00444-137">2.0</span><span class="sxs-lookup"><span data-stu-id="00444-137">2.0</span></span>     | <span data-ttu-id="00444-138">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="00444-138">C# 7.3</span></span>                      |
| <span data-ttu-id="00444-139">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="00444-139">.NET Standard</span></span>    | <span data-ttu-id="00444-140">1.x</span><span class="sxs-lookup"><span data-stu-id="00444-140">1.x</span></span>     | <span data-ttu-id="00444-141">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="00444-141">C# 7.3</span></span>                      |
| <span data-ttu-id="00444-142">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="00444-142">.NET Framework</span></span>   | <span data-ttu-id="00444-143">todo</span><span class="sxs-lookup"><span data-stu-id="00444-143">all</span></span>     | <span data-ttu-id="00444-144">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="00444-144">C# 7.3</span></span>                      |

<span data-ttu-id="00444-145">Cuando el proyecto tiene como destino un marco en versión preliminar que tenga una versión de lenguaje preliminar correspondiente, la versión de lenguaje que se usa es la que está en versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="00444-145">When your project targets a preview framework that has a corresponding preview language version, the language version used is the preview language version.</span></span> <span data-ttu-id="00444-146">Puede usar las características más recientes con esa versión preliminar en cualquier entorno, sin que afecte a los proyectos que tienen como destino una versión de .NET Core publicada.</span><span class="sxs-lookup"><span data-stu-id="00444-146">You use the latest features with that preview in any environment, without affecting projects that target a released .NET Core version.</span></span>

## <a name="override-a-default"></a><span data-ttu-id="00444-147">Invalidación de un valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="00444-147">Override a default</span></span>

<span data-ttu-id="00444-148">Si debe especificar su versión de C# explícitamente, puede hacerlo de varias maneras:</span><span class="sxs-lookup"><span data-stu-id="00444-148">If you must specify your C# version explicitly, you can do so in several ways:</span></span>

- <span data-ttu-id="00444-149">Editar manualmente el [archivo del proyecto](#edit-the-project-file).</span><span class="sxs-lookup"><span data-stu-id="00444-149">Manually edit your [project file](#edit-the-project-file).</span></span>
- <span data-ttu-id="00444-150">Establecer la versión del lenguaje [para varios proyectos en un subdirectorio](#configure-multiple-projects).</span><span class="sxs-lookup"><span data-stu-id="00444-150">Set the language version [for multiple projects in a subdirectory](#configure-multiple-projects).</span></span>
- <span data-ttu-id="00444-151">Configurar la opción dl compilador [Reemplace la opción del compilador `-langversion`](compiler-options/langversion-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="00444-151">Configure the [`-langversion` compiler option](compiler-options/langversion-compiler-option.md).</span></span>

### <a name="edit-the-project-file"></a><span data-ttu-id="00444-152">Edición del archivo del proyecto</span><span class="sxs-lookup"><span data-stu-id="00444-152">Edit the project file</span></span>

<span data-ttu-id="00444-153">Puede establecer la versión del lenguaje en el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="00444-153">You can set the language version in your project file.</span></span> <span data-ttu-id="00444-154">Por ejemplo, si quiere acceder explícitamente a las características en versión preliminar, agregue un elemento similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="00444-154">For example, if you explicitly want access to preview features, add an element like this:</span></span>

```xml
<PropertyGroup>
   <LangVersion>preview</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="00444-155">El valor `preview` usa la versión preliminar más reciente disponible del lenguaje C# que admite el compilador.</span><span class="sxs-lookup"><span data-stu-id="00444-155">The value `preview` uses the latest available preview C# language version that your compiler supports.</span></span>

### <a name="configure-multiple-projects"></a><span data-ttu-id="00444-156">Configurar varios proyectos</span><span class="sxs-lookup"><span data-stu-id="00444-156">Configure multiple projects</span></span>

<span data-ttu-id="00444-157">Para configurar varios proyectos, se puede crear un archivo **Directory.Build.props** que contenga el elemento `<LangVersion>`.</span><span class="sxs-lookup"><span data-stu-id="00444-157">To configure multiple projects, you can create a **Directory.Build.props** file that contains the `<LangVersion>` element.</span></span> <span data-ttu-id="00444-158">Por lo general, esto se hace en el directorio de la solución.</span><span class="sxs-lookup"><span data-stu-id="00444-158">You typically do that in your solution directory.</span></span> <span data-ttu-id="00444-159">Agregue lo siguiente a un archivo **Directory.Build.props** en el directorio de la solución:</span><span class="sxs-lookup"><span data-stu-id="00444-159">Add the following to a **Directory.Build.props** file in your solution directory:</span></span>

```xml
<Project>
 <PropertyGroup>
   <LangVersion>preview</LangVersion>
 </PropertyGroup>
</Project>
```

<span data-ttu-id="00444-160">Las compilaciones de todos los subdirectorios del directorio que contenga ese archivo usarán la sintaxis de la versión preliminar de C#.</span><span class="sxs-lookup"><span data-stu-id="00444-160">Builds in all subdirectories of the directory containing that file will use the preview C# version.</span></span> <span data-ttu-id="00444-161">Para obtener más información, consulte el artículo [Personalizar una compilación](/visualstudio/msbuild/customize-your-build).</span><span class="sxs-lookup"><span data-stu-id="00444-161">For more information, see the article on [Customize your build](/visualstudio/msbuild/customize-your-build).</span></span>

## <a name="c-language-version-reference"></a><span data-ttu-id="00444-162">Referencia de la versión del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="00444-162">C# language version reference</span></span>

<span data-ttu-id="00444-163">En la siguiente tabla se muestran las versiones actuales del lenguaje C#.</span><span class="sxs-lookup"><span data-stu-id="00444-163">The following table shows all current C# language versions.</span></span> <span data-ttu-id="00444-164">Es posible que el compilador no entienda necesariamente todos los valores si es más antiguo.</span><span class="sxs-lookup"><span data-stu-id="00444-164">Your compiler may not necessarily understand every value if it's older.</span></span> <span data-ttu-id="00444-165">Si instala .NET Core 3.0 o posterior, tiene acceso a todo lo que aparece.</span><span class="sxs-lookup"><span data-stu-id="00444-165">If you install .NET Core 3.0 or later, then you have access to everything listed.</span></span>

[!INCLUDE [langversion-table](includes/langversion-table.md)]

> [!TIP]
> <span data-ttu-id="00444-166">Abra el [Símbolo del sistema para desarrolladores de Visual Studio](../../framework/tools/developer-command-prompt-for-vs.md) y ejecute el siguiente comando para ver la lista de versiones de idioma disponibles en la máquina.</span><span class="sxs-lookup"><span data-stu-id="00444-166">Open the [Developer Command Prompt for Visual Studio](../../framework/tools/developer-command-prompt-for-vs.md), and run the following command to see the listing of language versions available on your machine.</span></span>
>
> ```CMD
> csc -langversion:?
> ```
>
> <span data-ttu-id="00444-167">Al cuestionar la opción de compilación [ -langversion ](compiler-options/langversion-compiler-option.md) de este modo, se imprimirá algo similar a lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="00444-167">Questioning the [-langversion](compiler-options/langversion-compiler-option.md) compile option like this, will print something similar to the following:</span></span>
>
> ```CMD
> Supported language versions:
> default
> 1
> 2
> 3
> 4
> 5
> 6
> 7.0
> 7.1
> 7.2
> 7.3
> 8.0 (default)
> latestmajor
> preview
> latest
> ```
