---
title: 'Control de versiones del lenguaje C#: Guía de C#'
description: Obtenga información sobre cómo se determina la versión del lenguaje C# en función del proyecto y los motivos de esa decisión. Obtenga información sobre cómo invalidar el valor predeterminado de forma manual.
ms.custom: updateeachrelease
ms.date: 08/11/2020
ms.openlocfilehash: ba6f453123668248b2c65ee6a431cb16dfe74c46
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102258408"
---
# <a name="c-language-versioning"></a><span data-ttu-id="6ee37-104">Control de versiones del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="6ee37-104">C# language versioning</span></span>

<span data-ttu-id="6ee37-105">El compilador de C# más actualizado determina una versión de lenguaje predeterminada basada en los marcos o las plataformas de destino del proyecto.</span><span class="sxs-lookup"><span data-stu-id="6ee37-105">The latest C# compiler determines a default language version based on your project's target framework or frameworks.</span></span> <span data-ttu-id="6ee37-106">Visual Studio no proporciona una interfaz de usuario para cambiar el valor, pero se puede cambiar si se modifica el archivo *csproj*.</span><span class="sxs-lookup"><span data-stu-id="6ee37-106">Visual Studio doesn't provide a UI to change the value, but you can change it by editing the *csproj* file.</span></span> <span data-ttu-id="6ee37-107">La opción predeterminada garantiza que se use la versión del lenguaje más reciente compatible con el marco de trabajo de destino.</span><span class="sxs-lookup"><span data-stu-id="6ee37-107">The choice of default ensures that you use the latest language version compatible with your target framework.</span></span> <span data-ttu-id="6ee37-108">Se beneficia del acceso a las características de lenguaje más recientes compatibles con el destino del proyecto.</span><span class="sxs-lookup"><span data-stu-id="6ee37-108">You benefit from access to the latest language features compatible with your project's target.</span></span> <span data-ttu-id="6ee37-109">Esta opción predeterminada también garantiza que no se use un lenguaje que requiera tipos o el comportamiento en tiempo de ejecución no esté disponible en la plataforma de destino.</span><span class="sxs-lookup"><span data-stu-id="6ee37-109">This default choice also ensures you don't use a language that requires types or runtime behavior not available in your target framework.</span></span> <span data-ttu-id="6ee37-110">La elección de una versión del lenguaje más reciente que la predeterminada puede provocar errores en tiempo de compilación y en tiempo de ejecución difíciles de diagnosticar.</span><span class="sxs-lookup"><span data-stu-id="6ee37-110">Choosing a language version newer than the default can cause hard to diagnose compile-time and runtime errors.</span></span>

<span data-ttu-id="6ee37-111">Las reglas de este artículo se aplican al compilador ofrecido con Visual Studio 2019 o el SDK de .NET.</span><span class="sxs-lookup"><span data-stu-id="6ee37-111">The rules in this article apply to the compiler delivered with Visual Studio 2019 or the .NET SDK.</span></span> <span data-ttu-id="6ee37-112">Los compiladores de C# que forman parte de la instalación de Visual Studio 2017 o versiones anteriores del SDK de .NET Core tienen como destino C# 7.0 de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="6ee37-112">The C# compilers that are part of the Visual Studio 2017 installation or earlier .NET Core SDK versions target C# 7.0 by default.</span></span>

<span data-ttu-id="6ee37-113">C# 8.0 solo se admite en .NET Core 3.x y versiones más recientes.</span><span class="sxs-lookup"><span data-stu-id="6ee37-113">C# 8.0 is supported only on .NET Core 3.x and newer versions.</span></span> <span data-ttu-id="6ee37-114">Muchas de las características más recientes requieren características de biblioteca y runtime introducidas en .NET Core 3.x:</span><span class="sxs-lookup"><span data-stu-id="6ee37-114">Many of the newest features require library and runtime features introduced in .NET Core 3.x:</span></span>

