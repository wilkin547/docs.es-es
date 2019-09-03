---
title: 'Control de versiones del lenguaje C#: Guía de C#'
description: Obtenga información sobre cómo la versión del lenguaje C# se determina en función del proyecto y los distintos valores a los que puede ajustarlo manualmente.
ms.date: 07/10/2019
ms.openlocfilehash: fae36f5305e23fbfa1c55c5881e37391670f93ab
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2019
ms.locfileid: "70040350"
---
# <a name="c-language-versioning"></a><span data-ttu-id="a19cf-103">Control de versiones del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="a19cf-103">C# language versioning</span></span>

<span data-ttu-id="a19cf-104">El compilador de C# más actualizado determina una versión de lenguaje predeterminada basada en los marcos o las plataformas de destino del proyecto.</span><span class="sxs-lookup"><span data-stu-id="a19cf-104">The latest C# compiler determines a default language version based on your project's target framework or frameworks.</span></span> <span data-ttu-id="a19cf-105">Esto se debe a que el lenguaje C# puede tener características que se basan en tipos o componentes en tiempo de ejecución que no están disponibles en cada implementación de. NET.</span><span class="sxs-lookup"><span data-stu-id="a19cf-105">This is because the C# language may have features that rely on types or runtime components that are not available in every .NET implementation.</span></span> <span data-ttu-id="a19cf-106">Esto también garantiza que, para cualquier destino para el cual se compiló el proyecto, obtendrá la última versión de lenguaje compatible de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a19cf-106">This also ensures that for whatever target your project is built against, you get the highest compatible language version by default.</span></span>

<span data-ttu-id="a19cf-107">Las reglas de este artículo se aplican al compilador ofrecido con Visual Studio 2019 o al SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="a19cf-107">The rules in this article apply to the compiler delivered with Visual Studio 2019, or the .NET Core 3.0 SDK.</span></span> <span data-ttu-id="a19cf-108">Los compiladores de C# que forman parte de la instalación de Visual Studio 2017 o versiones anteriores del SDK de .NET Core tienen como destino C# 7.0 de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a19cf-108">The C# compilers that are part of the Visual Studio 2017 installation or earlier .NET Core SDK versions target C# 7.0 by default.</span></span> 

## <a name="defaults"></a><span data-ttu-id="a19cf-109">Valores predeterminados</span><span class="sxs-lookup"><span data-stu-id="a19cf-109">Defaults</span></span>

<span data-ttu-id="a19cf-110">El compilador determina un valor predeterminado según estas reglas:</span><span class="sxs-lookup"><span data-stu-id="a19cf-110">The compiler determines a default based on these rules:</span></span>

|<span data-ttu-id="a19cf-111">Marco de destino</span><span class="sxs-lookup"><span data-stu-id="a19cf-111">Target framework</span></span>|<span data-ttu-id="a19cf-112">version</span><span class="sxs-lookup"><span data-stu-id="a19cf-112">version</span></span>|<span data-ttu-id="a19cf-113">Versión predeterminada del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="a19cf-113">C# language version default</span></span>|
|----------------|-------|---------------------------|
|<span data-ttu-id="a19cf-114">Núcleo de .NET</span><span class="sxs-lookup"><span data-stu-id="a19cf-114">.NET Core</span></span>|<span data-ttu-id="a19cf-115">3.x</span><span class="sxs-lookup"><span data-stu-id="a19cf-115">3.x</span></span>|<span data-ttu-id="a19cf-116">C# 8.0</span><span class="sxs-lookup"><span data-stu-id="a19cf-116">C# 8.0</span></span>|
|<span data-ttu-id="a19cf-117">Núcleo de .NET</span><span class="sxs-lookup"><span data-stu-id="a19cf-117">.NET Core</span></span>|<span data-ttu-id="a19cf-118">2.x</span><span class="sxs-lookup"><span data-stu-id="a19cf-118">2.x</span></span>|<span data-ttu-id="a19cf-119">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="a19cf-119">C# 7.3</span></span>|
|<span data-ttu-id="a19cf-120">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="a19cf-120">.NET Standard</span></span>|<span data-ttu-id="a19cf-121">todo</span><span class="sxs-lookup"><span data-stu-id="a19cf-121">all</span></span>|<span data-ttu-id="a19cf-122">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="a19cf-122">C# 7.3</span></span>|
|<span data-ttu-id="a19cf-123">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="a19cf-123">.NET Framework</span></span>|<span data-ttu-id="a19cf-124">todo</span><span class="sxs-lookup"><span data-stu-id="a19cf-124">all</span></span>|<span data-ttu-id="a19cf-125">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="a19cf-125">C# 7.3</span></span>|

