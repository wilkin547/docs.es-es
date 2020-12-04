---
title: Archivos de configuración para las reglas de análisis de código
description: Obtenga información sobre los distintos archivos de configuración para configurar reglas de análisis de código.
ms.date: 09/24/2020
ms.topic: conceptual
no-loc:
- EditorConfig
ms.openlocfilehash: cf9b8f4033e6774684b2b7e3b788ef3c157d95df
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96594727"
---
# <a name="configuration-files-for-code-analysis-rules"></a><span data-ttu-id="0f8d8-103">Archivos de configuración para las reglas de análisis de código</span><span class="sxs-lookup"><span data-stu-id="0f8d8-103">Configuration files for code analysis rules</span></span>

<span data-ttu-id="0f8d8-104">Las reglas de análisis de código tienen varias [Opciones de configuración](configuration-options.md).</span><span class="sxs-lookup"><span data-stu-id="0f8d8-104">Code analysis rules have various [configuration options](configuration-options.md).</span></span> <span data-ttu-id="0f8d8-105">Estas opciones se especifican como pares clave-valor en uno de los siguientes archivos de configuración del analizador:</span><span class="sxs-lookup"><span data-stu-id="0f8d8-105">You specify these options as key-value pairs in one of the following analyzer configuration files:</span></span>