- <span data-ttu-id="6ee37-115">[La implementación de interfaz predeterminada](../whats-new/csharp-8.md#default-interface-methods) requiere nuevas características en el CLR de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="6ee37-115">[Default interface implementation](../whats-new/csharp-8.md#default-interface-methods) requires new features in the .NET Core 3.0 CLR.</span></span>
- <span data-ttu-id="6ee37-116">Las [secuencias asincrónicas](../whats-new/csharp-8.md#asynchronous-streams) requieren los nuevos tipos <xref:System.IAsyncDisposable?displayProperty=nameWithType>, <xref:System.Collections.Generic.IAsyncEnumerable%601?displayProperty=nameWithType> y <xref:System.Collections.Generic.IAsyncEnumerator%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6ee37-116">[Async streams](../whats-new/csharp-8.md#asynchronous-streams) require the new types <xref:System.IAsyncDisposable?displayProperty=nameWithType>, <xref:System.Collections.Generic.IAsyncEnumerable%601?displayProperty=nameWithType>, and <xref:System.Collections.Generic.IAsyncEnumerator%601?displayProperty=nameWithType>.</span></span>
- <span data-ttu-id="6ee37-117">Los [índices y los intervalos](../whats-new/csharp-8.md#indices-and-ranges) requieren los nuevos tipos <xref:System.Index?displayProperty=nameWithType>y <xref:System.Range?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6ee37-117">[Indices and ranges](../whats-new/csharp-8.md#indices-and-ranges) require the new types <xref:System.Index?displayProperty=nameWithType> and <xref:System.Range?displayProperty=nameWithType>.</span></span>
- <span data-ttu-id="6ee37-118">Los [tipos de referencia que admiten un valor NULL](../whats-new/csharp-8.md#nullable-reference-types) hacen uso de varios [atributos](attributes/nullable-analysis.md) para proporcionar mejores advertencias.</span><span class="sxs-lookup"><span data-stu-id="6ee37-118">[Nullable reference types](../whats-new/csharp-8.md#nullable-reference-types) make use of several [attributes](attributes/nullable-analysis.md) to provide better warnings.</span></span> <span data-ttu-id="6ee37-119">Esos atributos se han agregado en .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="6ee37-119">Those attributes were added in .NET Core 3.0.</span></span> <span data-ttu-id="6ee37-120">Otras plataformas de destino no se han anotado con ninguno de estos atributos.</span><span class="sxs-lookup"><span data-stu-id="6ee37-120">Other target frameworks haven't been annotated with any of these attributes.</span></span> <span data-ttu-id="6ee37-121">Esto significa que es posible que las advertencias que admiten un valor NULL no reflejen con precisión los posibles problemas.</span><span class="sxs-lookup"><span data-stu-id="6ee37-121">That means nullable warnings may not accurately reflect potential issues.</span></span>

<span data-ttu-id="6ee37-122">C# 9.0 solo se admite en .NET 5 y versiones más recientes.</span><span class="sxs-lookup"><span data-stu-id="6ee37-122">C# 9.0 is supported only on .NET 5 and newer versions.</span></span>

## <a name="defaults"></a><span data-ttu-id="6ee37-123">Valores predeterminados</span><span class="sxs-lookup"><span data-stu-id="6ee37-123">Defaults</span></span>

<span data-ttu-id="6ee37-124">El compilador determina un valor predeterminado según estas reglas:</span><span class="sxs-lookup"><span data-stu-id="6ee37-124">The compiler determines a default based on these rules:</span></span>

| <span data-ttu-id="6ee37-125">Marco de destino</span><span class="sxs-lookup"><span data-stu-id="6ee37-125">Target framework</span></span> | <span data-ttu-id="6ee37-126">version</span><span class="sxs-lookup"><span data-stu-id="6ee37-126">version</span></span> | <span data-ttu-id="6ee37-127">Versión predeterminada del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="6ee37-127">C# language version default</span></span> |
|------------------|---------|-----------------------------|
| <span data-ttu-id="6ee37-128">.NET</span><span class="sxs-lookup"><span data-stu-id="6ee37-128">.NET</span></span>             | <span data-ttu-id="6ee37-129">5.x</span><span class="sxs-lookup"><span data-stu-id="6ee37-129">5.x</span></span>     | <span data-ttu-id="6ee37-130">C# 9.0</span><span class="sxs-lookup"><span data-stu-id="6ee37-130">C# 9.0</span></span>                      |
| <span data-ttu-id="6ee37-131">.NET Core</span><span class="sxs-lookup"><span data-stu-id="6ee37-131">.NET Core</span></span>        | <span data-ttu-id="6ee37-132">3.x</span><span class="sxs-lookup"><span data-stu-id="6ee37-132">3.x</span></span>     | <span data-ttu-id="6ee37-133">C# 8.0</span><span class="sxs-lookup"><span data-stu-id="6ee37-133">C# 8.0</span></span>                      |
| <span data-ttu-id="6ee37-134">.NET Core</span><span class="sxs-lookup"><span data-stu-id="6ee37-134">.NET Core</span></span>        | <span data-ttu-id="6ee37-135">2.x</span><span class="sxs-lookup"><span data-stu-id="6ee37-135">2.x</span></span>     | <span data-ttu-id="6ee37-136">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="6ee37-136">C# 7.3</span></span>                      |
| <span data-ttu-id="6ee37-137">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="6ee37-137">.NET Standard</span></span>    | <span data-ttu-id="6ee37-138">2.1</span><span class="sxs-lookup"><span data-stu-id="6ee37-138">2.1</span></span>     | <span data-ttu-id="6ee37-139">C# 8.0</span><span class="sxs-lookup"><span data-stu-id="6ee37-139">C# 8.0</span></span>                      |
| <span data-ttu-id="6ee37-140">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="6ee37-140">.NET Standard</span></span>    | <span data-ttu-id="6ee37-141">2.0</span><span class="sxs-lookup"><span data-stu-id="6ee37-141">2.0</span></span>     | <span data-ttu-id="6ee37-142">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="6ee37-142">C# 7.3</span></span>                      |
| <span data-ttu-id="6ee37-143">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="6ee37-143">.NET Standard</span></span>    | <span data-ttu-id="6ee37-144">1.x</span><span class="sxs-lookup"><span data-stu-id="6ee37-144">1.x</span></span>     | <span data-ttu-id="6ee37-145">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="6ee37-145">C# 7.3</span></span>                      |
| <span data-ttu-id="6ee37-146">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="6ee37-146">.NET Framework</span></span>   | <span data-ttu-id="6ee37-147">todo</span><span class="sxs-lookup"><span data-stu-id="6ee37-147">all</span></span>     | <span data-ttu-id="6ee37-148">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="6ee37-148">C# 7.3</span></span>                      |

<span data-ttu-id="6ee37-149">Cuando el proyecto tiene como destino un marco en versión preliminar que tenga una versión de lenguaje preliminar correspondiente, la versión de lenguaje que se usa es la que está en versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="6ee37-149">When your project targets a preview framework that has a corresponding preview language version, the language version used is the preview language version.</span></span> <span data-ttu-id="6ee37-150">Puede usar las características más recientes con esa versión preliminar en cualquier entorno, sin que afecte a los proyectos que tienen como destino una versión de .NET Core publicada.</span><span class="sxs-lookup"><span data-stu-id="6ee37-150">You use the latest features with that preview in any environment, without affecting projects that target a released .NET Core version.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6ee37-151">Visual Studio 2017 agregaba una entrada `<LangVersion>latest</LangVersion>` a los archivos de proyecto creados.</span><span class="sxs-lookup"><span data-stu-id="6ee37-151">Visual Studio 2017 added a `<LangVersion>latest</LangVersion>` entry to any project files it created.</span></span> <span data-ttu-id="6ee37-152">Eso implicaba el uso de *C# 7.0* cuando esto sucedía.</span><span class="sxs-lookup"><span data-stu-id="6ee37-152">That meant *C# 7.0* when it was added.</span></span> <span data-ttu-id="6ee37-153">Sin embargo, una vez que se actualiza a Visual Studio 2019, se usa la versión más reciente, sin importar la plataforma de destino.</span><span class="sxs-lookup"><span data-stu-id="6ee37-153">However, once you upgrade to Visual Studio 2019, that means the latest released version, regardless of the target framework.</span></span> <span data-ttu-id="6ee37-154">Estos proyectos ahora [invalidan el comportamiento predeterminado](#override-a-default).</span><span class="sxs-lookup"><span data-stu-id="6ee37-154">These projects now [override the default behavior](#override-a-default).</span></span> <span data-ttu-id="6ee37-155">Debe editar el archivo de proyecto y quitar ese nodo.</span><span class="sxs-lookup"><span data-stu-id="6ee37-155">You should edit the project file and remove that node.</span></span> <span data-ttu-id="6ee37-156">Después, el proyecto usará la versión del compilador recomendada para la plataforma de destino.</span><span class="sxs-lookup"><span data-stu-id="6ee37-156">Then, your project will use the compiler version recommended for your target framework.</span></span>

## <a name="override-a-default"></a><span data-ttu-id="6ee37-157">Invalidación de un valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="6ee37-157">Override a default</span></span>

<span data-ttu-id="6ee37-158">Si debe especificar su versión de C# explícitamente, puede hacerlo de varias maneras:</span><span class="sxs-lookup"><span data-stu-id="6ee37-158">If you must specify your C# version explicitly, you can do so in several ways:</span></span>

- <span data-ttu-id="6ee37-159">Editar manualmente el [archivo del proyecto](#edit-the-project-file).</span><span class="sxs-lookup"><span data-stu-id="6ee37-159">Manually edit your [project file](#edit-the-project-file).</span></span>
- <span data-ttu-id="6ee37-160">Establecer la versión del lenguaje [para varios proyectos en un subdirectorio](#configure-multiple-projects).</span><span class="sxs-lookup"><span data-stu-id="6ee37-160">Set the language version [for multiple projects in a subdirectory](#configure-multiple-projects).</span></span>
- <span data-ttu-id="6ee37-161">Configurar la opción dl compilador [Reemplace la opción del compilador `-langversion`](compiler-options/langversion-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="6ee37-161">Configure the [`-langversion` compiler option](compiler-options/langversion-compiler-option.md).</span></span>

> [!TIP]
> <span data-ttu-id="6ee37-162">Para saber qué versión de lenguaje está usando actualmente, incluya `#error version` (con distinción de mayúsculas y minúsculas) en el código.</span><span class="sxs-lookup"><span data-stu-id="6ee37-162">To know what language version you're currently using, put `#error version` (case sensitive) in your code.</span></span> <span data-ttu-id="6ee37-163">Esto hace que el compilador genere un error de compilador, CS8304, con un mensaje que contiene la versión del compilador que se usa y la versión del lenguaje seleccionada actualmente.</span><span class="sxs-lookup"><span data-stu-id="6ee37-163">This makes the compiler report a compiler error, CS8304, with a message containing the compiler version being used and the current selected language version.</span></span> <span data-ttu-id="6ee37-164">Vea [#error (Referencia de C#)](preprocessor-directives/preprocessor-error.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="6ee37-164">See [#error (C# Reference)](preprocessor-directives/preprocessor-error.md) for more information.</span></span>

### <a name="edit-the-project-file"></a><span data-ttu-id="6ee37-165">Edición del archivo del proyecto</span><span class="sxs-lookup"><span data-stu-id="6ee37-165">Edit the project file</span></span>

<span data-ttu-id="6ee37-166">Puede establecer la versión del lenguaje en el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="6ee37-166">You can set the language version in your project file.</span></span> <span data-ttu-id="6ee37-167">Por ejemplo, si quiere acceder explícitamente a las características en versión preliminar, agregue un elemento similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="6ee37-167">For example, if you explicitly want access to preview features, add an element like this:</span></span>

```xml
<PropertyGroup>
   <LangVersion>preview</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="6ee37-168">El valor `preview` usa la versión preliminar más reciente disponible del lenguaje C# que admite el compilador.</span><span class="sxs-lookup"><span data-stu-id="6ee37-168">The value `preview` uses the latest available preview C# language version that your compiler supports.</span></span>

### <a name="configure-multiple-projects"></a><span data-ttu-id="6ee37-169">Configurar varios proyectos</span><span class="sxs-lookup"><span data-stu-id="6ee37-169">Configure multiple projects</span></span>

<span data-ttu-id="6ee37-170">Para configurar varios proyectos, se puede crear un archivo **Directory.Build.props** que contenga el elemento `<LangVersion>`.</span><span class="sxs-lookup"><span data-stu-id="6ee37-170">To configure multiple projects, you can create a **Directory.Build.props** file that contains the `<LangVersion>` element.</span></span> <span data-ttu-id="6ee37-171">Por lo general, esto se hace en el directorio de la solución.</span><span class="sxs-lookup"><span data-stu-id="6ee37-171">You typically do that in your solution directory.</span></span> <span data-ttu-id="6ee37-172">Agregue lo siguiente a un archivo **Directory.Build.props** en el directorio de la solución:</span><span class="sxs-lookup"><span data-stu-id="6ee37-172">Add the following to a **Directory.Build.props** file in your solution directory:</span></span>

```xml
<Project>
 <PropertyGroup>
   <LangVersion>preview</LangVersion>
 </PropertyGroup>
</Project>
```

<span data-ttu-id="6ee37-173">Las compilaciones de todos los subdirectorios del directorio que contenga ese archivo usarán la sintaxis de la versión preliminar de C#.</span><span class="sxs-lookup"><span data-stu-id="6ee37-173">Builds in all subdirectories of the directory containing that file will use the preview C# version.</span></span> <span data-ttu-id="6ee37-174">Para obtener más información, consulte [Personalización de la compilación](/visualstudio/msbuild/customize-your-build).</span><span class="sxs-lookup"><span data-stu-id="6ee37-174">For more information, see [Customize your build](/visualstudio/msbuild/customize-your-build).</span></span>

## <a name="c-language-version-reference"></a><span data-ttu-id="6ee37-175">Referencia de la versión del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="6ee37-175">C# language version reference</span></span>

<span data-ttu-id="6ee37-176">En la siguiente tabla se muestran las versiones actuales del lenguaje C#.</span><span class="sxs-lookup"><span data-stu-id="6ee37-176">The following table shows all current C# language versions.</span></span> <span data-ttu-id="6ee37-177">Es posible que el compilador no entienda necesariamente todos los valores si es más antiguo.</span><span class="sxs-lookup"><span data-stu-id="6ee37-177">Your compiler may not necessarily understand every value if it's older.</span></span> <span data-ttu-id="6ee37-178">Si instala el SDK de .NET más reciente, tendrá acceso a todo lo que aparece.</span><span class="sxs-lookup"><span data-stu-id="6ee37-178">If you install the latest .NET SDK, then you have access to everything listed.</span></span>

[!INCLUDE [langversion-table](includes/langversion-table.md)]

> [!TIP]
> <span data-ttu-id="6ee37-179">Abra un [shell de línea de comandos para desarrolladores](/visualstudio/ide/reference/command-prompt-powershell) y ejecute el comando siguiente para ver la lista de versiones de idioma disponibles en la máquina.</span><span class="sxs-lookup"><span data-stu-id="6ee37-179">Open a [developer command-line shell](/visualstudio/ide/reference/command-prompt-powershell), and run the following command to see the listing of language versions available on your machine.</span></span>
>
> ```CMD
> csc -langversion:?
> ```
>
> <span data-ttu-id="6ee37-180">Al consultar la opción de compilación [-langversion](compiler-options/langversion-compiler-option.md) de este modo, se imprimirá algo similar a lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6ee37-180">Querying the [-langversion](compiler-options/langversion-compiler-option.md) compile option like this prints something similar to the following:</span></span>
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
> 8.0
> 9.0 (default)
> latestmajor
> preview
> latest
> ```
