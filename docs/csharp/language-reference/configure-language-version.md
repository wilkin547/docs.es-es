---
title: Seleccionar la versión del lenguaje C# - Guía de C#
description: Configurar el compilador para validar la sintaxis con una versión específica del compilador
ms.date: 05/24/2018
ms.openlocfilehash: 9b91e62168ced0f373e1a55def8b279dc64833d8
ms.sourcegitcommit: 6bc4efca63e526ce6f2d257fa870f01f8c459ae4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "36208091"
---
# <a name="select-the-c-language-version"></a><span data-ttu-id="a03a0-103">Seleccionar la versión del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="a03a0-103">Select the C# language version</span></span>

<span data-ttu-id="a03a0-104">El compilador de C# tiene como valor predeterminado la última versión principal del lenguaje que se haya publicado.</span><span class="sxs-lookup"><span data-stu-id="a03a0-104">The C# compiler defaults to the latest major version of the language that has been released.</span></span> <span data-ttu-id="a03a0-105">Puede elegir compilar cualquier proyecto con una versión nueva del lenguaje.</span><span class="sxs-lookup"><span data-stu-id="a03a0-105">You may choose to compile any project using a new point release of the language.</span></span> <span data-ttu-id="a03a0-106">Elegir la versión más reciente del lenguaje permite que el proyecto use las últimas características de ese lenguaje.</span><span class="sxs-lookup"><span data-stu-id="a03a0-106">Choosing a newer version of the language enables your project to make use of the latest language features.</span></span> <span data-ttu-id="a03a0-107">En otros escenarios, puede ser necesario validar que un proyecto se compile correctamente cuando se usa una versión anterior del lenguaje.</span><span class="sxs-lookup"><span data-stu-id="a03a0-107">In other scenarios, you may need to validate that a project compiles cleanly when using an older version of the language.</span></span>

<span data-ttu-id="a03a0-108">Esta capacidad hace que la decisión de instalar nuevas versiones del SDK y las herramientas en el entorno de desarrollo no esté vinculada a la decisión de incorporar nuevas características del lenguaje en un proyecto.</span><span class="sxs-lookup"><span data-stu-id="a03a0-108">This capability decouples the decision to install new versions of the SDK and tools in your development environment from the decision to incorporate new language features in a project.</span></span> <span data-ttu-id="a03a0-109">Puede instalar el SDK y las herramientas más recientes en el equipo de compilación.</span><span class="sxs-lookup"><span data-stu-id="a03a0-109">You can install the latest SDK and tools on your build machine.</span></span> <span data-ttu-id="a03a0-110">Cada proyecto se puede configurar para que, durante su compilación, se use una versión de lenguaje específica.</span><span class="sxs-lookup"><span data-stu-id="a03a0-110">Each project can be configured to use a specific version of the language for its build.</span></span>

<span data-ttu-id="a03a0-111">Hay varias maneras de establecer la versión de idioma:</span><span class="sxs-lookup"><span data-stu-id="a03a0-111">There are several ways to set the language version:</span></span>