- <span data-ttu-id="0f8d8-106">[EditorConfig](#editorconfig) archivo: opciones de configuración basadas en archivos o carpetas.</span><span class="sxs-lookup"><span data-stu-id="0f8d8-106">[EditorConfig](#editorconfig) file: File-based or folder-based configuration options.</span></span>
- <span data-ttu-id="0f8d8-107">Archivo [AnalyzerConfig global](#global-analyzerconfig) : opciones de configuración de nivel de proyecto.</span><span class="sxs-lookup"><span data-stu-id="0f8d8-107">[Global AnalyzerConfig](#global-analyzerconfig) file: Project-level configuration options.</span></span>

## EditorConfig

<span data-ttu-id="0f8d8-108">[EditorConfig](/visualstudio/ide/create-portable-custom-editor-options) los archivos se usan para proporcionar **opciones que se aplican a archivos o carpetas de origen específicos**.</span><span class="sxs-lookup"><span data-stu-id="0f8d8-108">[EditorConfig](/visualstudio/ide/create-portable-custom-editor-options) files are used to provide **options that apply to specific source files or folders**.</span></span> <span data-ttu-id="0f8d8-109">Las opciones se colocan en encabezados de sección para identificar los archivos y carpetas aplicables.</span><span class="sxs-lookup"><span data-stu-id="0f8d8-109">Options are placed under section headers to identify the applicable files and folders.</span></span> <span data-ttu-id="0f8d8-110">Agregue una entrada para cada regla que desee configurar y colóquela en la sección de la extensión de archivo correspondiente, por ejemplo, `[*.cs]` .</span><span class="sxs-lookup"><span data-stu-id="0f8d8-110">Add an entry for each rule you want to configure, and place it under the corresponding file extension section, for example, `[*.cs]`.</span></span>

```ini
[*.cs]
<option_name> = <option_value>
```

<span data-ttu-id="0f8d8-111">En el ejemplo anterior, `[*.cs]` es un encabezado de sección editorconfig para seleccionar todos los archivos de C# con `.cs` extensión de archivo dentro de la carpeta actual, incluidas las subcarpetas.</span><span class="sxs-lookup"><span data-stu-id="0f8d8-111">In the above example, `[*.cs]` is an editorconfig section header to select all C# files with `.cs` file extension within the current folder, including subfolders.</span></span> <span data-ttu-id="0f8d8-112">La entrada siguiente, `<option_name> = <option_value>` , es una opción del analizador que se aplicará a todos los archivos de C#.</span><span class="sxs-lookup"><span data-stu-id="0f8d8-112">The subsequent entry, `<option_name> = <option_value>`, is an analyzer option that will be applied to all the C# files.</span></span>

<span data-ttu-id="0f8d8-113">Puede aplicar EditorConfig las convenciones de archivo a una carpeta, un proyecto o un repositorio completo colocando el archivo en el directorio correspondiente.</span><span class="sxs-lookup"><span data-stu-id="0f8d8-113">You can apply EditorConfig file conventions to a folder, a project, or an entire repo by placing the file in the corresponding directory.</span></span> <span data-ttu-id="0f8d8-114">Estas opciones se aplican al ejecutar el análisis en tiempo de compilación y mientras edita código en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0f8d8-114">These options are applied when executing the analysis at build time and while you edit code in Visual Studio.</span></span>

<span data-ttu-id="0f8d8-115">Si tiene un archivo *. editorconfig* existente para la configuración del editor, como el tamaño de sangría o si desea recortar el espacio en blanco final, puede colocar las opciones de configuración de análisis de código en el mismo archivo.</span><span class="sxs-lookup"><span data-stu-id="0f8d8-115">If you have an existing *.editorconfig* file for editor settings such as indent size or whether to trim trailing whitespace, you can place your code analysis configuration options in the same file.</span></span>

> [!TIP]
> <span data-ttu-id="0f8d8-116">Visual Studio proporciona una plantilla de elemento *. editorconfig* que facilita la tarea de agregar uno de estos archivos al proyecto.</span><span class="sxs-lookup"><span data-stu-id="0f8d8-116">Visual Studio provides an *.editorconfig* item template that makes is easy to add one of these files to your project.</span></span> <span data-ttu-id="0f8d8-117">Para obtener más información, vea [Agregar un EditorConfig archivo a un proyecto](/visualstudio/ide/create-portable-custom-editor-options#add-an-editorconfig-file-to-a-project).</span><span class="sxs-lookup"><span data-stu-id="0f8d8-117">For more information, see [Add an EditorConfig file to a project](/visualstudio/ide/create-portable-custom-editor-options#add-an-editorconfig-file-to-a-project).</span></span>

### <a name="example"></a><span data-ttu-id="0f8d8-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0f8d8-118">Example</span></span>

<span data-ttu-id="0f8d8-119">A continuación se encuentra un EditorConfig archivo de ejemplo para configurar las opciones y la gravedad de la regla:</span><span class="sxs-lookup"><span data-stu-id="0f8d8-119">Following is an example EditorConfig file to configure options and rule severity:</span></span>

```ini
# Remove the line below if you want to inherit .editorconfig settings from higher directories
root = true

# C# files
[*.cs]

#### Core EditorConfig Options ####

# Indentation and spacing
indent_size = 4
indent_style = space
tab_width = 4

#### .NET Coding Conventions ####

# this. and Me. preferences
dotnet_style_qualification_for_method = true:warning

#### Diagnostic configuration ####

# CA1000: Do not declare static members on generic types
dotnet_diagnostic.CA1000.severity = warning
```

## <a name="global-analyzerconfig"></a><span data-ttu-id="0f8d8-120">AnalyzerConfig global</span><span class="sxs-lookup"><span data-stu-id="0f8d8-120">Global AnalyzerConfig</span></span>

<span data-ttu-id="0f8d8-121">A partir del SDK de .NET 5,0 (que es compatible con la versión 16,8 de Visual Studio 2019 y versiones posteriores), también puede configurar las opciones del analizador con archivos _AnalyzerConfig_ globales.</span><span class="sxs-lookup"><span data-stu-id="0f8d8-121">Starting with the .NET 5.0 SDK (which is supported in Visual Studio 2019 version 16.8 and later versions), you can also configure analyzer options with global _AnalyzerConfig_ files.</span></span> <span data-ttu-id="0f8d8-122">Estos archivos se usan para proporcionar **las opciones que se aplican a todos los archivos de origen de un proyecto**, independientemente de sus nombres de archivo o rutas de acceso de archivo.</span><span class="sxs-lookup"><span data-stu-id="0f8d8-122">These files are used to provide **options that apply to all the source files in a project**, regardless of their file names or file paths.</span></span>

<span data-ttu-id="0f8d8-123">A diferencia [EditorConfig](#editorconfig) de los archivos, los archivos de configuración global no se pueden usar para configurar los valores de estilo de editor para IDE, como el tamaño de sangría o si se debe recortar el espacio en blanco final.</span><span class="sxs-lookup"><span data-stu-id="0f8d8-123">Unlike [EditorConfig](#editorconfig) files, global config files can't be used to configure editor style settings for IDEs, such as indent size or whether to trim trailing whitespace.</span></span> <span data-ttu-id="0f8d8-124">En su lugar, están diseñados exclusivamente para especificar las opciones de configuración del analizador de nivel de proyecto.</span><span class="sxs-lookup"><span data-stu-id="0f8d8-124">Instead, they are designed purely for specifying project-level analyzer configuration options.</span></span>

### <a name="format"></a><span data-ttu-id="0f8d8-125">Formato</span><span class="sxs-lookup"><span data-stu-id="0f8d8-125">Format</span></span>

<span data-ttu-id="0f8d8-126">A diferencia EditorConfig de los archivos, que deben tener encabezados de sección, como `[*.cs]` , para identificar los archivos y carpetas aplicables, los archivos AnalyzerConfig globales no tienen encabezados de sección.</span><span class="sxs-lookup"><span data-stu-id="0f8d8-126">Unlike EditorConfig files, which must have section headers, such as `[*.cs]`, to identify the applicable files and folders, global AnalyzerConfig files don't have section headers.</span></span> <span data-ttu-id="0f8d8-127">En su lugar, requieren una entrada de nivel superior del formulario `is_global = true` para diferenciarlos de EditorConfig los archivos normales.</span><span class="sxs-lookup"><span data-stu-id="0f8d8-127">Instead, they require a top level entry of the form `is_global = true` to differentiate them from regular EditorConfig files.</span></span> <span data-ttu-id="0f8d8-128">Esto indica que todas las opciones del archivo se aplican a todo el proyecto.</span><span class="sxs-lookup"><span data-stu-id="0f8d8-128">This indicates that all the options in the file apply to the entire project.</span></span> <span data-ttu-id="0f8d8-129">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0f8d8-129">For example:</span></span>

```ini
is_global = true
<option_name> = <option_value>
```

### <a name="naming"></a><span data-ttu-id="0f8d8-130">Nomenclatura</span><span class="sxs-lookup"><span data-stu-id="0f8d8-130">Naming</span></span>

<span data-ttu-id="0f8d8-131">A diferencia de EditorConfig los archivos, que se deben denominar `.editorconfig` , los archivos de configuración global no necesitan tener un nombre o una extensión específicos.</span><span class="sxs-lookup"><span data-stu-id="0f8d8-131">Unlike EditorConfig files, which must be named `.editorconfig`, global config files do not need to have a specific name or extension.</span></span> <span data-ttu-id="0f8d8-132">Sin embargo, si asigna un nombre a estos archivos como `.globalconfig` , se aplicarán implícitamente a todos los proyectos de C# y Visual Basic dentro de la carpeta actual, incluidas las subcarpetas.</span><span class="sxs-lookup"><span data-stu-id="0f8d8-132">However, if you name these files as `.globalconfig` then they will be implicitly applied to all the C# and Visual Basic projects within the current folder, including subfolders.</span></span> <span data-ttu-id="0f8d8-133">De lo contrario, debe agregar explícitamente el `GlobalAnalyzerConfigFiles` elemento al archivo de proyecto de MSBuild:</span><span class="sxs-lookup"><span data-stu-id="0f8d8-133">Otherwise, you must explicitly add the `GlobalAnalyzerConfigFiles` item to your MSBuild project file:</span></span>

```xml
<ItemGroup>
  <GlobalAnalyzerConfigFiles Include="<path_to_global_analyzer_config>" />
</ItemGroup>
```

> [!NOTE]
> <span data-ttu-id="0f8d8-134">La entrada de nivel superior `is_global = true` es necesaria incluso cuando el archivo se denomina `.globalconfig` .</span><span class="sxs-lookup"><span data-stu-id="0f8d8-134">The top-level entry `is_global = true` is required even when the file is named `.globalconfig`.</span></span>

### <a name="example"></a><span data-ttu-id="0f8d8-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0f8d8-135">Example</span></span>

<span data-ttu-id="0f8d8-136">A continuación se encuentra un archivo AnalyzerConfig global de ejemplo para configurar las opciones y la gravedad de la regla en el nivel de proyecto:</span><span class="sxs-lookup"><span data-stu-id="0f8d8-136">Following is an example global AnalyzerConfig file to configure options and rule severity at the project level:</span></span>

```ini
# Top level entry required to mark this as a global AnalyzerConfig file
is_global = true

# NOTE: No section headers for configuration entries

#### .NET Coding Conventions ####

# this. and Me. preferences
dotnet_style_qualification_for_method = true:warning

#### Diagnostic configuration ####

# CA1000: Do not declare static members on generic types
dotnet_diagnostic.CA1000.severity = warning
```

## <a name="precedence"></a><span data-ttu-id="0f8d8-137">Prioridad</span><span class="sxs-lookup"><span data-stu-id="0f8d8-137">Precedence</span></span>

<span data-ttu-id="0f8d8-138">Tanto archivos EditorConfig como archivos AnalyzerConfig globales especifican un par clave-valor para cada opción.</span><span class="sxs-lookup"><span data-stu-id="0f8d8-138">Both EditorConfig files and global AnalyzerConfig files specify a key-value pair for each option.</span></span> <span data-ttu-id="0f8d8-139">Se producen conflictos cuando hay varias entradas con la misma clave pero con distintos valores.</span><span class="sxs-lookup"><span data-stu-id="0f8d8-139">Conflicts arise when there are multiple entries with the same key but different values.</span></span>

### <a name="general-options"></a><span data-ttu-id="0f8d8-140">Opciones generales</span><span class="sxs-lookup"><span data-stu-id="0f8d8-140">General options</span></span>

<span data-ttu-id="0f8d8-141">Cuando surgen conflictos entre las opciones, se usan las siguientes reglas de prioridad para resolver los conflictos:</span><span class="sxs-lookup"><span data-stu-id="0f8d8-141">When conflicts arise between options, the following precedence rules are used to resolve the conflicts:</span></span>

- <span data-ttu-id="0f8d8-142">Entradas en conflicto en el mismo archivo de configuración: la entrada que aparece más adelante en el archivo gana.</span><span class="sxs-lookup"><span data-stu-id="0f8d8-142">Conflicting entries in the same configuration file: The entry that appears later in the file wins.</span></span> <span data-ttu-id="0f8d8-143">Esto se aplica a las entradas conflictivas dentro de un único EditorConfig archivo y también dentro de un único archivo AnalyzerConfig global.</span><span class="sxs-lookup"><span data-stu-id="0f8d8-143">This is true for conflicting entries within a single EditorConfig file and also within a single global AnalyzerConfig file.</span></span>

- <span data-ttu-id="0f8d8-144">Entradas en conflicto en dos EditorConfig archivos: la entrada en el EditorConfig archivo que es más profunda en el sistema de archivos y, por tanto, tiene una ruta de acceso de archivo más larga, gana.</span><span class="sxs-lookup"><span data-stu-id="0f8d8-144">Conflicting entries in two EditorConfig files: The entry in the EditorConfig file that's deeper in the file system, and hence has a longer file path, wins.</span></span>

- <span data-ttu-id="0f8d8-145">Entradas en conflicto en dos archivos AnalyzerConfig globales: se indica una advertencia del compilador y se omiten ambas entradas.</span><span class="sxs-lookup"><span data-stu-id="0f8d8-145">Conflicting entries in two global AnalyzerConfig files: A compiler warning is reported and both entries are ignored.</span></span>

- <span data-ttu-id="0f8d8-146">Entradas en conflicto en un EditorConfig archivo y un archivo AnalyzerConfig global: la entrada en el EditorConfig archivo gana.</span><span class="sxs-lookup"><span data-stu-id="0f8d8-146">Conflicting entries in an EditorConfig file and a Global AnalyzerConfig file: The entry in the EditorConfig file wins.</span></span>

### <a name="severity-options"></a><span data-ttu-id="0f8d8-147">Opciones de gravedad</span><span class="sxs-lookup"><span data-stu-id="0f8d8-147">Severity options</span></span>

<span data-ttu-id="0f8d8-148">Las [reglas de prioridad general](#general-options) anteriores se aplican a todas las opciones especificadas en los archivos de configuración.</span><span class="sxs-lookup"><span data-stu-id="0f8d8-148">The previous [general precedence rules](#general-options) apply for all options specified in configuration files.</span></span> <span data-ttu-id="0f8d8-149">En el caso de las opciones de [configuración de gravedad](configuration-options.md#severity-level) , se aplican las siguientes reglas de prioridad adicionales:</span><span class="sxs-lookup"><span data-stu-id="0f8d8-149">For [severity configuration](configuration-options.md#severity-level) options, the following additional precedence rules apply:</span></span>

- <span data-ttu-id="0f8d8-150">Las opciones de gravedad especificadas en la línea de comandos como opciones del compilador ( `/nowarn` o `/warnaserror` ) siempre invalidan las opciones de [configuración de gravedad](configuration-options.md#severity-level) especificadas en EditorConfig y archivos AnalyzerConfig globales.</span><span class="sxs-lookup"><span data-stu-id="0f8d8-150">Severity options specified at the command line as compiler options (`/nowarn` or `/warnaserror`) always override [severity configuration](configuration-options.md#severity-level) options specified in EditorConfig and global AnalyzerConfig files.</span></span>

- <span data-ttu-id="0f8d8-151">Las opciones de gravedad también se pueden especificar con un archivo [ruleset](/visualstudio/code-quality/using-rule-sets-to-group-code-analysis-rules) .</span><span class="sxs-lookup"><span data-stu-id="0f8d8-151">Severity options can also be specified with a [Ruleset](/visualstudio/code-quality/using-rule-sets-to-group-code-analysis-rules) file.</span></span> <span data-ttu-id="0f8d8-152">Sin embargo, los archivos de conjuntos de archivos están en desuso en favor de EditorConfig los archivos AnalyzerConfig globales.</span><span class="sxs-lookup"><span data-stu-id="0f8d8-152">However, rulesets files are deprecated in favor of EditorConfig and global AnalyzerConfig files.</span></span> <span data-ttu-id="0f8d8-153">Se recomienda [convertir los archivos ruleset en un EditorConfig archivo equivalente](/visualstudio/code-quality/use-roslyn-analyzers#convert-an-existing-ruleset-file-to-editorconfig-file).</span><span class="sxs-lookup"><span data-stu-id="0f8d8-153">It's recommended that you [convert ruleset files to an equivalent EditorConfig file](/visualstudio/code-quality/use-roslyn-analyzers#convert-an-existing-ruleset-file-to-editorconfig-file).</span></span> <span data-ttu-id="0f8d8-154">Prioridad de las entradas de gravedad conflictivas de un archivo ruleset y de que EditorConfig los archivos AnalyzerConfig globales no estén _definidos_.</span><span class="sxs-lookup"><span data-stu-id="0f8d8-154">Precedence for conflicting severity entries from a ruleset file and EditorConfig or global AnalyzerConfig files is _undefined_.</span></span>

- <span data-ttu-id="0f8d8-155">Para obtener información sobre las reglas de prioridad de las opciones de gravedad relacionadas con claves diferentes, por ejemplo, cuando se especifican diferentes gravedades para una sola regla y para la categoría en la que esta regla se encuentra bajo, vea [Opciones de configuración para el análisis de código](configuration-options.md#precedence).</span><span class="sxs-lookup"><span data-stu-id="0f8d8-155">For information about precedence rules for related severity options with different keys, for example, when different severities are specified for a single rule and for the category that rule falls under, see [Configuration options for code analysis](configuration-options.md#precedence).</span></span>

## <a name="see-also"></a><span data-ttu-id="0f8d8-156">Vea también</span><span class="sxs-lookup"><span data-stu-id="0f8d8-156">See also</span></span>

- [<span data-ttu-id="0f8d8-157">EditorConfig problema de diseño de AnalyzerConfig global de vs</span><span class="sxs-lookup"><span data-stu-id="0f8d8-157">EditorConfig vs global AnalyzerConfig design issue</span></span>](https://github.com/dotnet/roslyn/issues/47707)
