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
# <a name="net-core-run-time-configuration-settings"></a><span data-ttu-id="7d0cb-103">Opciones de configuración en tiempo de ejecución de .NET Core</span><span class="sxs-lookup"><span data-stu-id="7d0cb-103">.NET Core run-time configuration settings</span></span>

<span data-ttu-id="7d0cb-104">.NET Core admite el uso de archivos de configuración y variables de entorno para configurar el comportamiento de las aplicaciones .NET Core en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="7d0cb-104">.NET Core supports the use of configuration files and environment variables to configure the behavior of .NET Core applications at run time.</span></span> <span data-ttu-id="7d0cb-105">La configuración en tiempo de ejecución es una opción atractiva si:</span><span class="sxs-lookup"><span data-stu-id="7d0cb-105">Run-time configuration is an attractive option if:</span></span>

- <span data-ttu-id="7d0cb-106">No se posee ni controla el código fuente de una aplicación y, por tanto, no puede configurarlo mediante programación.</span><span class="sxs-lookup"><span data-stu-id="7d0cb-106">You don't own or control the source code for an application and therefore are unable to configure it programmatically.</span></span>

- <span data-ttu-id="7d0cb-107">Varias instancias de la aplicación se ejecutan al mismo tiempo en un solo sistema y se quiere configurar cada una para un rendimiento óptimo.</span><span class="sxs-lookup"><span data-stu-id="7d0cb-107">Multiple instances of your application run at the same time on a single system, and you want to configure each for optimum performance.</span></span>

