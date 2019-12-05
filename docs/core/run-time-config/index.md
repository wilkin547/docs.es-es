---
title: Configuración del tiempo de ejecución
description: Aprenda a configurar aplicaciones .NET Core mediante opciones de configuración de tiempo de ejecución.
ms.date: 11/13/2019
ms.openlocfilehash: 2665026347e94d26026821beb2bfcf8441f755f6
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2019
ms.locfileid: "74801918"
---
# <a name="net-core-run-time-configuration-settings"></a>Opciones de configuración en tiempo de ejecución de .NET Core

.NET Core admite el uso de archivos de configuración y variables de entorno para configurar el comportamiento de las aplicaciones .NET Core en tiempo de ejecución. La configuración en tiempo de ejecución es una opción atractiva si:

- No se posee ni controla el código fuente de una aplicación y, por tanto, no puede configurarlo mediante programación.

- Varias instancias de la aplicación se ejecutan al mismo tiempo en un solo sistema y se quiere configurar cada una para un rendimiento óptimo.

> [!NOTE]
> Esta documentación está en desarrollo. Si observa que la información que se presenta aquí está incompleta o es inexacta, [abra una incidencia](https://github.com/dotnet/docs/issues) para informarnos sobre ella o [envíe una solicitud de incorporación de cambios](https://github.com/dotnet/docs/pulls) para solucionarla. Para obtener información sobre el envío de solicitudes de incorporación de cambios para el repositorio dotnet/docs, consulte la [guía del colaborador](https://github.com/dotnet/docs/blob/master/CONTRIBUTING.md).

.NET Core ofrece los siguientes mecanismos para configurar aplicaciones en tiempo de ejecución:

- El [archivo runtimeconfig.json](#runtimeconfigjson)

- [Variables de entorno](#environment-variables)

Los artículos de esta sección de la documentación incluida están organizados por categoría, como, por ejemplo, depuración y recolección de elementos no utilizados. Si procede, las opciones de configuración disponibles se muestran para *runtimeconfig.json* (solo .NET Core), *app.config* (solo .NET Framework) y las variables de entorno.

## <a name="runtimeconfigjson"></a>runtimeconfig.json

Especifique las opciones de configuración en tiempo de ejecución en la sección **configProperties** del archivo *runtimeconfig.json* de la aplicación. Esta sección tiene el formato siguiente:

```json
{
   "runtimeOptions": {
      "configProperties": {
         "config-property-name1": "config-value1",
         "config-property-name2": "config-value2"
      }
   }
}
```

Aquí tiene un archivo de ejemplo:

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Concurrent": true,
         "System.GC.RetainVM": true,
         "System.Threading.ThreadPool.MinThreads": "4",
         "System.Threading.ThreadPool.MaxThreads": "25"
      }
   }
}
```

El archivo *runtimeconfig.json* se crea automáticamente en el directorio de compilación mediante el comando [dotnet build](../tools/dotnet-build.md). También se crea al seleccionar la opción de menú **Compilar** en Visual Studio. Una vez creado, puede editar el archivo.

Algunos valores de configuración también se pueden establecer mediante programación llamando al método <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType>.

## <a name="environment-variables"></a>Variables de entorno

Las variables de entorno se pueden usar para proporcionar información de configuración del entorno de ejecución. Los botones de configuración especificados como variables de entorno generalmente tienen el prefijo **COMPlus_** .

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
