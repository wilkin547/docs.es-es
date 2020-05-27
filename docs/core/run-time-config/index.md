---
title: Opciones de configuración de runtime
description: Aprenda a configurar aplicaciones .NET Core mediante opciones de configuración de tiempo de ejecución.
ms.date: 01/21/2020
ms.openlocfilehash: 68690689fd4f936e3af76ab647f0b58d8ec6ca27
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2020
ms.locfileid: "83761959"
---
# <a name="net-core-run-time-configuration-settings"></a>Opciones de configuración en tiempo de ejecución de .NET Core

.NET Core admite el uso de archivos de configuración y variables de entorno para configurar el comportamiento de las aplicaciones .NET Core en tiempo de ejecución. La configuración en tiempo de ejecución es una opción atractiva si:

- No se posee ni controla el código fuente de una aplicación y, por tanto, no puede configurarlo mediante programación.

- Varias instancias de la aplicación se ejecutan al mismo tiempo en un solo sistema y se quiere configurar cada una para un rendimiento óptimo.

> [!NOTE]
> Esta documentación está en desarrollo. Si observa que la información que se presenta aquí está incompleta o es inexacta, [abra una incidencia](https://github.com/dotnet/docs/issues) para informarnos sobre ella o [envíe una solicitud de incorporación de cambios](https://github.com/dotnet/docs/pulls) para solucionarla. Para obtener información sobre el envío de solicitudes de incorporación de cambios para el repositorio dotnet/docs, consulte la [guía del colaborador](https://docs.microsoft.com/contribute/dotnet/dotnet-contribute).

.NET Core ofrece los siguientes mecanismos para configurar el comportamiento de las aplicaciones en tiempo de ejecución:

- El [archivo runtimeconfig.json](#runtimeconfigjson)

- [Propiedades de MSBuild](#msbuild-properties)

- [Variables de entorno](#environment-variables)

> [!TIP]
> El hecho de configurar una opción relativa al tiempo de ejecución mediante el uso de una variable de entorno aplica la configuración a todas las aplicaciones de .NET Core. Sin embargo, si se configura una opción relativa al tiempo de ejecución en *runtimeconfig.json* o en el archivo del proyecto, la configuración solo afectará a la aplicación en cuestión.

Algunos valores de configuración también se pueden establecer mediante programación llamando al método <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType>.

Los artículos de esta sección de la documentación están organizados por categoría, como, por ejemplo, [depuración](debugging-profiling.md) y [recolección de elementos no utilizados](garbage-collector.md). En su caso, se muestran las opciones de configuración para archivos *runtimeconfig.json*, propiedades de MSBuild, variables de entorno y, para referencias cruzadas, archivos de *app.config* para proyectos de .NET Framework.

## <a name="runtimeconfigjson"></a>runtimeconfig.json

Cuando un proyecto se [compila](../tools/dotnet-build.md), se genera un archivo *[nombre_aplicación].runtimeconfig.json* en el directorio de salida. Si un archivo *runtimeconfig.template.json* existe en la misma carpeta que el archivo de proyecto, las opciones de configuración que contiene se combinan en el archivo *[nombre_aplicación].runtimeconfig.json*. Si va a compilar la aplicación, coloque las opciones de configuración en el archivo *runtimeconfig.template.json*. Si solo va a ejecutar la aplicación, insértelas directamente en el archivo *[nombre_aplicación].runtimeconfig.json* file.

> [!NOTE]
> El archivo *[nombre_aplicación].runtimeconfig.json* se sobrescribirá en las compilaciones posteriores.

Especifique las opciones de configuración de runtime en la sección **configProperties** de los archivos *runtimeconfig.json*. Esta sección tiene el formato siguiente:

```json
"configProperties": {
  "config-property-name1": "config-value1",
  "config-property-name2": "config-value2"
}
```

### <a name="example-appnameruntimeconfigjson-file"></a>Archivo de ejemplo [nombre_aplicación].runtimeconfig.json

Si va a colocar las opciones en el archivo JSON de salida, anídelas en la propiedad `runtimeOptions`.

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

### <a name="example-runtimeconfigtemplatejson-file"></a>Archivo de ejemplo runtimeconfig.template.json

Si va a colocar las opciones en el archivo JSON de plantilla, omita la propiedad `runtimeOptions`.

```json
{
  "configProperties": {
    "System.GC.Concurrent": false,
    "System.Threading.ThreadPool.MinThreads": "4",
    "System.Threading.ThreadPool.MaxThreads": "25"
  }
}
```

## <a name="msbuild-properties"></a>propiedades de MSBuild

Algunas opciones de configuración de runtime se pueden establecer mediante propiedades de MSBuild en el archivo *.csproj* o *.vbproj* de proyectos de .NET Core de estilo SDK. Las propiedades de MSBuild tienen prioridad sobre las opciones establecidas en el archivo *runtimeconfig.template.json*. También sobrescriben las opciones establecidas en el archivo *[nombre_aplicación].runtimeconfig.json* en tiempo de compilación.

Este es un ejemplo de archivo de proyecto de estilo SDK con propiedades de MSBuild para configurar el comportamiento de runtime:

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

Las propiedades de MSBuild para configurar el comportamiento de runtime se indican en los artículos individuales de cada área, por ejemplo, la [recolección de elementos no utilizados](garbage-collector.md). También se enumeran en la sección sobre la [configuración del tiempo de ejecución](../project-sdk/msbuild-props.md#run-time-configuration-properties) de la referencia de las propiedades de MSBuild para los proyectos de estilo de SDK.

## <a name="environment-variables"></a>Variables de entorno

Las variables de entorno se pueden usar para proporcionar información de configuración del entorno de ejecución. El hecho de configurar una opción relativa al tiempo de ejecución mediante el uso de una variable de entorno aplica la configuración a todas las aplicaciones de .NET Core. Los botones de configuración especificados como variables de entorno generalmente tienen el prefijo **COMPlus_** .

Puede definir variables de entorno desde el Panel de control de Windows, en la línea de comandos o mediante programación llamando al método <xref:System.Environment.SetEnvironmentVariable(System.String,System.String)?displayProperty=nameWithType> en sistemas basados en Windows y Unix.

En los siguientes ejemplos se muestra cómo establecer una variable de entorno en la línea de comandos:

```shell
# Windows
set COMPlus_GCRetainVM=1

# Powershell
$env:COMPlus_GCRetainVM="1"

# Unix
export COMPlus_GCRetainVM=1
```
