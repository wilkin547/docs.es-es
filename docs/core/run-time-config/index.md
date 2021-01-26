---
title: Opciones de configuración de runtime
description: Aprenda a configurar aplicaciones .NET Core mediante opciones de configuración de tiempo de ejecución.
ms.date: 01/21/2020
ms.openlocfilehash: 5e9f292476cf953c3e63bb8e89268f7cc06b3bfc
ms.sourcegitcommit: 2b878d7011306b215dbf3d5dc9c1e78355a6dcd5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/25/2021
ms.locfileid: "98757855"
---
# <a name="net-core-run-time-configuration-settings"></a><span data-ttu-id="d8df0-103">Opciones de configuración en tiempo de ejecución de .NET Core</span><span class="sxs-lookup"><span data-stu-id="d8df0-103">.NET Core run-time configuration settings</span></span>

<span data-ttu-id="d8df0-104">.NET Core admite el uso de archivos de configuración y variables de entorno para configurar el comportamiento de las aplicaciones .NET Core en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="d8df0-104">.NET Core supports the use of configuration files and environment variables to configure the behavior of .NET Core applications at run time.</span></span> <span data-ttu-id="d8df0-105">La configuración en tiempo de ejecución es una opción atractiva si:</span><span class="sxs-lookup"><span data-stu-id="d8df0-105">Run-time configuration is an attractive option if:</span></span>

- <span data-ttu-id="d8df0-106">No se posee ni controla el código fuente de una aplicación y, por tanto, no puede configurarlo mediante programación.</span><span class="sxs-lookup"><span data-stu-id="d8df0-106">You don't own or control the source code for an application and therefore are unable to configure it programmatically.</span></span>

- <span data-ttu-id="d8df0-107">Varias instancias de la aplicación se ejecutan al mismo tiempo en un solo sistema y se quiere configurar cada una para un rendimiento óptimo.</span><span class="sxs-lookup"><span data-stu-id="d8df0-107">Multiple instances of your application run at the same time on a single system, and you want to configure each for optimum performance.</span></span>