## <a name="default-for-previews"></a><span data-ttu-id="a19cf-126">Valor predeterminado para las versiones preliminares</span><span class="sxs-lookup"><span data-stu-id="a19cf-126">Default for previews</span></span>

<span data-ttu-id="a19cf-127">Cuando el proyecto tiene como destino un marco en versión preliminar que tenga una versión de lenguaje preliminar correspondiente, la versión de lenguaje que se usa es la que está en versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="a19cf-127">When your project targets a preview framework that has a corresponding preview language version, the language version used is the preview language version.</span></span> <span data-ttu-id="a19cf-128">Esto asegura que puede usar las características más recientes que se garantiza que funcionen con esa versión preliminar en cualquier entorno sin que afecte a los proyectos que tienen como destino una versión de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a19cf-128">This ensures that you can use the latest features that are guaranteed to work with that preview in any environment without affecting your projects that target a released .NET Core version.</span></span>

## <a name="override-a-default"></a><span data-ttu-id="a19cf-129">Invalidación de un valor predeterminado</span><span class="sxs-lookup"><span data-stu-id="a19cf-129">Override a default</span></span>

<span data-ttu-id="a19cf-130">Si debe especificar su versión de C# explícitamente, puede hacerlo de varias maneras:</span><span class="sxs-lookup"><span data-stu-id="a19cf-130">If you must specify your C# version explicitly, you can do so in several ways:</span></span>

