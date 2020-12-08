---
title: 'Depuración del uso elevado de CPU: .NET Core'
description: Tutorial que le guiará a lo largo del proceso de depuración del uso elevado de CPU en .NET Core.
ms.topic: tutorial
ms.date: 07/20/2020
ms.openlocfilehash: 91f31f77b54398d2f9816890338955bc9b0852e4
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2020
ms.locfileid: "96437835"
---
# <a name="debug-high-cpu-usage-in-net-core"></a>Depuración del uso elevado de CPU en .NET Core

**Este artículo se aplica a: ✔️** SDK de .NET Core 3.1 y versiones posteriores

En este tutorial, aprenderá a depurar un escenario de uso excesivo de CPU. Con el repositorio de código fuente de ejemplo proporcionado, [Aplicación web de ASP.NET Core](/samples/dotnet/samples/diagnostic-scenarios), puede provocar un interbloqueo de forma intencionada. El punto de conexión experimentará un bloqueo y una acumulación de subprocesos. Aprenderá a usar diversas herramientas para diagnosticar este escenario con varios elementos clave de datos de diagnóstico.

En este tutorial va a:

> [!div class="checklist"]
>
> - Investigar el uso elevado de CPU
> - Determinar el uso de CPU con [dotnet-counters](dotnet-counters.md)
> - Usar [dotnet-trace](dotnet-trace.md) para la generación de seguimiento
> - Realizar perfiles de rendimiento en PerfView
> - Diagnosticar y resolver el uso excesivo de CPU

## <a name="prerequisites"></a>Requisitos previos

En el tutorial se usa:

- [SDK de .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core) o una versión posterior
- [Destino de depuración de ejemplo](/samples/dotnet/samples/diagnostic-scenarios) para desencadenar el escenario
- [dotnet-trace](dotnet-trace.md) para enumerar los procesos y generar un perfil
- [dotnet-counters](dotnet-counters.md) para supervisar el uso de la CPU

## <a name="cpu-counters"></a>Contadores de CPU

Antes de intentar recopilar datos de diagnóstico, debe observar una condición de CPU alta. Ejecute la [aplicación de ejemplo](/samples/dotnet/samples/diagnostic-scenarios) mediante el siguiente comando desde el directorio raíz del proyecto.

```dotnetcli
dotnet run
```

Para encontrar el identificador de proceso, use el comando siguiente:

```dotnetcli
dotnet-trace ps
```

Anote el identificador de proceso de la salida del comando. El identificador de proceso era `22884`, pero el suyo será diferente. Para comprobar el uso de CPU actual, use el comando de la herramienta [dotnet-counters](dotnet-counters.md):

```dotnetcli
dotnet-counters monitor --refresh-interval 1 -p 22884
```

`refresh-interval` es el número de segundos entre los valores de CPU de sondeo de contador. La salida debe ser similar a la siguiente:

```console
Press p to pause, r to resume, q to quit.
    Status: Running

[System.Runtime]
    % Time in GC since last GC (%)                         0
    Allocation Rate / 1 sec (B)                            0
    CPU Usage (%)                                          0
    Exception Count / 1 sec                                0
    GC Heap Size (MB)                                      4
    Gen 0 GC Count / 60 sec                                0
    Gen 0 Size (B)                                         0
    Gen 1 GC Count / 60 sec                                0
    Gen 1 Size (B)                                         0
    Gen 2 GC Count / 60 sec                                0
    Gen 2 Size (B)                                         0
    LOH Size (B)                                           0
    Monitor Lock Contention Count / 1 sec                  0
    Number of Active Timers                                1
    Number of Assemblies Loaded                          140
    ThreadPool Completed Work Item Count / 1 sec           3
    ThreadPool Queue Length                                0
    ThreadPool Thread Count                                7
    Working Set (MB)                                      63
```

Con la aplicación web en ejecución, inmediatamente después del inicio, no se consume CPU en absoluto y se muestra `0%`. Vaya a la ruta `api/diagscenario/highcpu` con `60000` como parámetro de ruta:

`https://localhost:5001/api/diagscenario/highcpu/60000`

Ahora, vuelva a ejecutar el comando [dotnet-counters](dotnet-counters.md). Para supervisar solo `cpu-usage`, especifique `System.Runtime[cpu-usage]` como parte del comando.

```dotnetcli
dotnet-counters monitor --counters System.Runtime[cpu-usage] -p 22884 --refresh-interval 1
```

Debería ver un aumento en el uso de CPU, como se muestra a continuación:

```console
Press p to pause, r to resume, q to quit.
    Status: Running

[System.Runtime]
    CPU Usage (%)                                         25
```