> [!NOTE]
> <span data-ttu-id="d8df0-108">Esta documentación está en desarrollo.</span><span class="sxs-lookup"><span data-stu-id="d8df0-108">This documentation is a work in progress.</span></span> <span data-ttu-id="d8df0-109">Si observa que la información que se presenta aquí está incompleta o es inexacta, [abra una incidencia](https://github.com/dotnet/docs/issues) para informarnos sobre ella o [envíe una solicitud de incorporación de cambios](https://github.com/dotnet/docs/pulls) para solucionarla.</span><span class="sxs-lookup"><span data-stu-id="d8df0-109">If you notice that the information presented here is either incomplete or inaccurate, either [open an issue](https://github.com/dotnet/docs/issues) to let us know about it, or [submit a pull request](https://github.com/dotnet/docs/pulls) to address the issue.</span></span> <span data-ttu-id="d8df0-110">Para obtener información sobre el envío de solicitudes de incorporación de cambios para el repositorio dotnet/docs, consulte la [guía del colaborador](/contribute/dotnet/dotnet-contribute).</span><span class="sxs-lookup"><span data-stu-id="d8df0-110">For information about submitting pull requests for the dotnet/docs repository, see the [contributor's guide](/contribute/dotnet/dotnet-contribute).</span></span>

<span data-ttu-id="d8df0-111">.NET Core ofrece los siguientes mecanismos para configurar el comportamiento de las aplicaciones en tiempo de ejecución:</span><span class="sxs-lookup"><span data-stu-id="d8df0-111">.NET Core provides the following mechanisms for configuring application behavior at run time:</span></span>

- <span data-ttu-id="d8df0-112">El [archivo runtimeconfig.json](#runtimeconfigjson)</span><span class="sxs-lookup"><span data-stu-id="d8df0-112">The [runtimeconfig.json file](#runtimeconfigjson)</span></span>

- [<span data-ttu-id="d8df0-113">Propiedades de MSBuild</span><span class="sxs-lookup"><span data-stu-id="d8df0-113">MSBuild properties</span></span>](#msbuild-properties)

- [<span data-ttu-id="d8df0-114">Variables de entorno</span><span class="sxs-lookup"><span data-stu-id="d8df0-114">Environment variables</span></span>](#environment-variables)

> [!TIP]
> <span data-ttu-id="d8df0-115">El hecho de configurar una opción relativa al tiempo de ejecución mediante el uso de una variable de entorno aplica la configuración a todas las aplicaciones de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d8df0-115">Configuring a run-time option by using an environment variable applies the setting to all .NET Core apps.</span></span> <span data-ttu-id="d8df0-116">Sin embargo, si se configura una opción relativa al tiempo de ejecución en *runtimeconfig.json* o en el archivo del proyecto, la configuración solo afectará a la aplicación en cuestión.</span><span class="sxs-lookup"><span data-stu-id="d8df0-116">Configuring a run-time option in the *runtimeconfig.json* or project file applies the setting to that application only.</span></span>

<span data-ttu-id="d8df0-117">Algunos valores de configuración también se pueden establecer mediante programación llamando al método <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d8df0-117">Some configuration values can also be set programmatically by calling the <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="d8df0-118">Los artículos de esta sección de la documentación están organizados por categoría, como, por ejemplo, [depuración](debugging-profiling.md) y [recolección de elementos no utilizados](garbage-collector.md).</span><span class="sxs-lookup"><span data-stu-id="d8df0-118">The articles in this section of the documentation are organized by category, for example, [debugging](debugging-profiling.md) and [garbage collection](garbage-collector.md).</span></span> <span data-ttu-id="d8df0-119">En su caso, se muestran las opciones de configuración para archivos *runtimeconfig.json*, propiedades de MSBuild, variables de entorno y, para referencias cruzadas, archivos de *app.config* para proyectos de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d8df0-119">Where applicable, configuration options are shown for *runtimeconfig.json* files, MSBuild properties, environment variables, and, for cross-reference, *app.config* files for .NET Framework projects.</span></span>

## <a name="runtimeconfigjson"></a><span data-ttu-id="d8df0-120">runtimeconfig.json</span><span class="sxs-lookup"><span data-stu-id="d8df0-120">runtimeconfig.json</span></span>

<span data-ttu-id="d8df0-121">Cuando un proyecto se [compila](../tools/dotnet-build.md), se genera un archivo *[nombre_aplicación].runtimeconfig.json* en el directorio de salida.</span><span class="sxs-lookup"><span data-stu-id="d8df0-121">When a project is [built](../tools/dotnet-build.md), an *[appname].runtimeconfig.json* file is generated in the output directory.</span></span> <span data-ttu-id="d8df0-122">Si un archivo *runtimeconfig.template.json* existe en la misma carpeta que el archivo de proyecto, las opciones de configuración que contiene se insertan en el archivo *[nombre_aplicación].runtimeconfig.json*.</span><span class="sxs-lookup"><span data-stu-id="d8df0-122">If a *runtimeconfig.template.json* file exists in the same folder as the project file, any configuration options it contains are inserted into the *[appname].runtimeconfig.json* file.</span></span> <span data-ttu-id="d8df0-123">Si va a compilar la aplicación, coloque las opciones de configuración en el archivo *runtimeconfig.template.json*.</span><span class="sxs-lookup"><span data-stu-id="d8df0-123">If you're building the app yourself, put any configuration options in the *runtimeconfig.template.json* file.</span></span> <span data-ttu-id="d8df0-124">Si solo va a ejecutar la aplicación, insértelas directamente en el archivo *[nombre_aplicación].runtimeconfig.json* file.</span><span class="sxs-lookup"><span data-stu-id="d8df0-124">If you're just running the app, insert them directly into the *[appname].runtimeconfig.json* file.</span></span>

> [!NOTE]
> <span data-ttu-id="d8df0-125">El archivo *[nombre_aplicación].runtimeconfig.json* se sobrescribirá en las compilaciones posteriores.</span><span class="sxs-lookup"><span data-stu-id="d8df0-125">The *[appname].runtimeconfig.json* file will get overwritten on subsequent builds.</span></span>

<span data-ttu-id="d8df0-126">Especifique las opciones de configuración de runtime en la sección **configProperties** de los archivos *runtimeconfig.json*.</span><span class="sxs-lookup"><span data-stu-id="d8df0-126">Specify run-time configuration options in the **configProperties** section of the *runtimeconfig.json* files.</span></span> <span data-ttu-id="d8df0-127">Esta sección tiene el formato siguiente:</span><span class="sxs-lookup"><span data-stu-id="d8df0-127">This section has the form:</span></span>

```json
"configProperties": {
  "config-property-name1": "config-value1",
  "config-property-name2": "config-value2"
}
```

### <a name="example-appnameruntimeconfigjson-file"></a><span data-ttu-id="d8df0-128">Archivo de ejemplo [nombre_aplicación].runtimeconfig.json</span><span class="sxs-lookup"><span data-stu-id="d8df0-128">Example [appname].runtimeconfig.json file</span></span>

<span data-ttu-id="d8df0-129">Si va a colocar las opciones en el archivo JSON de salida, anídelas en la propiedad `runtimeOptions`.</span><span class="sxs-lookup"><span data-stu-id="d8df0-129">If you're placing the options in the output JSON file, nest them under the `runtimeOptions` property.</span></span>

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

### <a name="example-runtimeconfigtemplatejson-file"></a><span data-ttu-id="d8df0-130">Archivo de ejemplo runtimeconfig.template.json</span><span class="sxs-lookup"><span data-stu-id="d8df0-130">Example runtimeconfig.template.json file</span></span>

<span data-ttu-id="d8df0-131">Si va a colocar las opciones en el archivo JSON de plantilla, omita la propiedad `runtimeOptions`.</span><span class="sxs-lookup"><span data-stu-id="d8df0-131">If you're placing the options in the template JSON file, omit the `runtimeOptions` property.</span></span>

```json
{
  "configProperties": {
    "System.GC.Concurrent": false,
    "System.Threading.ThreadPool.MinThreads": "4",
    "System.Threading.ThreadPool.MaxThreads": "25"
  }
}
```

## <a name="msbuild-properties"></a><span data-ttu-id="d8df0-132">propiedades de MSBuild</span><span class="sxs-lookup"><span data-stu-id="d8df0-132">MSBuild properties</span></span>

<span data-ttu-id="d8df0-133">Algunas opciones de configuración de runtime se pueden establecer mediante propiedades de MSBuild en el archivo *.csproj* o *.vbproj* de proyectos de .NET Core de estilo SDK.</span><span class="sxs-lookup"><span data-stu-id="d8df0-133">Some run-time configuration options can be set using MSBuild properties in the *.csproj* or *.vbproj* file of SDK-style .NET Core projects.</span></span> <span data-ttu-id="d8df0-134">Las propiedades de MSBuild tienen prioridad sobre las opciones establecidas en el archivo *runtimeconfig.template.json*.</span><span class="sxs-lookup"><span data-stu-id="d8df0-134">MSBuild properties take precedence over options set in the *runtimeconfig.template.json* file.</span></span>

<span data-ttu-id="d8df0-135">Este es un ejemplo de archivo de proyecto de estilo SDK con propiedades de MSBuild para configurar el comportamiento de runtime:</span><span class="sxs-lookup"><span data-stu-id="d8df0-135">Here is an example SDK-style project file with MSBuild properties for configuring run-time behavior:</span></span>

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

<span data-ttu-id="d8df0-136">Las propiedades de MSBuild para configurar el comportamiento de runtime se indican en los artículos individuales de cada área, por ejemplo, la [recolección de elementos no utilizados](garbage-collector.md).</span><span class="sxs-lookup"><span data-stu-id="d8df0-136">MSBuild properties for configuring run-time behavior are noted in the individual articles for each area, for example, [garbage collection](garbage-collector.md).</span></span> <span data-ttu-id="d8df0-137">También se enumeran en la sección sobre la [configuración del tiempo de ejecución](../project-sdk/msbuild-props.md#run-time-configuration-properties) de la referencia de las propiedades de MSBuild para los proyectos de estilo de SDK.</span><span class="sxs-lookup"><span data-stu-id="d8df0-137">They are also listed in the [Run-time configuration](../project-sdk/msbuild-props.md#run-time-configuration-properties) section of the MSBuild properties reference for SDK-style projects.</span></span>

## <a name="environment-variables"></a><span data-ttu-id="d8df0-138">Variables de entorno</span><span class="sxs-lookup"><span data-stu-id="d8df0-138">Environment variables</span></span>

<span data-ttu-id="d8df0-139">Las variables de entorno se pueden usar para proporcionar información de configuración del entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="d8df0-139">Environment variables can be used to supply some run-time configuration information.</span></span> <span data-ttu-id="d8df0-140">El hecho de configurar una opción relativa al tiempo de ejecución mediante el uso de una variable de entorno aplica la configuración a todas las aplicaciones de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d8df0-140">Configuring a run-time option by using an environment variable applies the setting to all .NET Core apps.</span></span> <span data-ttu-id="d8df0-141">Los botones de configuración especificados como variables de entorno generalmente tienen el prefijo **COMPlus_** .</span><span class="sxs-lookup"><span data-stu-id="d8df0-141">Configuration knobs specified as environment variables generally have the prefix **COMPlus_**.</span></span>

<span data-ttu-id="d8df0-142">Puede definir variables de entorno desde el Panel de control de Windows, en la línea de comandos o mediante programación llamando al método <xref:System.Environment.SetEnvironmentVariable(System.String,System.String)?displayProperty=nameWithType> en sistemas basados en Windows y Unix.</span><span class="sxs-lookup"><span data-stu-id="d8df0-142">You can define environment variables from the Windows Control Panel, at the command line, or programmatically by calling the <xref:System.Environment.SetEnvironmentVariable(System.String,System.String)?displayProperty=nameWithType> method on both Windows and Unix-based systems.</span></span>

<span data-ttu-id="d8df0-143">En los siguientes ejemplos se muestra cómo establecer una variable de entorno en la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="d8df0-143">The following examples show how to set an environment variable at the command line:</span></span>

```shell
# Windows
set COMPlus_GCRetainVM=1

# Powershell
$env:COMPlus_GCRetainVM="1"

# Unix
export COMPlus_GCRetainVM=1
```
