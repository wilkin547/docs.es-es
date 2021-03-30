---
title: Recopilación de información detallada de carga de ensamblados - .NET Core
description: Descripción de cómo recopilar información de carga de ensamblados en .NET Core
author: elinor-fung
ms.author: elfung
ms.date: 11/17/2020
ms.openlocfilehash: 505fc827021fe4d34675b2ef5a7fc5746ada1af6
ms.sourcegitcommit: c7f0beaa2bd66ebca86362ca17d673f7e8256ca6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104872943"
---
# <a name="collect-detailed-assembly-loading-information"></a>Recopilación de información detallada de carga de ensamblados

A partir de .NET 5.0, el entorno de ejecución puede emitir eventos a través de `EventPipe` con información detallada sobre la [carga de ensamblados administrados](loading-managed.md) como ayuda para diagnosticar problemas en la carga de ensamblados. El proveedor `Microsoft-Windows-DotNETRuntime` emite estos [eventos](../../fundamentals/diagnostics/runtime-loader-binder-events.md) bajo la palabra clave `AssemblyLoader` (`0x4`).

## <a name="prerequisites"></a>Requisitos previos

- [SDK de .NET 5.0](https://dotnet.microsoft.com/download) o versiones posteriores
- Herramienta [dotnet-trace](../diagnostics/dotnet-trace.md)

## <a name="collect-a-trace-with-assembly-loading-events"></a>Recopilación de un seguimiento con eventos de carga de ensamblados

Para habilitar los eventos de carga de ensamblados en el entorno de ejecución y recopilar un seguimiento de ellos, use `dotnet-trace` con el siguiente comando:

```console
dotnet-trace collect --providers Microsoft-Windows-DotNETRuntime:4 --process-id <pid>
```

Esto recopilará un seguimiento del `<pid>` especificado, habilitando los eventos `AssemblyLoader` en el proveedor `Microsoft-Windows-DotNETRuntime`. El resultado es un archivo `.nettrace`.

## <a name="view-a-trace"></a>Visualización de un seguimiento

El archivo de seguimiento recopilado se puede ver en Windows mediante la vista Eventos en [PerfView](https://github.com/microsoft/perfview). Todos los eventos de carga de ensamblados tendrán como prefijo `Microsoft-Windows-DotNETRuntime/AssemblyLoader`.

## <a name="example-on-windows"></a>Ejemplo (en Windows)

En este ejemplo se usa el [ejemplo de puntos de extensión de la carga de ensamblados](https://docs.microsoft.com/samples/dotnet/samples/assembly-loading-extension-points/). La aplicación intenta cargar un ensamblado `MyLibrary`; un ensamblado al que no hace referencia la aplicación y, por tanto, requiere el control en un punto de extensión de carga de ensamblados para que se cargue correctamente.

### <a name="collect-the-trace"></a>Recopilación del seguimiento

01. Navegue hasta el directorio con el ejemplo descargado. Compile la aplicación:

    ```console
    dotnet build
    ```

01. Inicie la aplicación con argumentos que indiquen que debe hacer una pausa, a la espera de que se presione una tecla. Al reanudar la operación, intentará cargar el ensamblado en el `AssemblyLoadContext` predeterminado, sin el control necesario para una carga correcta. Navegue hasta el directorio de salida y ejecute:

    ```console
    AssemblyLoading.exe /d default
    ```

01. Busque el identificador de proceso de la aplicación.

    ```console
    dotnet-trace ps
    ```

    En la salida se enumerarán los procesos disponibles. Por ejemplo:

    ```console
    35832 AssemblyLoading C:\src\AssemblyLoading\bin\Debug\net5.0\AssemblyLoading.exe
    ```

01. Adjunte `dotnet-trace` a la aplicación en ejecución.

    ```console
    dotnet-trace collect --providers Microsoft-Windows-DotNETRuntime:4 --process-id 35832
    ```

01. En la ventana que ejecuta la aplicación, presione cualquier tecla para dejar que el programa continúe. El seguimiento se detendrá automáticamente una vez que se cierre la aplicación.

### <a name="view-the-trace"></a>Visualización del seguimiento

Abra el seguimiento recopilado en [PerfView](https://github.com/microsoft/perfview) y abra la vista Eventos. Filtre la lista de eventos para eventos `Microsoft-Windows-DotNETRuntime/AssemblyLoader`.

:::image type="content" source="media/collect-details/assembly-loader-filter.png" alt-text="Imagen del filtro del cargador de ensamblados de PerfView":::

Se mostrarán todas las cargas de ensamblado que se produjeron en la aplicación después del inicio del seguimiento. Para inspeccionar la operación de carga para el ensamblado de interés para este ejemplo (`MyLibrary`), podemos seguir filtrando.

### <a name="assembly-loads"></a>Cargas de ensamblado

Filtre la vista por los eventos [`Start`](../../fundamentals/diagnostics/runtime-loader-binder-events.md#assemblyloadstart-event) y [`Stop`](../../fundamentals/diagnostics/runtime-loader-binder-events.md#assemblyloadstop-event) en `Microsoft-Windows-DotNETRuntime/AssemblyLoader` con la lista de eventos de la izquierda. Agregue las columnas `AssemblyName`, `ActivityID` y `Success` a la vista. Filtre los eventos que contienen `MyLibrary`.

:::image type="content" source="media/collect-details/start-stop.png" alt-text="Imagen de inicio y detención de eventos de PerfView":::

| Nombre del evento             | AssemblyName                                      | Identificador de actividad | Correcto |
| ---------------------- | ------------------------------------------------- | ---------- | ------- |
| `AssemblyLoader/Start` | `MyLibrary, Culture=neutral, PublicKeyToken=null` | //1/2/     |         |
| `AssemblyLoader/Stop`  | `MyLibrary, Culture=neutral, PublicKeyToken=null` | //1/2/     | False   |

Debería ver un par `Start`/`Stop` con `Success=False` en el evento `Stop`, lo cual indica que se ha producido un error en la operación de carga. Tenga en cuenta que los dos eventos tienen el mismo identificador de actividad. El identificador de actividad se puede usar para filtrar todos los demás eventos del cargador de ensamblados a solo los que corresponden a esta operación de carga.

### <a name="breakdown-of-attempt-to-load"></a>Desglose del intento de carga

Para obtener un desglose más detallado de la operación de carga, filtre la vista por los [eventos `ResolutionAttempted`](../../fundamentals/diagnostics/runtime-loader-binder-events.md#resolutionattempted-event) bajo `Microsoft-Windows-DotNETRuntime/AssemblyLoader` mediante la lista de eventos de la izquierda. Agregue las columnas `AssemblyName`, `Stage` y `Result` a la vista. Filtre los eventos con el identificador de actividad del par `Start`/`Stop`.

:::image type="content" source="media/collect-details/resolution-attempted.png" alt-text="Imagen de eventos ResolutionAttempted de PerfView":::

| Nombre del evento                           | AssemblyName                                      | Fase                               | Resultado             |
| ------------------------------------ | ------------------------------------------------- | ----------------------------------- | ------------------ |
| `AssemblyLoader/ResolutionAttempted` | `MyLibrary, Culture=neutral, PublicKeyToken=null` | `FindInLoadContext`                 | `AssemblyNotFound` |
| `AssemblyLoader/ResolutionAttempted` | `MyLibrary, Culture=neutral, PublicKeyToken=null` | `ApplicationAssemblies`             | `AssemblyNotFound` |
| `AssemblyLoader/ResolutionAttempted` | `MyLibrary, Culture=neutral, PublicKeyToken=null` | `AssemblyLoadContextResolvingEvent` | `AssemblyNotFound` |
| `AssemblyLoader/ResolutionAttempted` | `MyLibrary, Culture=neutral, PublicKeyToken=null` | `AppDomainAssemblyResolveEvent`     | `AssemblyNotFound` |

Los eventos anteriores indican que el cargador de ensamblados intentó resolver el ensamblado examinando el contexto de carga actual, ejecutando la lógica de sondeo predeterminada para los ensamblados de aplicación administrados, invocando controladores para el evento <xref:System.Runtime.Loader.AssemblyLoadContext.Resolving?displayProperty=nameWithType> e invocando controladores para <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>. En todos estos pasos, no se encontró el ensamblado.

### <a name="extension-points"></a>Puntos de extensión

Para ver los puntos de extensión que se invocaron, filtre la vista a [`AssemblyLoadContextResolvingHandlerInvoked`](../../fundamentals/diagnostics/runtime-loader-binder-events.md#assemblyloadcontextresolvinghandlerinvoked-event) y [`AppDomainAssemblyResolveHandlerInvoked`](../../fundamentals/diagnostics/runtime-loader-binder-events.md#appdomainassemblyresolvehandlerinvoked-event) en `Microsoft-Windows-DotNETRuntime/AssemblyLoader` mediante la lista de eventos de la izquierda. Agregue las columnas `AssemblyName` y `HandlerName` a la vista. Filtre los eventos con el identificador de actividad del par `Start`/`Stop`.

:::image type="content" source="media/collect-details/extension-point.png" alt-text="Imagen de eventos de punto de extensión de PerfView":::

| Nombre del evento                                                  | AssemblyName                                      | HandlerName                      |
| ----------------------------------------------------------- | ------------------------------------------------- | -------------------------------- |
| `AssemblyLoader/AssemblyLoadContextResolvingHandlerInvoked` | `MyLibrary, Culture=neutral, PublicKeyToken=null` | `OnAssemblyLoadContextResolving` |
| `AssemblyLoader/AppDomainAssemblyResolveHandlerInvoked`     | `MyLibrary, Culture=neutral, PublicKeyToken=null` | `OnAppDomainAssemblyResolve`     |

Los eventos anteriores indican que se invocó un controlador con el nombre `OnAssemblyLoadContextResolving` para el evento <xref:System.Runtime.Loader.AssemblyLoadContext.Resolving?displayProperty=nameWithType> y que se invocó un controlador denominado `OnAppDomainAssemblyResolve` para el evento <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>.

### <a name="collect-another-trace"></a>Recopilación de otro seguimiento

Ejecute la aplicación con argumentos de modo que su controlador para el evento <xref:System.Runtime.Loader.AssemblyLoadContext.Resolving?displayProperty=nameWithType> cargue el ensamblado `MyLibrary`.

```console
AssemblyLoading /d default alc-resolving
```

Recopile y abra otro archivo `.nettrace` con los [pasos anteriores](#collect-the-trace).

Filtre de nuevo a los eventos `Start` y `Stop` de `MyLibrary`. Debería ver un par `Start`/`Stop` con otro `Start`/`Stop` entre ellos. La operación de carga interna representa la carga desencadenada por el controlador para <xref:System.Runtime.Loader.AssemblyLoadContext.Resolving?displayProperty=nameWithType> cuando llamó a <xref:System.Runtime.Loader.AssemblyLoadContext.LoadFromAssemblyPath%2A?displayProperty=nameWithType>. Esta vez, debería ver `Success=True` en el evento `Stop`, lo cual indica que la operación de carga se realizó correctamente. En el campo `ResultAssemblyPath` se muestra la ruta de acceso del ensamblado resultante.

:::image type="content" source="media/collect-details/start-stop-success.png" alt-text="Imagen de inicio y detención de eventos correctos de PerfView":::

| Nombre del evento             | AssemblyName                                                       | Identificador de actividad | Correcto | ResultAssemblyPath                                      |
| ---------------------- | ------------------------------------------------------------------ |------------|---------| ------------------------------------------------------- |
| `AssemblyLoader/Start` |                  `MyLibrary, Culture=neutral, PublicKeyToken=null` | //1/2/     |         |                                                         |
| `AssemblyLoader/Start` | `MyLibrary, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null` | //1/2/1/   |         |                                                         |
| `AssemblyLoader/Stop`  | `MyLibrary, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null` | //1/2/1/   | True    | *C:\src\AssemblyLoading\bin\Debug\net5.0\MyLibrary.dll* |
| `AssemblyLoader/Stop`  |                  `MyLibrary, Culture=neutral, PublicKeyToken=null` | //1/2/     | True    | *C:\src\AssemblyLoading\bin\Debug\net5.0\MyLibrary.dll* |

A continuación, podemos examinar los eventos `ResolutionAttempted` con el identificador de actividad de la carga externa para determinar el paso en el que el ensamblado se resolvió correctamente. Esta vez, los eventos mostrarán que la fase `AssemblyLoadContextResolvingEvent` se ha realizado correctamente. En el campo `ResultAssemblyPath` se muestra la ruta de acceso del ensamblado resultante.

:::image type="content" source="media/collect-details/resolution-attempted-success.png" alt-text="Imagen de eventos ResolutionAttempted correctos de PerfView":::

| Nombre del evento                           | AssemblyName                                      | Fase                               | Resultado             | ResultAssemblyPath |
| ------------------------------------ | ------------------------------------------------- | ----------------------------------- | ------------------ | ------------------ |
| `AssemblyLoader/ResolutionAttempted` | `MyLibrary, Culture=neutral, PublicKeyToken=null` | `FindInLoadContext`                 | `AssemblyNotFound` |                    |
| `AssemblyLoader/ResolutionAttempted` | `MyLibrary, Culture=neutral, PublicKeyToken=null` | `ApplicationAssemblies`             | `AssemblyNotFound` |                    |
| `AssemblyLoader/ResolutionAttempted` | `MyLibrary, Culture=neutral, PublicKeyToken=null` | `AssemblyLoadContextResolvingEvent` | `Success`          | *C:\src\AssemblyLoading\bin\Debug\net5.0\MyLibrary.dll* |

Al fijarse en los eventos `AssemblyLoadContextResolvingHandlerInvoked`, verá que se invocó el controlador denominado `OnAssemblyLoadContextResolving`. El campo `ResultAssemblyPath` muestra la ruta de acceso del ensamblado devuelto por el controlador.

:::image type="content" source="media/collect-details/extension-point-success.png" alt-text="Imagen de eventos de punto de extensión correcto de PerfView":::

| Nombre del evento                                                  | AssemblyName                                      | HandlerName                      | ResultAssemblyPath |
| ----------------------------------------------------------- | ------------------------------------------------- | -------------------------------- | ------------------ |
| `AssemblyLoader/AssemblyLoadContextResolvingHandlerInvoked` | `MyLibrary, Culture=neutral, PublicKeyToken=null` | `OnAssemblyLoadContextResolving` | *C:\src\AssemblyLoading\bin\Debug\net5.0\MyLibrary.dll* |

Tenga en cuenta que ya no hay un evento `ResolutionAttempted` con la fase `AppDomainAssemblyResolveEvent` ni eventos `AppDomainAssemblyResolveHandlerInvoked`, ya que el ensamblado se cargó correctamente antes de alcanzar el paso del algoritmo de carga que genera el evento <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType>.

## <a name="see-also"></a>Vea también

- [Eventos del cargador de ensamblados](../../fundamentals/diagnostics/runtime-loader-binder-events.md)
- [dotnet-trace](../diagnostics/dotnet-trace.md)
- [PerfView](https://github.com/microsoft/perfview)