Durante toda la solicitud, el uso de CPU rondará en torno al 25 %. En función del equipo host, se espera un uso de CPU variable.

> [!TIP]
> Para visualizar un uso de CPU incluso mayor, puede ejecutar este punto de conexión simultáneamente en varias pestañas del explorador.

En este momento, puede afirmar con seguridad que el uso de CPU es mayor del esperado.

## <a name="trace-generation"></a>Generación de seguimiento

Al analizar una solicitud lenta, necesita una herramienta de diagnóstico que pueda proporcionar información sobre lo que hace el código. Lo habitual es optar por un generador de perfiles. Existen diferentes opciones de generador de perfiles entre las que elegir.

### <a name="linux"></a>[Linux](#tab/linux)

La herramienta `perf` se puede usar para generar perfiles de aplicaciones .NET Core. Salga de la instancia anterior del [destino de depuración de ejemplo](/samples/dotnet/samples/diagnostic-scenarios).

Establezca la variable de entorno `COMPlus_PerfMapEnabled` para que la aplicación .NET Core cree un archivo `map` en el directorio `/tmp`. `perf` usa este archivo `map` para asignar la dirección de CPU a las funciones generadas por JIT por nombre. Para obtener más información, consulte [Escritura del mapa de rendimiento](../run-time-config/debugging-profiling.md#write-perf-map).

Ejecute el [destino de depuración de ejemplo](/samples/dotnet/samples/diagnostic-scenarios) en la misma sesión de terminal.

```dotnetcli
export COMPlus_PerfMapEnabled=1
dotnet run
```

Ejecute de nuevo el punto de conexión de la API de uso elevado de CPU (`https://localhost:5001/api/diagscenario/highcpu/60000`). Mientras se ejecuta en la solicitud de 1 minuto, ejecute el comando `perf` con el identificador de proceso:

```bash
sudo perf record -p 2266 -g
```

El comando `perf` inicia el proceso de recopilación de rendimiento. Deje que se ejecute durante unos 20 o 30 segundos y, luego, presione <kbd>Ctrl+C</kbd> para salir del proceso de recopilación. Puede usar el mismo comando `perf` para ver la salida del seguimiento.

```bash
sudo perf report -f
```

También puede generar un _gráfico de llamas_ mediante los comandos siguientes:

```bash
git clone --depth=1 https://github.com/BrendanGregg/FlameGraph
sudo perf script | FlameGraph/stackcollapse-perf.pl | FlameGraph/flamegraph.pl > flamegraph.svg
```

Este comando genera un archivo `flamegraph.svg` que puede ver en el explorador para investigar el problema de rendimiento:

[![Imagen SVG del gráfico de llamas](media/flamegraph.jpg)](media/flamegraph.jpg#lightbox)

### <a name="windows"></a>[Windows](#tab/windows)

En Windows, puede usar la herramienta [dotnet-trace](dotnet-trace.md) como generador de perfiles. Con el anterior [destino de depuración de ejemplo](/samples/dotnet/samples/diagnostic-scenarios), ejecute de nuevo el punto de conexión de uso elevado de CPU (`https://localhost:5001/api/diagscenario/highcpu/60000`). Mientras se ejecuta en la solicitud de 1 minuto, ejecute el comando `collect` como se indica a continuación:

```dotnetcli
dotnet-trace collect -p 22884 --providers Microsoft-DotNETCore-SampleProfiler
```

Deje que [dotnet-trace](dotnet-trace.md) se ejecute durante unos 20 o 30 segundos y, luego, presione la tecla <kbd>ENTRAR</kbd> para salir de la recopilación. El resultado es un archivo `nettrace` ubicado en la misma carpeta. Los archivos `nettrace` son una excelente manera de usar las herramientas de análisis existentes en Windows.

Abra `nettrace` con [`PerfView`](https://github.com/microsoft/perfview/blob/master/documentation/Downloading.md) como se muestra a continuación.

[![Imagen de PerfView](media/perfview.jpg)](media/perfview.jpg#lightbox)

---

## <a name="see-also"></a>Consulte también

- [dotnet-trace](dotnet-trace.md) para mostrar procesos
- [dotnet-counters](dotnet-counters.md) para comprobar el uso de memoria administrada
- [dotnet-dump](dotnet-dump.md) para recopilar y analizar un archivo de volcado de memoria
- [dotnet/diagnostics](https://github.com/dotnet/diagnostics/tree/master/documentation/tutorial)

## <a name="next-steps"></a>Pasos siguientes

> [!div class="nextstepaction"]
> [Depuración de un interbloqueo en .NET Core](debug-deadlock.md)
