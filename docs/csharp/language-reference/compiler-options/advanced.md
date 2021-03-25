---
description: Opciones avanzadas del compilador de C#. Estas opciones se usan en escenarios avanzados.
title: 'Opciones del compilador de C#: escenarios avanzados'
ms.date: 03/12/2021
f1_keywords:
- cs.build.options
helpviewer_keywords:
- BaseAddress compiler option [C#]
- ChecksumAlgorithm compiler option [C#]
- CodePage compiler option [C#]
- Utf8Output compiler option [C#]
- MainEntryPoint compiler option [C#]
- GenerateFullPaths compiler option [C#]
- FileAlignment compiler option [C#]
- PathMap compiler option [C#]
- PdbFile compiler option [C#]
- ErrorEndLocation compiler option [C#]
- NoStandardLib compiler option [C#]
- PreferredUILang compiler option [C#]
- SubsystemVersion compiler option [C#]
- AdditionalLibPaths compiler option [C#]
- ApplicationConfiguration compiler option [C#]
- ModuleAssemblyName compiler option [C#]
ms.openlocfilehash: 47c84968682e056acdb73805807d907c6bb7c7ee
ms.sourcegitcommit: 1dbe25ff484a02025d5c34146e517c236f7161fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "104652768"
---
# <a name="advanced-c-compiler-options"></a><span data-ttu-id="18ba5-104">Opciones avanzadas del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="18ba5-104">Advanced C# compiler options</span></span>

<span data-ttu-id="18ba5-105">Las opciones siguientes admiten escenarios avanzados.</span><span class="sxs-lookup"><span data-stu-id="18ba5-105">The following options support advanced scenarios.</span></span> <span data-ttu-id="18ba5-106">La nueva sintaxis de MSBuild se muestra en **negrita**.</span><span class="sxs-lookup"><span data-stu-id="18ba5-106">The new MSBuild syntax is shown in **Bold**.</span></span> <span data-ttu-id="18ba5-107">La sintaxis de `csc.exe` anterior se muestra en `code style`.</span><span class="sxs-lookup"><span data-stu-id="18ba5-107">The older `csc.exe` syntax is shown in `code style`.</span></span>

- <span data-ttu-id="18ba5-108">**MainEntryPoint**, **StartupObject** / `-main`: se especifica el tipo que contiene el punto de entrada.</span><span class="sxs-lookup"><span data-stu-id="18ba5-108">**MainEntryPoint**, **StartupObject** / `-main`: Specify the type that contains the entry point.</span></span>
- <span data-ttu-id="18ba5-109">**PdbFile** / `-pdb`: se especifica el nombre del archivo de información de depuración.</span><span class="sxs-lookup"><span data-stu-id="18ba5-109">**PdbFile** / `-pdb`: Specify debug information file name.</span></span>
- <span data-ttu-id="18ba5-110">**PathMap** / `-pathmap`: se especifica una asignación para los nombres de rutas de acceso de origen generados por el compilador.</span><span class="sxs-lookup"><span data-stu-id="18ba5-110">**PathMap** / `-pathmap`: Specify a mapping for source path names output by the compiler.</span></span>
- <span data-ttu-id="18ba5-111">**ApplicationConfiguration** / `-appconfig`: se especifica un archivo de configuración de la aplicación que contenga la configuración de enlace de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="18ba5-111">**ApplicationConfiguration** / `-appconfig`: Specify an application configuration file containing assembly binding settings.</span></span>
- <span data-ttu-id="18ba5-112">**AdditionalLibPaths** / `-lib`: se especifican los directorios adicionales en los que buscar referencias.</span><span class="sxs-lookup"><span data-stu-id="18ba5-112">**AdditionalLibPaths** / `-lib`: Specify additional directories to search in for references.</span></span>
- <span data-ttu-id="18ba5-113">**GenerateFullPaths** / `-fullpath`: el compilador genera rutas de acceso completas.</span><span class="sxs-lookup"><span data-stu-id="18ba5-113">**GenerateFullPaths** / `-fullpath`: Compiler generates fully qualified paths.</span></span>
- <span data-ttu-id="18ba5-114">**PreferredUILang** / `-preferreduilang`: se especifica el nombre del lenguaje de salida preferido.</span><span class="sxs-lookup"><span data-stu-id="18ba5-114">**PreferredUILang** / `-preferreduilang`: Specify the preferred output language name.</span></span>
- <span data-ttu-id="18ba5-115">**BaseAddress** / `-baseaddress`: se especifica la dirección base de la biblioteca que se va a compilar.</span><span class="sxs-lookup"><span data-stu-id="18ba5-115">**BaseAddress** / `-baseaddress`: Specify the base address for the library to be built.</span></span>
- <span data-ttu-id="18ba5-116">**ChecksumAlgorithm** / `-checksumalgorithm`: se especifica el algoritmo para calcular la suma de comprobación del archivo de origen almacenada en el archivo PDB.</span><span class="sxs-lookup"><span data-stu-id="18ba5-116">**ChecksumAlgorithm** / `-checksumalgorithm` : Specify algorithm for calculating source file checksum stored in PDB.</span></span>
- <span data-ttu-id="18ba5-117">**CodePage** / `-codepage`: se especifica la página de códigos que se va a usar al abrir los archivos de código fuente.</span><span class="sxs-lookup"><span data-stu-id="18ba5-117">**CodePage** / `-codepage`: Specify the codepage to use when opening source files.</span></span>
- <span data-ttu-id="18ba5-118">**Utf8Output** / `-utf8output`: se muestran los mensajes del compilador en codificación UTF-8.</span><span class="sxs-lookup"><span data-stu-id="18ba5-118">**Utf8Output** / `-utf8output`: Output compiler messages in UTF-8 encoding.</span></span>
- <span data-ttu-id="18ba5-119">**FileAlignment** / `-filealign`: se especifica la alineación utilizada para las secciones de archivos de salida.</span><span class="sxs-lookup"><span data-stu-id="18ba5-119">**FileAlignment** / `-filealign`: Specify the alignment used for output file sections.</span></span>
- <span data-ttu-id="18ba5-120">**ErrorEndLocation** / `-errorendlocation`: se muestra la línea y la columna de salida de la ubicación final de cada error.</span><span class="sxs-lookup"><span data-stu-id="18ba5-120">**ErrorEndLocation** / `-errorendlocation`: Output line and column of the end location of each error.</span></span>
- <span data-ttu-id="18ba5-121">**NoStandardLib** / `-nostdlib`: no se hace referencia a la biblioteca estándar *mscorlib.dll*.</span><span class="sxs-lookup"><span data-stu-id="18ba5-121">**NoStandardLib** / `-nostdlib`: Don't reference standard library *mscorlib.dll*.</span></span>
- <span data-ttu-id="18ba5-122">**SubsystemVersion** / `-subsystemversion`: se especifica la versión del subsistema de este ensamblado.</span><span class="sxs-lookup"><span data-stu-id="18ba5-122">**SubsystemVersion** / `-subsystemversion`: Specify subsystem version of this assembly.</span></span>
- <span data-ttu-id="18ba5-123">**ModuleAssemblyName** / `-moduleassemblyname`: nombre del ensamblado del que este módulo formará parte.</span><span class="sxs-lookup"><span data-stu-id="18ba5-123">**ModuleAssemblyName** / `-moduleassemblyname`: Name of the assembly that this module will be a part of.</span></span>

## <a name="mainentrypoint-or-startupobject"></a><span data-ttu-id="18ba5-124">MainEntryPoint o StartupObject</span><span class="sxs-lookup"><span data-stu-id="18ba5-124">MainEntryPoint or StartupObject</span></span>

<span data-ttu-id="18ba5-125">Esta opción especifica la clase que contiene el punto de entrada al programa si hay más de una clase que contenga un método `Main`.</span><span class="sxs-lookup"><span data-stu-id="18ba5-125">This option specifies the class that contains the entry point to the program, if more than one class contains a `Main` method.</span></span>

```xml
<StartupObject>MyNamespace.Program</StartupObject>
```

<span data-ttu-id="18ba5-126">or</span><span class="sxs-lookup"><span data-stu-id="18ba5-126">or</span></span>

```xml
<MainEntryPoint>MyNamespace.Program</MainEntryPoint>
```

<span data-ttu-id="18ba5-127">Donde `Program` es el tipo que contiene el método `Main`.</span><span class="sxs-lookup"><span data-stu-id="18ba5-127">Where `Program` is the type that contains the `Main` method.</span></span> <span data-ttu-id="18ba5-128">El nombre de clase proporcionado debe ser completo: debe incluir el espacio de nombres completo que contiene la clase, seguido del nombre de clase.</span><span class="sxs-lookup"><span data-stu-id="18ba5-128">The provided class name must be fully qualified; it must include the full namespace containing the class, followed by the class name.</span></span> <span data-ttu-id="18ba5-129">Por ejemplo, cuando el método `Main` se encuentra dentro de la clase `Program` en el espacio de nombres `MyApplication.Core`, la opción del compilador tiene que ser `-main:MyApplication.Core.Program`.</span><span class="sxs-lookup"><span data-stu-id="18ba5-129">For example, when the `Main` method is located inside the `Program` class in the `MyApplication.Core` namespace, the compiler option has to be `-main:MyApplication.Core.Program`.</span></span> <span data-ttu-id="18ba5-130">Si la compilación incluye más de un tipo con un método [`Main`](../../programming-guide/main-and-command-args/index.md), puede especificar qué tipo contiene el método `Main`.</span><span class="sxs-lookup"><span data-stu-id="18ba5-130">If your compilation includes more than one type with a [`Main`](../../programming-guide/main-and-command-args/index.md) method, you can specify which type contains the `Main` method.</span></span>

> [!NOTE]
> <span data-ttu-id="18ba5-131">Esta opción no se puede usar para un proyecto que incluya [instrucciones de nivel superior](../../programming-guide/main-and-command-args/top-level-statements.md), incluso si contiene uno o más métodos `Main`.</span><span class="sxs-lookup"><span data-stu-id="18ba5-131">This option can't be used for a project that includes [top-level statements](../../programming-guide/main-and-command-args/top-level-statements.md), even if that project contains one or more `Main` methods.</span></span>

## <a name="pdbfile"></a><span data-ttu-id="18ba5-132">PdbFile</span><span class="sxs-lookup"><span data-stu-id="18ba5-132">PdbFile</span></span>

<span data-ttu-id="18ba5-133">La opción del compilador **PdbFile** especifica el nombre y la ubicación del archivo de símbolos de depuración.</span><span class="sxs-lookup"><span data-stu-id="18ba5-133">The **PdbFile** compiler option specifies the name and location of the debug symbols file.</span></span>  <span data-ttu-id="18ba5-134">El valor `filename` especifica el nombre y la ubicación del archivo de símbolos de depuración.</span><span class="sxs-lookup"><span data-stu-id="18ba5-134">The `filename` value specifies the name and location of the debug symbols file.</span></span>  

```xml
<PdbFile>filename</PdbFile>
```

<span data-ttu-id="18ba5-135">Al especificar [**DebugType**](code-generation.md#debugtype), el compilador creará un archivo *.pdb* en el mismo directorio donde creará el archivo de salida (.exe o .dll).</span><span class="sxs-lookup"><span data-stu-id="18ba5-135">When you specify [**DebugType**](code-generation.md#debugtype), the compiler will create a *.pdb* file in the same directory where the compiler will create the output file (.exe or .dll).</span></span> <span data-ttu-id="18ba5-136">El archivo *.pdb* tiene el mismo nombre de archivo base que el del archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="18ba5-136">The *.pdb* file has the same base file name as the name of the output file.</span></span> <span data-ttu-id="18ba5-137">**PdbFile** le permite especificar un nombre de archivo y una ubicación distintos a los predeterminados para el archivo .pdb.</span><span class="sxs-lookup"><span data-stu-id="18ba5-137">**PdbFile** allows you to specify a non-default file name and location for the .pdb file.</span></span> <span data-ttu-id="18ba5-138">No se puede establecer esta opción del compilador en el entorno de desarrollo de Visual Studio, ni se puede cambiar mediante programación.</span><span class="sxs-lookup"><span data-stu-id="18ba5-138">This compiler option cannot be set in the Visual Studio development environment, nor can it be changed programmatically.</span></span>  

## <a name="pathmap"></a><span data-ttu-id="18ba5-139">PathMap</span><span class="sxs-lookup"><span data-stu-id="18ba5-139">PathMap</span></span>

<span data-ttu-id="18ba5-140">La opción del compilador **PathMap** especifica cómo asignar rutas de acceso físicas a los nombres de rutas de acceso de origen generados por el compilador.</span><span class="sxs-lookup"><span data-stu-id="18ba5-140">The **PathMap** compiler option specifies how to map physical paths to source path names output by the compiler.</span></span> <span data-ttu-id="18ba5-141">Esta opción asigna cada ruta de acceso física en la máquina donde el compilador se ejecuta a una ruta de acceso correspondiente que debe escribirse en los archivos de salida.</span><span class="sxs-lookup"><span data-stu-id="18ba5-141">This option maps each physical path on the machine where the compiler runs to a corresponding path that should be written in the output files.</span></span> <span data-ttu-id="18ba5-142">En el ejemplo siguiente, `path1` es la ruta completa a los archivos de código fuente en el entorno actual y `sourcePath1` es la ruta de origen sustituida por `path1` en cualquier archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="18ba5-142">In the following example, `path1` is the full path to the source files in the current environment, and `sourcePath1` is the source path substituted for `path1` in any output files.</span></span> <span data-ttu-id="18ba5-143">Para especificar varias rutas de acceso de origen asignadas, sepárelas mediante punto y coma.</span><span class="sxs-lookup"><span data-stu-id="18ba5-143">To specify multiple mapped source paths, separate each with a semicolon.</span></span>

```xml
<PathMap>path1=sourcePath1;path2=sourcePath2</PathMap>
```

<span data-ttu-id="18ba5-144">El compilador escribe la ruta de acceso de origen en la salida por las razones siguientes:</span><span class="sxs-lookup"><span data-stu-id="18ba5-144">The compiler writes the source path into its output for the following reasons:</span></span>

1. <span data-ttu-id="18ba5-145">La ruta de acceso de origen se sustituye por un argumento cuando se aplica <xref:System.Runtime.CompilerServices.CallerFilePathAttribute> a un parámetro opcional.</span><span class="sxs-lookup"><span data-stu-id="18ba5-145">The source path is substituted for an argument when the <xref:System.Runtime.CompilerServices.CallerFilePathAttribute> is applied to an optional parameter.</span></span>
1. <span data-ttu-id="18ba5-146">La ruta de acceso de origen se inserta en un archivo PDB.</span><span class="sxs-lookup"><span data-stu-id="18ba5-146">The source path is embedded in a PDB file.</span></span>
1. <span data-ttu-id="18ba5-147">La ruta de acceso del archivo PDB se inserta en un archivo PE (ejecutable portable).</span><span class="sxs-lookup"><span data-stu-id="18ba5-147">The path of the PDB file is embedded into a PE (portable executable) file.</span></span>

## <a name="applicationconfiguration"></a><span data-ttu-id="18ba5-148">ApplicationConfiguration</span><span class="sxs-lookup"><span data-stu-id="18ba5-148">ApplicationConfiguration</span></span>

<span data-ttu-id="18ba5-149">La opción del compilador **ApplicationConfiguration** permite a una aplicación de C# especificar la ubicación del archivo de configuración de la aplicación de un ensamblado (app.config) al Common Language Runtime (CLR) en tiempo de enlace del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="18ba5-149">The **ApplicationConfiguration** compiler option enables a C# application to specify the location of an assembly's application configuration (app.config) file to the common language runtime (CLR) at assembly binding time.</span></span>

```xml
<ApplicationConfiguration>file</ApplicationConfiguration>
```

<span data-ttu-id="18ba5-150">`file` es el archivo de configuración de la aplicación que contiene los valores de enlace del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="18ba5-150">Where `file` is the application configuration file that contains assembly binding settings.</span></span> <span data-ttu-id="18ba5-151">Un uso de **ApplicationConfiguration** es para escenarios avanzados en los que un ensamblado tiene que hacer referencia a la versión de .NET Framework y a la de .NET Framework para Silverlight de un ensamblado de referencia determinado al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="18ba5-151">One use of **ApplicationConfiguration** is advanced scenarios in which an assembly has to reference both the .NET Framework version and the .NET Framework for Silverlight version of a particular reference assembly at the same time.</span></span> <span data-ttu-id="18ba5-152">Por ejemplo, un diseñador de XAML escrito en Windows Presentation Foundation (WPF) podría tener que hacer referencia al escritorio de WPF, para la interfaz de usuario del diseñador, y al subconjunto de WPF que se incluye con Silverlight.</span><span class="sxs-lookup"><span data-stu-id="18ba5-152">For example, a XAML designer written in Windows Presentation Foundation (WPF) might have to reference both the WPF Desktop, for the designer's user interface, and the subset of WPF that is included with Silverlight.</span></span> <span data-ttu-id="18ba5-153">El mismo ensamblado del diseñador tiene que tener acceso a ambos ensamblados.</span><span class="sxs-lookup"><span data-stu-id="18ba5-153">The same designer assembly has to access both assemblies.</span></span> <span data-ttu-id="18ba5-154">De forma predeterminada, las referencias independientes producen un error del compilador, ya que el enlace del ensamblado considera los dos ensamblados equivalentes.</span><span class="sxs-lookup"><span data-stu-id="18ba5-154">By default, the separate references cause a compiler error, because assembly binding sees the two assemblies as equivalent.</span></span> <span data-ttu-id="18ba5-155">La opción del compilador **ApplicationConfiguration** permite especificar la ubicación de un archivo app.config que deshabilita el comportamiento predeterminado mediante una etiqueta `<supportPortability>`, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="18ba5-155">The **ApplicationConfiguration** compiler option enables you to specify the location of an app.config file that disables the default behavior by using a `<supportPortability>` tag, as shown in the following example.</span></span>

```xml
<supportPortability PKT="7cec85d7bea7798e" enable="false"/>
```

<span data-ttu-id="18ba5-156">El compilador pasa la ubicación del archivo a la lógica de enlace del ensamblado de CLR.</span><span class="sxs-lookup"><span data-stu-id="18ba5-156">The compiler passes the location of the file to the CLR's assembly-binding logic.</span></span>

> [!NOTE]
> <span data-ttu-id="18ba5-157">Para usar el archivo app.config que ya está establecido en el proyecto, agregue la etiqueta de propiedades `<UseAppConfigForCompiler>` al archivo *.csproj* y establezca su valor en `true`.</span><span class="sxs-lookup"><span data-stu-id="18ba5-157">To use the app.config file that is already set in the project, add property tag `<UseAppConfigForCompiler>` to the *.csproj* file and set its value to `true`.</span></span> <span data-ttu-id="18ba5-158">Para especificar otro archivo app.config, agregue la etiqueta `<AppConfigForCompiler>` de propiedades y establezca su valor en la ubicación del archivo.</span><span class="sxs-lookup"><span data-stu-id="18ba5-158">To specify a different app.config file, add property tag `<AppConfigForCompiler>` and set its value to the location of the file.</span></span>

<span data-ttu-id="18ba5-159">En el siguiente ejemplo se muestra un archivo app.config que permite a una aplicación tener referencias a la implementación de .NET Framework y de .NET Framework para Silverlight de cualquier ensamblado de .NET Framework que exista en ambas implementaciones.</span><span class="sxs-lookup"><span data-stu-id="18ba5-159">The following example shows an app.config file that enables an application to have references to both the .NET Framework implementation and the .NET Framework for Silverlight implementation of any .NET Framework assembly that exists in both implementations.</span></span> <span data-ttu-id="18ba5-160">La opción del compilador **ApplicationConfiguration** especifica la ubicación de este archivo app.config.</span><span class="sxs-lookup"><span data-stu-id="18ba5-160">The **ApplicationConfiguration** compiler option specifies the location of this app.config file.</span></span>

```xml
<configuration>
  <runtime>
    <assemblyBinding>
      <supportPortability PKT="7cec85d7bea7798e" enable="false"/>
      <supportPortability PKT="31bf3856ad364e35" enable="false"/>
    </assemblyBinding>
  </runtime>
</configuration>
```

## <a name="additionallibpaths"></a><span data-ttu-id="18ba5-161">AdditionalLibPaths</span><span class="sxs-lookup"><span data-stu-id="18ba5-161">AdditionalLibPaths</span></span>

<span data-ttu-id="18ba5-162">La opción **AdditionalLibPaths** especifica la ubicación de los ensamblados a los que se hace referencia con la opción [**References**](inputs.md#references).</span><span class="sxs-lookup"><span data-stu-id="18ba5-162">The **AdditionalLibPaths** option specifies the location of assemblies referenced with the [**References**](inputs.md#references) option.</span></span>

```xml
<AdditionalLibPaths>dir1[,dir2]</AdditionalLibPaths>
```

<span data-ttu-id="18ba5-163">`dir1` es un directorio donde el compilador busca si un ensamblado al que se hace referencia no se encuentra en el directorio de trabajo actual (el directorio desde el que se invoca al compilador) o en el directorio del sistema de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="18ba5-163">Where `dir1` is a directory for the compiler to look in if a referenced assembly isn't found in the current working directory (the directory from which you're invoking the compiler) or in the common language runtime's system directory.</span></span> <span data-ttu-id="18ba5-164">`dir2` es uno o varios directorios adicionales en los que buscar referencias a ensamblados.</span><span class="sxs-lookup"><span data-stu-id="18ba5-164">`dir2` is one or more additional directories to search in for assembly references.</span></span> <span data-ttu-id="18ba5-165">Separe los nombres de directorio con una coma y sin espacio en blanco entre ellos.</span><span class="sxs-lookup"><span data-stu-id="18ba5-165">Separate directory names with a comma, and without white space between them.</span></span> <span data-ttu-id="18ba5-166">El compilador busca referencias a ensamblados que no presentan la ruta completa en el siguiente orden:</span><span class="sxs-lookup"><span data-stu-id="18ba5-166">The compiler searches for assembly references that aren't fully qualified in the following order:</span></span>  

1. <span data-ttu-id="18ba5-167">Directorio de trabajo actual.</span><span class="sxs-lookup"><span data-stu-id="18ba5-167">Current working directory.</span></span>
1. <span data-ttu-id="18ba5-168">El directorio del sistema de Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="18ba5-168">The common language runtime system directory.</span></span>
1. <span data-ttu-id="18ba5-169">Directorios especificados por **AdditionalLibPaths**.</span><span class="sxs-lookup"><span data-stu-id="18ba5-169">Directories specified by **AdditionalLibPaths**.</span></span>
1. <span data-ttu-id="18ba5-170">Directorios especificados por la variable de entorno LIB.</span><span class="sxs-lookup"><span data-stu-id="18ba5-170">Directories specified by the LIB environment variable.</span></span>

<span data-ttu-id="18ba5-171">Use **Reference** para especificar una referencia a un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="18ba5-171">Use **Reference** to specify an assembly reference.</span></span> <span data-ttu-id="18ba5-172">**AdditionalLibPaths** es aditivo.</span><span class="sxs-lookup"><span data-stu-id="18ba5-172">**AdditionalLibPaths** is additive.</span></span> <span data-ttu-id="18ba5-173">Si se especifica más de una vez, se anexa a los valores existentes.</span><span class="sxs-lookup"><span data-stu-id="18ba5-173">Specifying it more than once appends to any prior values.</span></span> <span data-ttu-id="18ba5-174">Como en el manifiesto del ensamblado no se especifica la ruta al ensamblado dependiente, la aplicación buscará y usará el ensamblado en la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="18ba5-174">Since the path to the dependent assembly isn't specified in the assembly manifest, the application will find and use the assembly in the global assembly cache.</span></span> <span data-ttu-id="18ba5-175">El compilador que hace referencia al ensamblado no implica que el Common Language Runtime pueda encontrar y cargar el ensamblado en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="18ba5-175">The compiler referencing the assembly doesn't imply the common language runtime can find and load the assembly at runtime.</span></span> <span data-ttu-id="18ba5-176">Vea [Cómo el motor en tiempo de ejecución ubica ensamblados](../../../framework/deployment/how-the-runtime-locates-assemblies.md) para obtener los detalles sobre cómo busca el motor en tiempo de ejecución los ensamblados a los que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="18ba5-176">See [How the Runtime Locates Assemblies](../../../framework/deployment/how-the-runtime-locates-assemblies.md) for details on how the runtime searches for referenced assemblies.</span></span>  

## <a name="generatefullpaths"></a><span data-ttu-id="18ba5-177">GenerateFullPaths</span><span class="sxs-lookup"><span data-stu-id="18ba5-177">GenerateFullPaths</span></span>

<span data-ttu-id="18ba5-178">La opción **GenerateFullPaths** hace que el compilador especifique la ruta completa al archivo cuando se muestran los errores de compilación y las advertencias.</span><span class="sxs-lookup"><span data-stu-id="18ba5-178">The **GenerateFullPaths** option causes the compiler to specify the full path to the file when listing compilation errors and warnings.</span></span>
  
```Xml
<GenerateFullPaths>true</GenerateFullPaths>
```

<span data-ttu-id="18ba5-179">De manera predeterminada, los errores y advertencias que se producen de la compilación especifican el nombre del archivo en el que se ha detectado el error.</span><span class="sxs-lookup"><span data-stu-id="18ba5-179">By default, errors and warnings that result from compilation specify the name of the file in which an error was found.</span></span> <span data-ttu-id="18ba5-180">La opción **GenerateFullPaths** hace que el compilador especifique la ruta completa al archivo.</span><span class="sxs-lookup"><span data-stu-id="18ba5-180">The **GenerateFullPaths** option causes the compiler to specify the full path to the file.</span></span> <span data-ttu-id="18ba5-181">Esta opción del compilador no está disponible en Visual Studio y no se puede cambiar mediante programación.</span><span class="sxs-lookup"><span data-stu-id="18ba5-181">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>

## <a name="preferreduilang"></a><span data-ttu-id="18ba5-182">PreferredUILang</span><span class="sxs-lookup"><span data-stu-id="18ba5-182">PreferredUILang</span></span>

<span data-ttu-id="18ba5-183">Mediante la opción del compilador **PreferredUILang** puede especificar el idioma en el que el compilador de C# muestra el resultado, como los mensajes de error.</span><span class="sxs-lookup"><span data-stu-id="18ba5-183">By using the **PreferredUILang** compiler option, you can specify the language in which the C# compiler displays output, such as error messages.</span></span>

```xml
<PreferredUILang>language</PreferredUILang>
```

<span data-ttu-id="18ba5-184">`language` es el [nombre del idioma](/windows/desktop/Intl/language-names) que se va a usar para la salida del compilador.</span><span class="sxs-lookup"><span data-stu-id="18ba5-184">Where `language` is the [language name](/windows/desktop/Intl/language-names) of the language to use for compiler output.</span></span> <span data-ttu-id="18ba5-185">Puede usar la opción del compilador **PreferredUILang** para especificar el idioma que quiere que use el compilador de C# para los mensajes de error y otra salida de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="18ba5-185">You can use the **PreferredUILang** compiler option to specify the language that you want the C# compiler to use for error messages and other command-line output.</span></span> <span data-ttu-id="18ba5-186">Si el paquete de idioma para el idioma no está instalado, en su lugar se usa la configuración de idioma del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="18ba5-186">If the language pack for the language isn't installed, the language setting of the operating system is used instead.</span></span>

## <a name="baseaddress"></a><span data-ttu-id="18ba5-187">BaseAddress</span><span class="sxs-lookup"><span data-stu-id="18ba5-187">BaseAddress</span></span>

<span data-ttu-id="18ba5-188">La opción **BaseAddress** permite especificar la dirección base preferida en la que cargar un archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="18ba5-188">The **BaseAddress** option lets you specify the preferred base address at which to load a DLL.</span></span> <span data-ttu-id="18ba5-189">Para obtener más información sobre cuándo y por qué usar esta opción, vea el [blog de Larry Osterman](/archive/blogs/larryosterman/why-should-i-even-bother-to-use-dlls-in-my-system).</span><span class="sxs-lookup"><span data-stu-id="18ba5-189">For more information about when and why to use this option, see [Larry Osterman's WebLog](/archive/blogs/larryosterman/why-should-i-even-bother-to-use-dlls-in-my-system).</span></span>

```xml
<BaseAddress>address</BaseAddress>
```

<span data-ttu-id="18ba5-190">`address` es la dirección base del archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="18ba5-190">Where `address` is the base address for the DLL.</span></span> <span data-ttu-id="18ba5-191">Esta dirección puede especificarse como un número octal, hexadecimal o decimal.</span><span class="sxs-lookup"><span data-stu-id="18ba5-191">This address can be specified as a decimal, hexadecimal, or octal number.</span></span> <span data-ttu-id="18ba5-192">La dirección base predeterminada para un archivo DLL se establece mediante Common Language Runtime de .NET.</span><span class="sxs-lookup"><span data-stu-id="18ba5-192">The default base address for a DLL is set by the .NET common language runtime.</span></span> <span data-ttu-id="18ba5-193">La palabra de orden inferior en esta dirección se redondeará.</span><span class="sxs-lookup"><span data-stu-id="18ba5-193">The lower-order word in this address will be rounded.</span></span> <span data-ttu-id="18ba5-194">Por ejemplo, si especifica `0x11110001`, se redondeará a `0x11110000`.</span><span class="sxs-lookup"><span data-stu-id="18ba5-194">For example, if you specify `0x11110001`, it will be rounded to `0x11110000`.</span></span> <span data-ttu-id="18ba5-195">Para completar el proceso de firma para un archivo DLL, use SN.EXE con la opción -R.</span><span class="sxs-lookup"><span data-stu-id="18ba5-195">To complete the signing process for a DLL, use SN.EXE with the -R option.</span></span>

## <a name="checksumalgorithm"></a><span data-ttu-id="18ba5-196">ChecksumAlgorithm</span><span class="sxs-lookup"><span data-stu-id="18ba5-196">ChecksumAlgorithm</span></span>

<span data-ttu-id="18ba5-197">Esta opción controla el algoritmo de suma de comprobación que se usa para codificar los archivos de código fuente en el archivo PDB.</span><span class="sxs-lookup"><span data-stu-id="18ba5-197">This option controls the checksum algorithm we use to encode source files in the PDB.</span></span>

```xml
<ChecksumAlgorithm>algorithm</ChecksumAlgorithm>
```

<span data-ttu-id="18ba5-198">`algorithm` debe ser `SHA1` (el valor predeterminado) o `SHA256`.</span><span class="sxs-lookup"><span data-stu-id="18ba5-198">The `algorithm` must be either `SHA1` (default) or `SHA256`.</span></span>

## <a name="codepage"></a><span data-ttu-id="18ba5-199">CodePage</span><span class="sxs-lookup"><span data-stu-id="18ba5-199">CodePage</span></span>

<span data-ttu-id="18ba5-200">Esta opción especifica qué página de códigos se va a usar durante la compilación si la página necesaria no es la página de códigos predeterminada actual del sistema.</span><span class="sxs-lookup"><span data-stu-id="18ba5-200">This option specifies which codepage to use during compilation if the required page isn't the current default codepage for the system.</span></span>
  
```xml
<CodePage>id</CodePage>
```

<span data-ttu-id="18ba5-201">`id` es el id. de la página de códigos que se va a usar para todos los archivos de código fuente de la compilación.</span><span class="sxs-lookup"><span data-stu-id="18ba5-201">Where `id` is the id of the code page to use for all source code files in the compilation.</span></span> <span data-ttu-id="18ba5-202">El compilador primero intenta interpretar todos los archivos de código fuente como UTF-8.</span><span class="sxs-lookup"><span data-stu-id="18ba5-202">The compiler will first attempt to interpret all source files as UTF-8.</span></span> <span data-ttu-id="18ba5-203">Si los archivos de código fuente se encuentran en una codificación distinta de UTF-8 y usan caracteres que no sean ASCII de 7 bits, utilice la opción **CodePage** para especificar qué página de códigos se debe usar.</span><span class="sxs-lookup"><span data-stu-id="18ba5-203">If your source code files are in an encoding other than UTF-8 and use characters other than 7-bit ASCII characters, use the **CodePage** option to specify which code page should be used.</span></span> <span data-ttu-id="18ba5-204">**CodePage** se aplica a todos los archivos de código fuente de la compilación.</span><span class="sxs-lookup"><span data-stu-id="18ba5-204">**CodePage** applies to all source code files in your compilation.</span></span> <span data-ttu-id="18ba5-205">Vea [GetCPInfo](/windows/desktop/api/winnls/nf-winnls-getcpinfo) para obtener información sobre cómo buscar las páginas de códigos que se admiten en su sistema.</span><span class="sxs-lookup"><span data-stu-id="18ba5-205">See [GetCPInfo](/windows/desktop/api/winnls/nf-winnls-getcpinfo) for information on how to find which code pages are supported on your system.</span></span>

## <a name="utf8output"></a><span data-ttu-id="18ba5-206">Utf8Output</span><span class="sxs-lookup"><span data-stu-id="18ba5-206">Utf8Output</span></span>

<span data-ttu-id="18ba5-207">La opción **Utf8Output** muestra los resultados del compilador en codificación UTF-8.</span><span class="sxs-lookup"><span data-stu-id="18ba5-207">The **Utf8Output** option displays compiler output using UTF-8 encoding.</span></span>

```xml
<Utf8Output>true</Utf8Output>
```

<span data-ttu-id="18ba5-208">En algunas configuraciones internacionales, el resultado del compilador no puede mostrarse correctamente en la consola.</span><span class="sxs-lookup"><span data-stu-id="18ba5-208">In some international configurations, compiler output cannot correctly be displayed in the console.</span></span> <span data-ttu-id="18ba5-209">Use **Utf8Output** y redirija el resultado del compilador a un archivo.</span><span class="sxs-lookup"><span data-stu-id="18ba5-209">Use **Utf8Output** and redirect compiler output to a file.</span></span>

## <a name="filealignment"></a><span data-ttu-id="18ba5-210">FileAlignment</span><span class="sxs-lookup"><span data-stu-id="18ba5-210">FileAlignment</span></span>

<span data-ttu-id="18ba5-211">La opción **FileAlignment** permite especificar el tamaño de las secciones en el archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="18ba5-211">The **FileAlignment** option lets you specify the size of sections in your output file.</span></span> <span data-ttu-id="18ba5-212">Los valores válidos son 512, 1024, 2048, 4096 y 8192.</span><span class="sxs-lookup"><span data-stu-id="18ba5-212">Valid values are 512, 1024, 2048, 4096, and 8192.</span></span> <span data-ttu-id="18ba5-213">Estos valores están en bytes.</span><span class="sxs-lookup"><span data-stu-id="18ba5-213">These values are in bytes.</span></span>

```xml
<FileAlignment>number</FileAlignment>
```

<span data-ttu-id="18ba5-214">La opción **FileAlignment** se establece en la página **Avanzado** de las propiedades de **Compilación** del proyecto en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="18ba5-214">You set the **FileAlignment** option from the **Advanced** page of the **Build** properties for your project in Visual Studio.</span></span> <span data-ttu-id="18ba5-215">Cada sección se alineará en un límite que es un múltiplo del valor **FileAlignment**.</span><span class="sxs-lookup"><span data-stu-id="18ba5-215">Each section will be aligned on a boundary that is a multiple of the **FileAlignment** value.</span></span> <span data-ttu-id="18ba5-216">No hay ningún valor predeterminado fijo.</span><span class="sxs-lookup"><span data-stu-id="18ba5-216">There's no fixed default.</span></span> <span data-ttu-id="18ba5-217">Si no se especifica **FileAlignment**, Common Language Runtime elige un valor predeterminado en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="18ba5-217">If **FileAlignment** isn't specified, the common language runtime picks a default at compile time.</span></span> <span data-ttu-id="18ba5-218">Al especificar el tamaño de la sección, el tamaño del archivo de salida se ve afectado.</span><span class="sxs-lookup"><span data-stu-id="18ba5-218">By specifying the section size, you affect the size of the output file.</span></span> <span data-ttu-id="18ba5-219">Modificar el tamaño de la sección puede ser útil para los programas que se ejecutan en dispositivos más pequeños.</span><span class="sxs-lookup"><span data-stu-id="18ba5-219">Modifying section size may be useful for programs that will run on smaller devices.</span></span> <span data-ttu-id="18ba5-220">Use [DUMPBIN](/cpp/build/reference/dumpbin-options) para ver información sobre las secciones en el archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="18ba5-220">Use [DUMPBIN](/cpp/build/reference/dumpbin-options) to see information about sections in your output file.</span></span>

## <a name="errorendlocation"></a><span data-ttu-id="18ba5-221">ErrorEndLocation</span><span class="sxs-lookup"><span data-stu-id="18ba5-221">ErrorEndLocation</span></span>

<span data-ttu-id="18ba5-222">Indica al compilador que muestre la línea y la columna de salida de la ubicación final de cada error.</span><span class="sxs-lookup"><span data-stu-id="18ba5-222">Instructs the compiler to output line and column of the end location of each error.</span></span>

```xml
<ErrorEndLocation>filename</ErrorEndLocation>
```

<span data-ttu-id="18ba5-223">De forma predeterminada, el compilador escribe la ubicación inicial en el origen para todos los errores y advertencias.</span><span class="sxs-lookup"><span data-stu-id="18ba5-223">By default, the compiler writes the starting location in source for all errors and warnings.</span></span> <span data-ttu-id="18ba5-224">Cuando esta opción se establece en true, el compilador escribe la ubicación inicial y final para todos los errores y advertencias.</span><span class="sxs-lookup"><span data-stu-id="18ba5-224">When this option is set to true, the compiler writes both the starting and end location for each error and warning.</span></span>

## <a name="nostandardlib"></a><span data-ttu-id="18ba5-225">NoStandardLib</span><span class="sxs-lookup"><span data-stu-id="18ba5-225">NoStandardLib</span></span>

<span data-ttu-id="18ba5-226">**NoStandardLib** impide la importación de mscorlib.dll, que define el espacio de nombres System completo.</span><span class="sxs-lookup"><span data-stu-id="18ba5-226">**NoStandardLib** prevents the import of mscorlib.dll, which defines the entire System namespace.</span></span>

```xml
<NoStandardLib>true</NoStandardLib>
```

<span data-ttu-id="18ba5-227">Use esta opción si desea definir o crear sus propios objetos y espacio de nombres System.</span><span class="sxs-lookup"><span data-stu-id="18ba5-227">Use this option if you want to define or create your own System namespace and objects.</span></span> <span data-ttu-id="18ba5-228">Si no se especifica **NoStandardLib**, mscorlib.dll se importa en el programa (equivale a especificar `<NoStandardLib>false</NoStandardLib>`).</span><span class="sxs-lookup"><span data-stu-id="18ba5-228">If you don't specify **NoStandardLib**, mscorlib.dll is imported into your program (same as specifying `<NoStandardLib>false</NoStandardLib>`).</span></span>

## <a name="subsystemversion"></a><span data-ttu-id="18ba5-229">SubsystemVersion</span><span class="sxs-lookup"><span data-stu-id="18ba5-229">SubsystemVersion</span></span>

<span data-ttu-id="18ba5-230">Especifica la versión mínima del subsistema en el que se ejecuta el archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="18ba5-230">Specifies the minimum version of the subsystem on which the executable file runs.</span></span> <span data-ttu-id="18ba5-231">Normalmente, esta opción garantiza que el archivo ejecutable pueda usar características de seguridad que no están disponibles en versiones anteriores de Windows.</span><span class="sxs-lookup"><span data-stu-id="18ba5-231">Most commonly, this option ensures that the executable file can use security features that aren’t available with older versions of Windows.</span></span>

> [!NOTE]
> <span data-ttu-id="18ba5-232">Para especificar el subsistema en sí mismo, use la opción del compilador [**TargetType**](./output.md#targettype).</span><span class="sxs-lookup"><span data-stu-id="18ba5-232">To specify the subsystem itself, use the [**TargetType**](./output.md#targettype) compiler option.</span></span>

```xml
<SubsystemVersion>major.minor</SubsystemVersion>
```

<span data-ttu-id="18ba5-233">`major.minor` especifica la versión mínima necesaria del subsistema, expresada en una notación de puntos para las versiones principales y secundarias.</span><span class="sxs-lookup"><span data-stu-id="18ba5-233">The `major.minor` specify the minimum required version of the subsystem, as expressed in a dot notation for major and minor versions.</span></span> <span data-ttu-id="18ba5-234">Por ejemplo, puede especificar que una aplicación no se pueda ejecutar en un sistema operativo anterior a Windows 7.</span><span class="sxs-lookup"><span data-stu-id="18ba5-234">For example, you can specify that an application can't run on an operating system that's older than Windows 7.</span></span> <span data-ttu-id="18ba5-235">Establezca el valor de esta opción en 6.01, como se describe en la tabla que se muestra más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="18ba5-235">Set the value of this option to 6.01, as the table later in this article describes.</span></span> <span data-ttu-id="18ba5-236">Especifique los valores de `major` y `minor` como números enteros.</span><span class="sxs-lookup"><span data-stu-id="18ba5-236">You specify the values for `major` and `minor` as integers.</span></span> <span data-ttu-id="18ba5-237">Los ceros a la izquierda en la versión `minor` no cambian la versión, pero los ceros a la derecha sí.</span><span class="sxs-lookup"><span data-stu-id="18ba5-237">Leading zeroes in the `minor` version don't change the version, but trailing zeroes do.</span></span> <span data-ttu-id="18ba5-238">Por ejemplo, 6.1 y 6.01 hacen referencia a la misma versión, pero 6.10 hace referencia a una versión diferente.</span><span class="sxs-lookup"><span data-stu-id="18ba5-238">For example, 6.1 and 6.01 refer to the same version, but 6.10 refers to a different version.</span></span> <span data-ttu-id="18ba5-239">Se recomienda expresar la versión secundaria como dos dígitos para evitar confusiones.</span><span class="sxs-lookup"><span data-stu-id="18ba5-239">We recommend expressing the minor version as two digits to avoid confusion.</span></span>

<span data-ttu-id="18ba5-240">En la tabla siguiente se enumeran las versiones de subsistema habituales de Windows.</span><span class="sxs-lookup"><span data-stu-id="18ba5-240">The following table lists common subsystem versions of Windows.</span></span>

|<span data-ttu-id="18ba5-241">Versión de Windows</span><span class="sxs-lookup"><span data-stu-id="18ba5-241">Windows version</span></span>|<span data-ttu-id="18ba5-242">Versión de subsistema</span><span class="sxs-lookup"><span data-stu-id="18ba5-242">Subsystem version</span></span>|
|---------------------|-----------------------|
|<span data-ttu-id="18ba5-243">Windows 2000</span><span class="sxs-lookup"><span data-stu-id="18ba5-243">Windows 2000</span></span>|<span data-ttu-id="18ba5-244">5.00</span><span class="sxs-lookup"><span data-stu-id="18ba5-244">5.00</span></span>|
|<span data-ttu-id="18ba5-245">Windows XP</span><span class="sxs-lookup"><span data-stu-id="18ba5-245">Windows XP</span></span>|<span data-ttu-id="18ba5-246">5.01</span><span class="sxs-lookup"><span data-stu-id="18ba5-246">5.01</span></span>|
|<span data-ttu-id="18ba5-247">Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="18ba5-247">Windows Server 2003</span></span>|<span data-ttu-id="18ba5-248">5.02</span><span class="sxs-lookup"><span data-stu-id="18ba5-248">5.02</span></span>|
|<span data-ttu-id="18ba5-249">Windows Vista</span><span class="sxs-lookup"><span data-stu-id="18ba5-249">Windows Vista</span></span>|<span data-ttu-id="18ba5-250">6.00</span><span class="sxs-lookup"><span data-stu-id="18ba5-250">6.00</span></span>|
|<span data-ttu-id="18ba5-251">Windows 7</span><span class="sxs-lookup"><span data-stu-id="18ba5-251">Windows 7</span></span>|<span data-ttu-id="18ba5-252">6.01</span><span class="sxs-lookup"><span data-stu-id="18ba5-252">6.01</span></span>|
|<span data-ttu-id="18ba5-253">Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="18ba5-253">Windows Server 2008</span></span>|<span data-ttu-id="18ba5-254">6.01</span><span class="sxs-lookup"><span data-stu-id="18ba5-254">6.01</span></span>|
|<span data-ttu-id="18ba5-255">Windows 8</span><span class="sxs-lookup"><span data-stu-id="18ba5-255">Windows 8</span></span>|<span data-ttu-id="18ba5-256">6.02</span><span class="sxs-lookup"><span data-stu-id="18ba5-256">6.02</span></span>|

<span data-ttu-id="18ba5-257">El valor predeterminado de la opción del compilador **SubsystemVersion** depende de las condiciones de la lista siguiente:</span><span class="sxs-lookup"><span data-stu-id="18ba5-257">The default value of the **SubsystemVersion** compiler option depends on the conditions in the following list:</span></span>

- <span data-ttu-id="18ba5-258">El valor predeterminado es 6.02 si se establece cualquier opción del compilador en la siguiente lista:</span><span class="sxs-lookup"><span data-stu-id="18ba5-258">The default value is 6.02 if any compiler option in the following list is set:</span></span>
  - [<span data-ttu-id="18ba5-259">/target:appcontainerexe</span><span class="sxs-lookup"><span data-stu-id="18ba5-259">-target:appcontainerexe</span></span>](./target-appcontainerexe-compiler-option.md)
  - [<span data-ttu-id="18ba5-260">/target:winmdobj</span><span class="sxs-lookup"><span data-stu-id="18ba5-260">-target:winmdobj</span></span>](./target-winmdobj-compiler-option.md)
  - [<span data-ttu-id="18ba5-261">-platform:arm</span><span class="sxs-lookup"><span data-stu-id="18ba5-261">-platform:arm</span></span>](./platform-compiler-option.md)
- <span data-ttu-id="18ba5-262">El valor predeterminado es 6,00 si usa MSBuild, tiene como destino .NET Framework 4.5 y no ha configurado ninguna de las opciones del compilador que se han especificado anteriormente en esta lista.</span><span class="sxs-lookup"><span data-stu-id="18ba5-262">The default value is 6.00 if you're using MSBuild, you're targeting .NET Framework 4.5, and you haven't set any of the compiler options that were specified earlier in this list.</span></span>
- <span data-ttu-id="18ba5-263">El valor predeterminado es 4.00 si no se cumple ninguna de las condiciones anteriores.</span><span class="sxs-lookup"><span data-stu-id="18ba5-263">The default value is 4.00 if none of the previous conditions are true.</span></span>

## <a name="moduleassemblyname"></a><span data-ttu-id="18ba5-264">ModuleAssemblyName</span><span class="sxs-lookup"><span data-stu-id="18ba5-264">ModuleAssemblyName</span></span>

<span data-ttu-id="18ba5-265">Especifica el nombre de un ensamblado con tipos no públicos a los que puede acceder un archivo *.netmodule*.</span><span class="sxs-lookup"><span data-stu-id="18ba5-265">Specifies the name of an assembly whose non-public types a *.netmodule* can access.</span></span>

```xml
<ModuleAssemblyName>assembly_name</ModuleAssemblyName>
```

<span data-ttu-id="18ba5-266">Se debería usar **ModuleAssemblyName** al compilar un archivo *.netmodule* cuando se cumplan las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="18ba5-266">**ModuleAssemblyName** should be used when building a *.netmodule*, and where the following conditions are true:</span></span>

- <span data-ttu-id="18ba5-267">*.netmodule* necesita acceder a los tipos no públicos de un ensamblado existente.</span><span class="sxs-lookup"><span data-stu-id="18ba5-267">The *.netmodule* needs access to non-public types in an existing assembly.</span></span>
- <span data-ttu-id="18ba5-268">Sabe el nombre del ensamblado en el que se compilará .netmodule.</span><span class="sxs-lookup"><span data-stu-id="18ba5-268">You know the name of the assembly into which the .netmodule will be built.</span></span>
- <span data-ttu-id="18ba5-269">El ensamblado existente ha concedido acceso de ensamblado de confianza al ensamblado en el que se compilará *.netmodule*.</span><span class="sxs-lookup"><span data-stu-id="18ba5-269">The existing assembly has granted friend assembly access to the assembly into which the .*netmodule* will be built.</span></span>

<span data-ttu-id="18ba5-270">Para obtener más información sobre cómo crear un archivo .netmodule, vea la opción [**TargetType**](output.md#targettype) de **module**.</span><span class="sxs-lookup"><span data-stu-id="18ba5-270">For more information on building a .netmodule, see [**TargetType**](output.md#targettype) option of **module**.</span></span> <span data-ttu-id="18ba5-271">Para obtener más información sobre los ensamblados de confianza, vea [Ensamblados de confianza](../../../standard/assembly/friend.md).</span><span class="sxs-lookup"><span data-stu-id="18ba5-271">For more information on friend assemblies, see [Friend Assemblies](../../../standard/assembly/friend.md).</span></span>