- <span data-ttu-id="a19cf-131">Editar manualmente el [archivo del proyecto](#edit-the-project-file).</span><span class="sxs-lookup"><span data-stu-id="a19cf-131">Manually edit your [project file](#edit-the-project-file).</span></span>
- <span data-ttu-id="a19cf-132">Establecer la versión del lenguaje [para varios proyectos en un subdirectorio](#configure-multiple-projects).</span><span class="sxs-lookup"><span data-stu-id="a19cf-132">Set the language version [for multiple projects in a subdirectory](#configure-multiple-projects).</span></span>
- <span data-ttu-id="a19cf-133">Configurar la [opción del compilador `-langversion`](compiler-options/langversion-compiler-option.md)</span><span class="sxs-lookup"><span data-stu-id="a19cf-133">Configure the [`-langversion` compiler option](compiler-options/langversion-compiler-option.md)</span></span>

### <a name="edit-the-project-file"></a><span data-ttu-id="a19cf-134">Edición del archivo del proyecto</span><span class="sxs-lookup"><span data-stu-id="a19cf-134">Edit the project file</span></span>

<span data-ttu-id="a19cf-135">Puede establecer la versión del lenguaje en el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="a19cf-135">You can set the language version in your project file.</span></span> <span data-ttu-id="a19cf-136">Por ejemplo, si quiere acceder explícitamente a las características en versión preliminar, agregue un elemento similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="a19cf-136">For example, if you explicitly want access to preview features, add an element like this:</span></span>

```xml
<PropertyGroup>
   <LangVersion>preview</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="a19cf-137">El valor `preview` usa la versión preliminar más reciente disponible del lenguaje C# que admite el compilador.</span><span class="sxs-lookup"><span data-stu-id="a19cf-137">The value `preview` uses the latest available preview C# language version that your compiler supports.</span></span>

### <a name="configure-multiple-projects"></a><span data-ttu-id="a19cf-138">Configurar varios proyectos</span><span class="sxs-lookup"><span data-stu-id="a19cf-138">Configure multiple projects</span></span>

<span data-ttu-id="a19cf-139">Puede crear un archivo **Directory.Build.props** que contenga el elemento `<LangVersion>` para configurar varios directorios.</span><span class="sxs-lookup"><span data-stu-id="a19cf-139">You can create a **Directory.Build.props** file that contains the `<LangVersion>` element to configure multiple directories.</span></span> <span data-ttu-id="a19cf-140">Por lo general, esto se hace en el directorio de la solución.</span><span class="sxs-lookup"><span data-stu-id="a19cf-140">You typically do that in your solution directory.</span></span> <span data-ttu-id="a19cf-141">Agregue lo siguiente a un archivo **Directory.Build.props** en el directorio de la solución:</span><span class="sxs-lookup"><span data-stu-id="a19cf-141">Add the following to a **Directory.Build.props** file in your solution directory:</span></span>

```xml
<Project>
 <PropertyGroup>
   <LangVersion>preview</LangVersion>
 </PropertyGroup>
</Project>
```

<span data-ttu-id="a19cf-142">Ahora, las compilaciones de cada subdirectorio del directorio que contenga ese archivo usarán la sintaxis de la versión preliminar de C#.</span><span class="sxs-lookup"><span data-stu-id="a19cf-142">Now, builds in every subdirectory of the directory containing that file will use the preview C# version.</span></span> <span data-ttu-id="a19cf-143">Para obtener más información, consulte el artículo [Personalizar una compilación](/visualstudio/msbuild/customize-your-build).</span><span class="sxs-lookup"><span data-stu-id="a19cf-143">For more information, see the article on [Customize your build](/visualstudio/msbuild/customize-your-build).</span></span>

## <a name="c-language-version-reference"></a><span data-ttu-id="a19cf-144">Referencia de la versión del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="a19cf-144">C# language version reference</span></span>

<span data-ttu-id="a19cf-145">En la siguiente tabla se muestran las versiones actuales del lenguaje C#.</span><span class="sxs-lookup"><span data-stu-id="a19cf-145">The following table shows all current C# language versions.</span></span> <span data-ttu-id="a19cf-146">El compilador no entenderá necesariamente todos los valores si es más antiguo.</span><span class="sxs-lookup"><span data-stu-id="a19cf-146">Your compiler may not necessarily understand every value if it is older.</span></span> <span data-ttu-id="a19cf-147">Si instala .NET Core 3.0, tendrá acceso a todo lo que aparece.</span><span class="sxs-lookup"><span data-stu-id="a19cf-147">If you install .NET Core 3.0, then you will have access to everything listed.</span></span>

|<span data-ttu-id="a19cf-148">Valor</span><span class="sxs-lookup"><span data-stu-id="a19cf-148">Value</span></span>|<span data-ttu-id="a19cf-149">Significado</span><span class="sxs-lookup"><span data-stu-id="a19cf-149">Meaning</span></span>|
|------------|-------------|
|<span data-ttu-id="a19cf-150">preview</span><span class="sxs-lookup"><span data-stu-id="a19cf-150">preview</span></span>|<span data-ttu-id="a19cf-151">El compilador acepta toda la sintaxis de lenguaje válida de la última versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="a19cf-151">The compiler accepts all valid language syntax from the latest preview version.</span></span>|
|<span data-ttu-id="a19cf-152">latest</span><span class="sxs-lookup"><span data-stu-id="a19cf-152">latest</span></span>|<span data-ttu-id="a19cf-153">El compilador acepta la sintaxis de la última versión del compilador (incluida las versión secundaria).</span><span class="sxs-lookup"><span data-stu-id="a19cf-153">The compiler accepts syntax from the latest released version of the compiler (including minor version).</span></span>|
|<span data-ttu-id="a19cf-154">latestMajor</span><span class="sxs-lookup"><span data-stu-id="a19cf-154">latestMajor</span></span>|<span data-ttu-id="a19cf-155">El compilador acepta la sintaxis de la versión principal más reciente del compilador.</span><span class="sxs-lookup"><span data-stu-id="a19cf-155">The compiler accepts syntax from the latest released major version of the compiler.</span></span>|
|<span data-ttu-id="a19cf-156">8.0</span><span class="sxs-lookup"><span data-stu-id="a19cf-156">8.0</span></span>|<span data-ttu-id="a19cf-157">El compilador acepta solo la sintaxis que se incluye en C# 8.0 o versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="a19cf-157">The compiler accepts only syntax that is included in C# 8.0 or lower.</span></span>|
|<span data-ttu-id="a19cf-158">7.3</span><span class="sxs-lookup"><span data-stu-id="a19cf-158">7.3</span></span>|<span data-ttu-id="a19cf-159">El compilador acepta solo la sintaxis que se incluye en C# 7.3 o versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="a19cf-159">The compiler accepts only syntax that is included in C# 7.3 or lower.</span></span>|
|<span data-ttu-id="a19cf-160">7.2</span><span class="sxs-lookup"><span data-stu-id="a19cf-160">7.2</span></span>|<span data-ttu-id="a19cf-161">El compilador acepta solo la sintaxis que se incluye en C# 7.2 o versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="a19cf-161">The compiler accepts only syntax that is included in C# 7.2 or lower.</span></span>|
|<span data-ttu-id="a19cf-162">7.1</span><span class="sxs-lookup"><span data-stu-id="a19cf-162">7.1</span></span>|<span data-ttu-id="a19cf-163">El compilador acepta solo la sintaxis que se incluye en C# 7.1 o versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="a19cf-163">The compiler accepts only syntax that is included in C# 7.1 or lower.</span></span>|
|<span data-ttu-id="a19cf-164">7</span><span class="sxs-lookup"><span data-stu-id="a19cf-164">7</span></span>|<span data-ttu-id="a19cf-165">El compilador acepta solo la sintaxis que se incluye en C# 7.0 o versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="a19cf-165">The compiler accepts only syntax that is included in C# 7.0 or lower.</span></span>|
|<span data-ttu-id="a19cf-166">6</span><span class="sxs-lookup"><span data-stu-id="a19cf-166">6</span></span>|<span data-ttu-id="a19cf-167">El compilador acepta solo la sintaxis que se incluye en C# 6.0 o versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="a19cf-167">The compiler accepts only syntax that is included in C# 6.0 or lower.</span></span>|
|<span data-ttu-id="a19cf-168">5</span><span class="sxs-lookup"><span data-stu-id="a19cf-168">5</span></span>|<span data-ttu-id="a19cf-169">El compilador acepta solo la sintaxis que se incluye en C# 5.0 o versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="a19cf-169">The compiler accepts only syntax that is included in C# 5.0 or lower.</span></span>|
|<span data-ttu-id="a19cf-170">4</span><span class="sxs-lookup"><span data-stu-id="a19cf-170">4</span></span>|<span data-ttu-id="a19cf-171">El compilador acepta solo la sintaxis que se incluye en C# 4.0 o versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="a19cf-171">The compiler accepts only syntax that is included in C# 4.0 or lower.</span></span>|
|<span data-ttu-id="a19cf-172">3</span><span class="sxs-lookup"><span data-stu-id="a19cf-172">3</span></span>|<span data-ttu-id="a19cf-173">El compilador acepta solo la sintaxis que se incluye en C# 3.0 o versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="a19cf-173">The compiler accepts only syntax that is included in C# 3.0 or lower.</span></span>|
|<span data-ttu-id="a19cf-174">ISO-2</span><span class="sxs-lookup"><span data-stu-id="a19cf-174">ISO-2</span></span>|<span data-ttu-id="a19cf-175">El compilador acepta solo la sintaxis que se incluye en ISO/IEC 23270:2006 C# (2.0)</span><span class="sxs-lookup"><span data-stu-id="a19cf-175">The compiler accepts only syntax that is included in ISO/IEC 23270:2006 C# (2.0)</span></span> |
|<span data-ttu-id="a19cf-176">ISO-1</span><span class="sxs-lookup"><span data-stu-id="a19cf-176">ISO-1</span></span>|<span data-ttu-id="a19cf-177">El compilador acepta solo la sintaxis que se incluye en ISO/IEC 23270:2003 C# (1.0/1.2)</span><span class="sxs-lookup"><span data-stu-id="a19cf-177">The compiler accepts only syntax that is included in ISO/IEC 23270:2003 C# (1.0/1.2)</span></span> |
