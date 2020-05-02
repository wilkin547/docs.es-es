---
title: Opciones de configuración de runtime
description: Aprenda a configurar aplicaciones .NET Core mediante opciones de configuración de tiempo de ejecución.
ms.date: 01/21/2020
ms.openlocfilehash: d49707b93e272f0e527ff536a80140ec98e5c1a8
ms.sourcegitcommit: 1cb64b53eb1f253e6a3f53ca9510ef0be1fd06fe
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2020
ms.locfileid: "82506792"
---
# <a name="net-core-run-time-configuration-settings"></a><span data-ttu-id="f7296-103">Opciones de configuración en tiempo de ejecución de .NET Core</span><span class="sxs-lookup"><span data-stu-id="f7296-103">.NET Core run-time configuration settings</span></span>

<span data-ttu-id="f7296-104">.NET Core admite el uso de archivos de configuración y variables de entorno para configurar el comportamiento de las aplicaciones .NET Core en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="f7296-104">.NET Core supports the use of configuration files and environment variables to configure the behavior of .NET Core applications at run time.</span></span> <span data-ttu-id="f7296-105">La configuración en tiempo de ejecución es una opción atractiva si:</span><span class="sxs-lookup"><span data-stu-id="f7296-105">Run-time configuration is an attractive option if:</span></span>

- <span data-ttu-id="f7296-106">No se posee ni controla el código fuente de una aplicación y, por tanto, no puede configurarlo mediante programación.</span><span class="sxs-lookup"><span data-stu-id="f7296-106">You don't own or control the source code for an application and therefore are unable to configure it programmatically.</span></span>

- <span data-ttu-id="f7296-107">Varias instancias de la aplicación se ejecutan al mismo tiempo en un solo sistema y se quiere configurar cada una para un rendimiento óptimo.</span><span class="sxs-lookup"><span data-stu-id="f7296-107">Multiple instances of your application run at the same time on a single system, and you want to configure each for optimum performance.</span></span>