- <span data-ttu-id="a03a0-112">Basarse en una [acción rápida de Visual Studio](#visual-studio-quick-action).</span><span class="sxs-lookup"><span data-stu-id="a03a0-112">Rely on a [Visual Studio quick action](#visual-studio-quick-action).</span></span>
- <span data-ttu-id="a03a0-113">Establecer la versión del lenguaje en la [interfaz de usuario de Visual Studio](#set-the-language-version-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="a03a0-113">Set the language version in the [Visual Studio UI](#set-the-language-version-in-visual-studio).</span></span>
- <span data-ttu-id="a03a0-114">Editar manualmente el archivo [**.csproj** ](#edit-the-csproj-file).</span><span class="sxs-lookup"><span data-stu-id="a03a0-114">Manually edit your [**.csproj** file](#edit-the-csproj-file).</span></span>
- <span data-ttu-id="a03a0-115">Establecer la versión del lenguaje [para varios proyectos en un subdirectorio](#configure-multiple-projects).</span><span class="sxs-lookup"><span data-stu-id="a03a0-115">Set the language version [for multiple projects in a subdirectory](#configure-multiple-projects).</span></span>
- <span data-ttu-id="a03a0-116">Configurar la opción dl compilador [Reemplace la opción del compilador `-langversion`](#set-the-langversion-compiler-option).</span><span class="sxs-lookup"><span data-stu-id="a03a0-116">Configure the [`-langversion` compiler option](#set-the-langversion-compiler-option).</span></span>

## <a name="visual-studio-quick-action"></a><span data-ttu-id="a03a0-117">Acción rápida de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a03a0-117">Visual Studio quick action</span></span>

<span data-ttu-id="a03a0-118">Visual Studio le ayuda a determinar la versión de idioma que necesita.</span><span class="sxs-lookup"><span data-stu-id="a03a0-118">Visual Studio helps you determine the language version you need.</span></span> <span data-ttu-id="a03a0-119">Si usa una característica del lenguaje que no está disponible para la versión configurada actualmente, Visual Studio le propone una solución para actualizar la versión de lenguaje del proyecto.</span><span class="sxs-lookup"><span data-stu-id="a03a0-119">If you use a language feature that is not available for the currently configured version, Visual Studio shows a potential fix to update the language version for the project.</span></span>

## <a name="set-the-language-version-in-visual-studio"></a><span data-ttu-id="a03a0-120">Establecer la versión de idioma en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a03a0-120">Set the language version in Visual Studio</span></span>

<span data-ttu-id="a03a0-121">Puede establecer la versión de idioma en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a03a0-121">You can set the version in Visual Studio.</span></span> <span data-ttu-id="a03a0-122">En el Explorador de soluciones, haga clic con el botón derecho en el nodo del proyecto y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="a03a0-122">Right-click on the project node in Solution Explorer and select **Properties**.</span></span> <span data-ttu-id="a03a0-123">Seleccione la pestaña **Compilar** y, después, el botón **Opciones avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="a03a0-123">Select the **Build** tab and select the **Advanced** button.</span></span> <span data-ttu-id="a03a0-124">En la lista desplegable, seleccione la versión.</span><span class="sxs-lookup"><span data-stu-id="a03a0-124">In the dropdown, select the version.</span></span> <span data-ttu-id="a03a0-125">La siguiente imagen muestra el valor "más reciente":</span><span class="sxs-lookup"><span data-stu-id="a03a0-125">The following image shows the "latest" setting:</span></span>

![Captura de pantalla de la configuración de compilación avanzada en la que se puede especificar la versión del lenguaje](./media/configure-language-version/advanced-build-settings.png)

> [!NOTE]
> <span data-ttu-id="a03a0-127">Si usa el IDE de Visual Studio para actualizar los archivos csproj, este creará nodos independientes por cada configuración de compilación existente.</span><span class="sxs-lookup"><span data-stu-id="a03a0-127">If you use the Visual Studio IDE to update your csproj files, the IDE creates separate nodes for each build configuration.</span></span> <span data-ttu-id="a03a0-128">Normalmente, se establece el mismo valor en todas las configuraciones de compilación, pero deberá establecerse de forma explícita en cada configuración de compilación, o bien seleccionar "All Configurations" (Todas las configuraciones) cuando este valor se modifique.</span><span class="sxs-lookup"><span data-stu-id="a03a0-128">You'll typically set the value the same in all build configurations, but you need to set it explicitly for each build configuration, or select "All Configurations" when you modify this setting.</span></span> <span data-ttu-id="a03a0-129">Verá lo siguiente en el archivo csproj:</span><span class="sxs-lookup"><span data-stu-id="a03a0-129">You'll see the following in your csproj file:</span></span>
>
>```xml
> <PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Release|AnyCPU'">
>  <LangVersion>latest</LangVersion>
></PropertyGroup>
>
> <PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Debug|AnyCPU'">
>  <LangVersion>latest</LangVersion>
> </PropertyGroup>
> ```
>

## <a name="edit-the-csproj-file"></a><span data-ttu-id="a03a0-130">Editar el archivo csproj</span><span class="sxs-lookup"><span data-stu-id="a03a0-130">Edit the csproj file</span></span>

<span data-ttu-id="a03a0-131">Puede establecer la versión del lenguaje en el archivo **.csproj**.</span><span class="sxs-lookup"><span data-stu-id="a03a0-131">You can set the language version in your **.csproj** file.</span></span> <span data-ttu-id="a03a0-132">Agregue un elemento similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="a03a0-132">Add an element like the following:</span></span>

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="a03a0-133">El valor `latest` usa la versión secundaria más reciente del lenguaje C#.</span><span class="sxs-lookup"><span data-stu-id="a03a0-133">The value `latest` uses the latest minor version of the C# language.</span></span> <span data-ttu-id="a03a0-134">Los valores válidos son:</span><span class="sxs-lookup"><span data-stu-id="a03a0-134">Valid values are:</span></span>

|<span data-ttu-id="a03a0-135">Valor</span><span class="sxs-lookup"><span data-stu-id="a03a0-135">Value</span></span>|<span data-ttu-id="a03a0-136">Significado</span><span class="sxs-lookup"><span data-stu-id="a03a0-136">Meaning</span></span>|
|------------|-------------|
|<span data-ttu-id="a03a0-137">default</span><span class="sxs-lookup"><span data-stu-id="a03a0-137">default</span></span>|<span data-ttu-id="a03a0-138">El compilador acepta toda la sintaxis de lenguaje válida de la última versión principal que puede admitir.</span><span class="sxs-lookup"><span data-stu-id="a03a0-138">The compiler accepts all valid language syntax from the latest major version that it can support.</span></span>|
|<span data-ttu-id="a03a0-139">ISO-1</span><span class="sxs-lookup"><span data-stu-id="a03a0-139">ISO-1</span></span>|<span data-ttu-id="a03a0-140">El compilador acepta solo la sintaxis que se incluye en ISO/IEC 23270:2003 C# (1.0/1.2)</span><span class="sxs-lookup"><span data-stu-id="a03a0-140">The compiler accepts only syntax that is included in ISO/IEC 23270:2003 C# (1.0/1.2)</span></span> |
|<span data-ttu-id="a03a0-141">ISO-2</span><span class="sxs-lookup"><span data-stu-id="a03a0-141">ISO-2</span></span>|<span data-ttu-id="a03a0-142">El compilador acepta solo la sintaxis que se incluye en ISO/IEC 23270:2006 C# (2.0)</span><span class="sxs-lookup"><span data-stu-id="a03a0-142">The compiler accepts only syntax that is included in ISO/IEC 23270:2006 C# (2.0)</span></span> |
|<span data-ttu-id="a03a0-143">3</span><span class="sxs-lookup"><span data-stu-id="a03a0-143">3</span></span>|<span data-ttu-id="a03a0-144">El compilador acepta solo la sintaxis que se incluye en C# 3.0 o versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="a03a0-144">The compiler accepts only syntax that is included in C# 3.0 or lower.</span></span>|
|<span data-ttu-id="a03a0-145">4</span><span class="sxs-lookup"><span data-stu-id="a03a0-145">4</span></span>|<span data-ttu-id="a03a0-146">El compilador acepta solo la sintaxis que se incluye en C# 4.0 o versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="a03a0-146">The compiler accepts only syntax that is included in C# 4.0 or lower.</span></span>|
|<span data-ttu-id="a03a0-147">5</span><span class="sxs-lookup"><span data-stu-id="a03a0-147">5</span></span>|<span data-ttu-id="a03a0-148">El compilador acepta solo la sintaxis que se incluye en C# 5.0 o versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="a03a0-148">The compiler accepts only syntax that is included in C# 5.0 or lower.</span></span>|
|<span data-ttu-id="a03a0-149">6</span><span class="sxs-lookup"><span data-stu-id="a03a0-149">6</span></span>|<span data-ttu-id="a03a0-150">El compilador acepta solo la sintaxis que se incluye en C# 6.0 o versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="a03a0-150">The compiler accepts only syntax that is included in C# 6.0 or lower.</span></span>|
|<span data-ttu-id="a03a0-151">7</span><span class="sxs-lookup"><span data-stu-id="a03a0-151">7</span></span>|<span data-ttu-id="a03a0-152">El compilador acepta solo la sintaxis que se incluye en C# 7.0 o versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="a03a0-152">The compiler accepts only syntax that is included in C# 7.0 or lower.</span></span>|
|<span data-ttu-id="a03a0-153">7.1</span><span class="sxs-lookup"><span data-stu-id="a03a0-153">7.1</span></span>|<span data-ttu-id="a03a0-154">El compilador acepta solo la sintaxis que se incluye en C# 7.1 o versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="a03a0-154">The compiler accepts only syntax that is included in C# 7.1 or lower.</span></span>|
|<span data-ttu-id="a03a0-155">7.2</span><span class="sxs-lookup"><span data-stu-id="a03a0-155">7.2</span></span>|<span data-ttu-id="a03a0-156">El compilador acepta solo la sintaxis que se incluye en C# 7.2 o versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="a03a0-156">The compiler accepts only syntax that is included in C# 7.2 or lower.</span></span>|
|<span data-ttu-id="a03a0-157">7.3</span><span class="sxs-lookup"><span data-stu-id="a03a0-157">7.3</span></span>|<span data-ttu-id="a03a0-158">El compilador acepta solo la sintaxis que se incluye en C# 7.3 o versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="a03a0-158">The compiler accepts only syntax that is included in C# 7.3 or lower.</span></span>|
|<span data-ttu-id="a03a0-159">latest</span><span class="sxs-lookup"><span data-stu-id="a03a0-159">latest</span></span>|<span data-ttu-id="a03a0-160">El compilador acepta toda la sintaxis de lenguaje válida que puede admitir.</span><span class="sxs-lookup"><span data-stu-id="a03a0-160">The compiler accepts all valid language syntax that it can support.</span></span>|

<span data-ttu-id="a03a0-161">Las cadenas especiales `default` y `latest` se resuelven en las versiones de lenguaje principal (C# 7.0) y secundaria (C# 7.3) respectivamente más recientes que haya instaladas en el equipo de compilación.</span><span class="sxs-lookup"><span data-stu-id="a03a0-161">The special strings `default` and `latest` resolve to the latest major (C# 7.0) and minor (C# 7.3) language versions installed on the build machine, respectively.</span></span>

## <a name="configure-multiple-projects"></a><span data-ttu-id="a03a0-162">Configurar varios proyectos</span><span class="sxs-lookup"><span data-stu-id="a03a0-162">Configure multiple projects</span></span>

<span data-ttu-id="a03a0-163">Puede crear un archivo **Directory.build.props** que contenga el elemento `<LangVersion>` para configurar varios directorios.</span><span class="sxs-lookup"><span data-stu-id="a03a0-163">You can create a **Directory.build.props** file that contains the `<LangVersion>` element to configure multiple directories.</span></span> <span data-ttu-id="a03a0-164">Por lo general, esto se hace en el directorio de la solución.</span><span class="sxs-lookup"><span data-stu-id="a03a0-164">You typically do that in your solution directory.</span></span> <span data-ttu-id="a03a0-165">Agregue lo siguiente a un archivo **Directory.build.props** en el directorio de la solución:</span><span class="sxs-lookup"><span data-stu-id="a03a0-165">Add the following to a **Directory.build.props** file in your solution directory:</span></span>

```xml
<Project>
 <PropertyGroup>
   <LangVersion>7.3</LangVersion>
 </PropertyGroup>
</Project>
```

<span data-ttu-id="a03a0-166">Ahora, las compilaciones de cada subdirectorio del directorio que contenga ese archivo usarán la sintaxis de la versión 7.3 de C#.</span><span class="sxs-lookup"><span data-stu-id="a03a0-166">Now, builds in every subdirectory of the directory containing that file will use C# version 7.3 syntax.</span></span> <span data-ttu-id="a03a0-167">Para obtener más información, consulte el artículo [Personalizar una compilación](/visualstudio/msbuild/customize-your-build).</span><span class="sxs-lookup"><span data-stu-id="a03a0-167">For more information, see the article on [Customize your build](/visualstudio/msbuild/customize-your-build).</span></span>

## <a name="set-the-langversion-compiler-option"></a><span data-ttu-id="a03a0-168">Establecer la opción del compilador langversion</span><span class="sxs-lookup"><span data-stu-id="a03a0-168">Set the langversion compiler option</span></span>

<span data-ttu-id="a03a0-169">Puede usar la opción de la línea de comandos `-langversion`.</span><span class="sxs-lookup"><span data-stu-id="a03a0-169">You can use the `-langversion` command-line option.</span></span> <span data-ttu-id="a03a0-170">Para obtener más información, consulte el artículo sobre la opción del compilador [-langversion](../language-reference/compiler-options/langversion-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="a03a0-170">For more information, see the article on the [-langversion](../language-reference/compiler-options/langversion-compiler-option.md) compiler option.</span></span> <span data-ttu-id="a03a0-171">Para ver una lista de los valores válidos, escriba `csc -langversion:?`.</span><span class="sxs-lookup"><span data-stu-id="a03a0-171">You can see a list of the valid values by typing  `csc -langversion:?`.</span></span>