> [!NOTE]
> <span data-ttu-id="7d0cb-108">Esta documentación está en desarrollo.</span><span class="sxs-lookup"><span data-stu-id="7d0cb-108">This documentation is a work in progress.</span></span> <span data-ttu-id="7d0cb-109">Si observa que la información que se presenta aquí está incompleta o es inexacta, [abra una incidencia](https://github.com/dotnet/docs/issues) para informarnos sobre ella o [envíe una solicitud de incorporación de cambios](https://github.com/dotnet/docs/pulls) para solucionarla.</span><span class="sxs-lookup"><span data-stu-id="7d0cb-109">If you notice that the information presented here is either incomplete or inaccurate, either [open an issue](https://github.com/dotnet/docs/issues) to let us know about it, or [submit a pull request](https://github.com/dotnet/docs/pulls) to address the issue.</span></span> <span data-ttu-id="7d0cb-110">Para obtener información sobre el envío de solicitudes de incorporación de cambios para el repositorio dotnet/docs, consulte la [guía del colaborador](https://github.com/dotnet/docs/blob/master/CONTRIBUTING.md).</span><span class="sxs-lookup"><span data-stu-id="7d0cb-110">For information on submitting pull requests for the dotnet/docs repository, see the [contributor's guide](https://github.com/dotnet/docs/blob/master/CONTRIBUTING.md).</span></span>

<span data-ttu-id="7d0cb-111">.NET Core ofrece los siguientes mecanismos para configurar aplicaciones en tiempo de ejecución:</span><span class="sxs-lookup"><span data-stu-id="7d0cb-111">.NET Core provides the following mechanisms for configuring applications at run time:</span></span>

- <span data-ttu-id="7d0cb-112">El [archivo runtimeconfig.json](#runtimeconfigjson)</span><span class="sxs-lookup"><span data-stu-id="7d0cb-112">The [runtimeconfig.json file](#runtimeconfigjson)</span></span>

- [<span data-ttu-id="7d0cb-113">Variables de entorno</span><span class="sxs-lookup"><span data-stu-id="7d0cb-113">Environment variables</span></span>](#environment-variables)

<span data-ttu-id="7d0cb-114">Los artículos de esta sección de la documentación incluida están organizados por categoría, como, por ejemplo, depuración y recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="7d0cb-114">The articles in this section of the documentation include are organized by category, for example, debugging and garbage collection.</span></span> <span data-ttu-id="7d0cb-115">Si procede, las opciones de configuración disponibles se muestran para *runtimeconfig.json* (solo .NET Core), *app.config* (solo .NET Framework) y las variables de entorno.</span><span class="sxs-lookup"><span data-stu-id="7d0cb-115">Where applicable, configuration options are shown for *runtimeconfig.json* (.NET Core only), *app.config* (.NET Framework only), and environment variables.</span></span>

## <a name="runtimeconfigjson"></a><span data-ttu-id="7d0cb-116">runtimeconfig.json</span><span class="sxs-lookup"><span data-stu-id="7d0cb-116">runtimeconfig.json</span></span>

<span data-ttu-id="7d0cb-117">Especifique las opciones de configuración en tiempo de ejecución en la sección **configProperties** del archivo *runtimeconfig.json* de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7d0cb-117">Specify run-time configuration options in the **configProperties** section of the app's *runtimeconfig.json* file.</span></span> <span data-ttu-id="7d0cb-118">Esta sección tiene el formato siguiente:</span><span class="sxs-lookup"><span data-stu-id="7d0cb-118">This section has the form:</span></span>

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

<span data-ttu-id="7d0cb-119">Aquí tiene un archivo de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="7d0cb-119">Here is an example file:</span></span>

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

<span data-ttu-id="7d0cb-120">El archivo *runtimeconfig.json* se crea automáticamente en el directorio de compilación mediante el comando [dotnet build](../tools/dotnet-build.md).</span><span class="sxs-lookup"><span data-stu-id="7d0cb-120">The *runtimeconfig.json* file is automatically created in the build directory by the [dotnet build](../tools/dotnet-build.md) command.</span></span> <span data-ttu-id="7d0cb-121">También se crea al seleccionar la opción de menú **Compilar** en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7d0cb-121">It's also created when you select the **Build** menu option in Visual Studio.</span></span> <span data-ttu-id="7d0cb-122">Una vez creado, puede editar el archivo.</span><span class="sxs-lookup"><span data-stu-id="7d0cb-122">You can then edit the file once it's created.</span></span>

<span data-ttu-id="7d0cb-123">Algunos valores de configuración también se pueden establecer mediante programación llamando al método <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7d0cb-123">Some configuration values can also be set programmatically by calling the <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> method.</span></span>

## <a name="environment-variables"></a><span data-ttu-id="7d0cb-124">Variables de entorno</span><span class="sxs-lookup"><span data-stu-id="7d0cb-124">Environment variables</span></span>

<span data-ttu-id="7d0cb-125">Las variables de entorno se pueden usar para proporcionar información de configuración del entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="7d0cb-125">Environment variables can be used to supply some run-time configuration information.</span></span> <span data-ttu-id="7d0cb-126">Los botones de configuración especificados como variables de entorno generalmente tienen el prefijo **COMPlus_** .</span><span class="sxs-lookup"><span data-stu-id="7d0cb-126">Configuration knobs specified as environment variables generally have the prefix **COMPlus_**.</span></span>

<span data-ttu-id="7d0cb-127">Puede definir variables de entorno desde el Panel de control de Windows, en la línea de comandos o mediante programación llamando al método <xref:System.Environment.SetEnvironmentVariable(System.String,System.String)?displayProperty=nameWithType> en sistemas basados en Windows y Unix.</span><span class="sxs-lookup"><span data-stu-id="7d0cb-127">You can define environment variables from the Windows Control Panel, at the command line, or programmatically by calling the <xref:System.Environment.SetEnvironmentVariable(System.String,System.String)?displayProperty=nameWithType> method on both Windows and Unix-based systems.</span></span>

<span data-ttu-id="7d0cb-128">En los siguientes ejemplos se muestra cómo establecer una variable de entorno en la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="7d0cb-128">The following examples show how to set an environment variable at the command line:</span></span>

```shell
# Windows
set COMPlus_GCRetainVM=1

# Powershell
$env:COMPlus_GCRetainVM="1"

# Unix
export COMPlus_GCRetainVM=1
```