> [!NOTE]
> <span data-ttu-id="f7296-108">Esta documentación está en desarrollo.</span><span class="sxs-lookup"><span data-stu-id="f7296-108">This documentation is a work in progress.</span></span> <span data-ttu-id="f7296-109">Si observa que la información que se presenta aquí está incompleta o es inexacta, [abra una incidencia](https://github.com/dotnet/docs/issues) para informarnos sobre ella o [envíe una solicitud de incorporación de cambios](https://github.com/dotnet/docs/pulls) para solucionarla.</span><span class="sxs-lookup"><span data-stu-id="f7296-109">If you notice that the information presented here is either incomplete or inaccurate, either [open an issue](https://github.com/dotnet/docs/issues) to let us know about it, or [submit a pull request](https://github.com/dotnet/docs/pulls) to address the issue.</span></span> <span data-ttu-id="f7296-110">Para obtener información sobre el envío de solicitudes de incorporación de cambios para el repositorio dotnet/docs, consulte la [guía del colaborador](https://docs.microsoft.com/contribute/dotnet/dotnet-contribute).</span><span class="sxs-lookup"><span data-stu-id="f7296-110">For information about submitting pull requests for the dotnet/docs repository, see the [contributor's guide](https://docs.microsoft.com/contribute/dotnet/dotnet-contribute).</span></span>

<span data-ttu-id="f7296-111">.NET Core ofrece los siguientes mecanismos para configurar el comportamiento de aplicaciones de runtime:</span><span class="sxs-lookup"><span data-stu-id="f7296-111">.NET Core provides the following mechanisms for configuring run-time application behavior:</span></span>

- <span data-ttu-id="f7296-112">El [archivo runtimeconfig.json](#runtimeconfigjson)</span><span class="sxs-lookup"><span data-stu-id="f7296-112">The [runtimeconfig.json file](#runtimeconfigjson)</span></span>

- [<span data-ttu-id="f7296-113">Propiedades de MSBuild</span><span class="sxs-lookup"><span data-stu-id="f7296-113">MSBuild properties</span></span>](#msbuild-properties)

- [<span data-ttu-id="f7296-114">Variables de entorno</span><span class="sxs-lookup"><span data-stu-id="f7296-114">Environment variables</span></span>](#environment-variables)

<span data-ttu-id="f7296-115">Algunos valores de configuración también se pueden establecer mediante programación llamando al método <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f7296-115">Some configuration values can also be set programmatically by calling the <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="f7296-116">Los artículos de esta sección de la documentación están organizados por categoría, como, por ejemplo, [depuración](debugging-profiling.md) y [recolección de elementos no utilizados](garbage-collector.md).</span><span class="sxs-lookup"><span data-stu-id="f7296-116">The articles in this section of the documentation are organized by category, for example, [debugging](debugging-profiling.md) and [garbage collection](garbage-collector.md).</span></span> <span data-ttu-id="f7296-117">En su caso, se muestran las opciones de configuración para archivos *runtimeconfig.json*, propiedades de MSBuild, variables de entorno y, para referencias cruzadas, archivos de *app.config* para proyectos de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f7296-117">Where applicable, configuration options are shown for *runtimeconfig.json* files, MSBuild properties, environment variables, and, for cross-reference, *app.config* files for .NET Framework projects.</span></span>

## <a name="runtimeconfigjson"></a><span data-ttu-id="f7296-118">runtimeconfig.json</span><span class="sxs-lookup"><span data-stu-id="f7296-118">runtimeconfig.json</span></span>

<span data-ttu-id="f7296-119">Cuando un proyecto se [compila](../tools/dotnet-build.md), se genera un archivo *[nombre_aplicación].runtimeconfig.json* en el directorio de salida.</span><span class="sxs-lookup"><span data-stu-id="f7296-119">When a project is [built](../tools/dotnet-build.md), an *[appname].runtimeconfig.json* file is generated in the output directory.</span></span> <span data-ttu-id="f7296-120">Si un archivo *runtimeconfig.template.json* existe en la misma carpeta que el archivo de proyecto, las opciones de configuración que contiene se combinan en el archivo *[nombre_aplicación].runtimeconfig.json*.</span><span class="sxs-lookup"><span data-stu-id="f7296-120">If a *runtimeconfig.template.json* file exists in the same folder as the project file, any configuration options it contains are merged into the *[appname].runtimeconfig.json* file.</span></span> <span data-ttu-id="f7296-121">Si va a compilar la aplicación, coloque las opciones de configuración en el archivo *runtimeconfig.template.json*.</span><span class="sxs-lookup"><span data-stu-id="f7296-121">If you're building the app yourself, put any configuration options in the *runtimeconfig.template.json* file.</span></span> <span data-ttu-id="f7296-122">Si solo va a ejecutar la aplicación, insértelas directamente en el archivo *[nombre_aplicación].runtimeconfig.json* file.</span><span class="sxs-lookup"><span data-stu-id="f7296-122">If you're just running the app, insert them directly into the *[appname].runtimeconfig.json* file.</span></span>

> [!NOTE]
> <span data-ttu-id="f7296-123">El archivo *[nombre_aplicación].runtimeconfig.json* se sobrescribirá en las compilaciones posteriores.</span><span class="sxs-lookup"><span data-stu-id="f7296-123">The *[appname].runtimeconfig.json* file will get overwritten on subsequent builds.</span></span>

<span data-ttu-id="f7296-124">Especifique las opciones de configuración de runtime en la sección **configProperties** de los archivos *runtimeconfig.json*.</span><span class="sxs-lookup"><span data-stu-id="f7296-124">Specify run-time configuration options in the **configProperties** section of the *runtimeconfig.json* files.</span></span> <span data-ttu-id="f7296-125">Esta sección tiene el formato siguiente:</span><span class="sxs-lookup"><span data-stu-id="f7296-125">This section has the form:</span></span>

```json
"configProperties": {
  "config-property-name1": "config-value1",
  "config-property-name2": "config-value2"
}
```

### <a name="example-appnameruntimeconfigjson-file"></a><span data-ttu-id="f7296-126">Archivo de ejemplo [nombre_aplicación].runtimeconfig.json</span><span class="sxs-lookup"><span data-stu-id="f7296-126">Example [appname].runtimeconfig.json file</span></span>

<span data-ttu-id="f7296-127">Si va a colocar las opciones en el archivo JSON de salida, anídelas en la propiedad `runtimeOptions`.</span><span class="sxs-lookup"><span data-stu-id="f7296-127">If you're placing the options in the output JSON file, nest them under the `runtimeOptions` property.</span></span>

```json
{
  "runtimeOptions": {
    "tfm": "netcoreapp3.1",
    "framework": {
      "name": "Microsoft.NETCore.App",
      "version": "3.1.0"
    },
    "configProperties": {
      "System.GC.Concurrent": false,
      "System.Threading.ThreadPool.MinThreads": 4,
      "System.Threading.ThreadPool.MaxThreads": 25
    }
  }
}
```

### <a name="example-runtimeconfigtemplatejson-file"></a><span data-ttu-id="f7296-128">Archivo de ejemplo runtimeconfig.template.json</span><span class="sxs-lookup"><span data-stu-id="f7296-128">Example runtimeconfig.template.json file</span></span>

<span data-ttu-id="f7296-129">Si va a colocar las opciones en el archivo JSON de plantilla, omita la propiedad `runtimeOptions`.</span><span class="sxs-lookup"><span data-stu-id="f7296-129">If you're placing the options in the template JSON file, omit the `runtimeOptions` property.</span></span>

```json
{
  "configProperties": {
    "System.GC.Concurrent": false,
    "System.Threading.ThreadPool.MinThreads": "4",
    "System.Threading.ThreadPool.MaxThreads": "25"
  }
}
```

## <a name="msbuild-properties"></a><span data-ttu-id="f7296-130">propiedades de MSBuild</span><span class="sxs-lookup"><span data-stu-id="f7296-130">MSBuild properties</span></span>

<span data-ttu-id="f7296-131">Algunas opciones de configuración de runtime se pueden establecer mediante propiedades de MSBuild en el archivo *.csproj* o *.vbproj* de proyectos de .NET Core de estilo SDK.</span><span class="sxs-lookup"><span data-stu-id="f7296-131">Some run-time configuration options can be set using MSBuild properties in the *.csproj* or *.vbproj* file of SDK-style .NET Core projects.</span></span> <span data-ttu-id="f7296-132">Las propiedades de MSBuild tienen prioridad sobre las opciones establecidas en el archivo *runtimeconfig.template.json*.</span><span class="sxs-lookup"><span data-stu-id="f7296-132">MSBuild properties take precedence over options set in the *runtimeconfig.template.json* file.</span></span> <span data-ttu-id="f7296-133">También sobrescriben las opciones establecidas en el archivo *[nombre_aplicación].runtimeconfig.json* en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="f7296-133">They also overwrite any options you set in the *[appname].runtimeconfig.json* file at build time.</span></span>

<span data-ttu-id="f7296-134">Este es un ejemplo de archivo de proyecto de estilo SDK con propiedades de MSBuild para configurar el comportamiento de runtime:</span><span class="sxs-lookup"><span data-stu-id="f7296-134">Here is an example SDK-style project file with MSBuild properties for configuring run-time behavior:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp3.1</TargetFramework>
  </PropertyGroup>

  <PropertyGroup>
    <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
    <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
    <ThreadPoolMaxThreads>25</ThreadPoolMaxThreads>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="f7296-135">Las propiedades de MSBuild para configurar el comportamiento de runtime se indican en los artículos individuales de cada área, por ejemplo, la [recolección de elementos no utilizados](garbage-collector.md).</span><span class="sxs-lookup"><span data-stu-id="f7296-135">MSBuild properties for configuring run-time behavior are noted in the individual articles for each area, for example, [garbage collection](garbage-collector.md).</span></span>

## <a name="environment-variables"></a><span data-ttu-id="f7296-136">Variables de entorno</span><span class="sxs-lookup"><span data-stu-id="f7296-136">Environment variables</span></span>

<span data-ttu-id="f7296-137">Las variables de entorno se pueden usar para proporcionar información de configuración del entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="f7296-137">Environment variables can be used to supply some run-time configuration information.</span></span> <span data-ttu-id="f7296-138">Los botones de configuración especificados como variables de entorno generalmente tienen el prefijo **COMPlus_** .</span><span class="sxs-lookup"><span data-stu-id="f7296-138">Configuration knobs specified as environment variables generally have the prefix **COMPlus_**.</span></span>

<span data-ttu-id="f7296-139">Puede definir variables de entorno desde el Panel de control de Windows, en la línea de comandos o mediante programación llamando al método <xref:System.Environment.SetEnvironmentVariable(System.String,System.String)?displayProperty=nameWithType> en sistemas basados en Windows y Unix.</span><span class="sxs-lookup"><span data-stu-id="f7296-139">You can define environment variables from the Windows Control Panel, at the command line, or programmatically by calling the <xref:System.Environment.SetEnvironmentVariable(System.String,System.String)?displayProperty=nameWithType> method on both Windows and Unix-based systems.</span></span>

<span data-ttu-id="f7296-140">En los siguientes ejemplos se muestra cómo establecer una variable de entorno en la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="f7296-140">The following examples show how to set an environment variable at the command line:</span></span>

```shell
# Windows
set COMPlus_GCRetainVM=1

# Powershell
$env:COMPlus_GCRetainVM="1"

# Unix
export COMPlus_GCRetainVM=1
```
