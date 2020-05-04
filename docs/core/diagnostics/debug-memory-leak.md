---
title: Tutorial Depuración de una fuga de memoria
description: Obtenga información sobre cómo depurar una fuga de memoria en .NET Core.
ms.topic: tutorial
ms.date: 04/20/2020
ms.openlocfilehash: d47992bab9dab64cf7f88ff679eef407dd891b5a
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2020
ms.locfileid: "82021360"
---
# <a name="tutorial-debug-a-memory-leak-in-net-core"></a>Tutorial: Depuración de una fuga de memoria en .NET Core

**Este artículo se aplica a:** ✔️ SDK de .NET Core 3.0 y versiones posteriores

En este tutorial se muestran las herramientas para analizar una fuga de memoria de .NET Core.

En este tutorial se usa una aplicación de ejemplo, diseñada para perder memoria de manera intencionada. El ejemplo se proporciona como ejercicio. Asimismo, puede analizar una aplicación que pierda memoria involuntariamente.

En este tutorial va a:

> [!div class="checklist"]
>
> - Examinar el uso de memoria administrada con [dotnet-counters](dotnet-counters.md).
> - Generar un archivo de volcado de memoria.
> - Analizar el uso de memoria mediante el archivo de volcado de memoria.

## <a name="prerequisites"></a>Requisitos previos

En el tutorial se usa:

- [SDK de .NET Core 3.0](https://dotnet.microsoft.com/download/dotnet-core) o una versión posterior.
- [dotnet-trace](dotnet-trace.md) para mostrar procesos.
- [dotnet-counters](dotnet-counters.md) para comprobar el uso de memoria administrada.
- [dotnet-dump](dotnet-dump.md) para recopilar y analizar un archivo de volcado de memoria.
- Una aplicación de [destino de depuración de ejemplo](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios/) que se va a diagnosticar.

En el tutorial se da por supuesto que el ejemplo y las herramientas están instalados y listos para usarse.

## <a name="examine-managed-memory-usage"></a>Análisis del uso de memoria administrada

Antes de empezar a recopilar datos de diagnóstico que nos ayuden a establecer la causa principal de este escenario, debe asegurarse de que realmente está viendo una fuga de memoria (crecimiento de memoria). Puede usar la herramienta [dotnet-counters](dotnet-counters.md) para confirmar eso.

Abra una ventana de consola y vaya al directorio donde descargó y descomprimió el [destino de depuración de ejemplo](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios/). Ejecute el destino:

```dotnetcli
dotnet run
```

En una consola independiente, busque el identificador del proceso mediante la herramienta [dotnet-trace](dotnet-trace.md):

```console
dotnet-trace ps
```

La salida debe ser similar a:

```console
4807 DiagnosticScena /home/user/git/samples/core/diagnostics/DiagnosticScenarios/bin/Debug/netcoreapp3.0/DiagnosticScenarios
```

Ahora, compruebe el uso de memoria administrada con la herramienta [dotnet-counters](dotnet-counters.md). `--refresh-interval` especifica el número de segundos entre las actualizaciones:

```console
dotnet-counters monitor --refresh-interval 1 -p 4807
```

La salida en directo debe ser similar a:

```console
Press p to pause, r to resume, q to quit.
    Status: Running

[System.Runtime]
    # of Assemblies Loaded                           118
    % Time in GC (since last GC)                       0
    Allocation Rate (Bytes / sec)                 37,896
    CPU Usage (%)                                      0
    Exceptions / sec                                   0
    GC Heap Size (MB)                                  4
    Gen 0 GC / sec                                     0
    Gen 0 Size (B)                                     0
    Gen 1 GC / sec                                     0
    Gen 1 Size (B)                                     0
    Gen 2 GC / sec                                     0
    Gen 2 Size (B)                                     0
    LOH Size (B)                                       0
    Monitor Lock Contention Count / sec                0
    Number of Active Timers                            1
    ThreadPool Completed Work Items / sec             10
    ThreadPool Queue Length                            0
    ThreadPool Threads Count                           1
    Working Set (MB)                                  83
```

Establecimiento del foco en esta línea:

```console
    GC Heap Size (MB)                                  4
```

Puede ver que la memoria de montón administrado es de 4 MB justo después del inicio.

Ahora, visite la dirección URL `http://localhost:5000/api/diagscenario/memleak/20000`.

Observe que el uso de memoria ha aumentado a 30 MB.

```console
    GC Heap Size (MB)                                 30
```

Al observar el uso de memoria, puede indicar con seguridad el aumento o la fuga de memoria. El siguiente paso consiste en recopilar los datos adecuados para el análisis de memoria.

### <a name="generate-memory-dump"></a>Generación de un volcado de memoria

Al analizar posibles fugas de memoria, debe tener acceso al montón de memoria de la aplicación. A continuación, puede analizar el contenido de la memoria. Al observarse las relaciones entre los objetos, se crean teorías de por qué no se libera la memoria. Un origen de datos de diagnóstico habitual es un volcado de memoria en Windows o el volcado de memoria principal equivalente en Linux. Para generar un volcado de memoria de una aplicación .NET Core, puede usar la herramienta [dotnet-dump)](dotnet-dump.md).

Con el [destino de depuración de ejemplo](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios/) iniciado anteriormente, ejecute el siguiente comando para generar un volcado de memoria principal de Linux:

```dotnetcli
dotnet-dump collect -p 4807
```

El resultado es un volcado de memoria principal ubicado en la misma carpeta.

```console
Writing minidump with heap to ./core_20190430_185145
Complete
```

### <a name="restart-the-failed-process"></a>Reinicio del proceso con errores

Una vez recopilado el volcado de memoria, debe tener suficiente información para diagnosticar el proceso con errores. Si el proceso con errores se ejecuta en un servidor de producción, ahora es el momento ideal para la corrección a corto plazo reiniciando el proceso.

En este tutorial, ya ha terminado con el [destino de depuración de ejemplo](https://docs.microsoft.com/samples/dotnet/samples/diagnostic-scenarios/) y puede cerrarlo. Vaya al terminal que inició el servidor y presione `Control-C`.

### <a name="analyze-the-core-dump"></a>Análisis del volcado de memoria principal

Ahora que ha generado un volcado de memoria principal, use la herramienta [dotnet-dump](dotnet-dump.md) para analizar el volcado de memoria:

```dotnetcli
dotnet-dump analyze core_20190430_185145
```

Donde `core_20190430_185145` es el nombre del volcado de memoria principal que desea analizar.

> [!NOTE]
> Si ve un error que indica que no se encuentra *libdl.so*, es posible que tenga que instalar el paquete *libc6-dev*. Para más información, consulte [Requisitos previos para .NET Core en Linux](../install/dependencies.md?pivots=os-linux).

Se le mostrará un mensaje en el que puede escribir comandos SOS. Normalmente, lo primero que desea ver es el estado general del montón administrado:

```console
> dumpheap -stat

Statistics:
              MT    Count    TotalSize Class Name
...
00007f6c1eeefba8      576        59904 System.Reflection.RuntimeMethodInfo
00007f6c1dc021c8     1749        95696 System.SByte[]
00000000008c9db0     3847       116080      Free
00007f6c1e784a18      175       128640 System.Char[]
00007f6c1dbf5510      217       133504 System.Object[]
00007f6c1dc014c0      467       416464 System.Byte[]
00007f6c21625038        6      4063376 testwebapi.Controllers.Customer[]
00007f6c20a67498   200000      4800000 testwebapi.Controllers.Customer
00007f6c1dc00f90   206770     19494060 System.String
Total 428516 objects
```

Aquí puede ver que la mayoría de los objetos son objetos `String` o `Customer`.

Puede volver a usar el comando `dumpheap` con la tabla del método (MT) para obtener una lista de todas las instancias de `String`:

```console
> dumpheap -mt 00007faddaa50f90

         Address               MT     Size
...
00007f6ad09421f8 00007faddaa50f90       94
...
00007f6ad0965b20 00007f6c1dc00f90       80
00007f6ad0965c10 00007f6c1dc00f90       80
00007f6ad0965d00 00007f6c1dc00f90       80
00007f6ad0965df0 00007f6c1dc00f90       80
00007f6ad0965ee0 00007f6c1dc00f90       80

Statistics:
              MT    Count    TotalSize Class Name
00007f6c1dc00f90   206770     19494060 System.String
Total 206770 objects
```

Ahora puede usar el comando `gcroot` en una instancia de `System.String` para ver cómo y por qué se considera raíz el objeto. Tenga paciencia, ya que este comando tarda varios minutos con un montón de 30 MB:

```console
> gcroot -all 00007f6ad09421f8

Thread 3f68:
    00007F6795BB58A0 00007F6C1D7D0745 System.Diagnostics.Tracing.CounterGroup.PollForValues() [/_/src/System.Private.CoreLib/shared/System/Diagnostics/Tracing/CounterGroup.cs @ 260]
        rbx:  (interior)
            ->  00007F6BDFFFF038 System.Object[]
            ->  00007F69D0033570 testwebapi.Controllers.Processor
            ->  00007F69D0033588 testwebapi.Controllers.CustomerCache
            ->  00007F69D00335A0 System.Collections.Generic.List`1[[testwebapi.Controllers.Customer, DiagnosticScenarios]]
            ->  00007F6C000148A0 testwebapi.Controllers.Customer[]
            ->  00007F6AD0942258 testwebapi.Controllers.Customer
            ->  00007F6AD09421F8 System.String

HandleTable:
    00007F6C98BB15F8 (pinned handle)
    -> 00007F6BDFFFF038 System.Object[]
    -> 00007F69D0033570 testwebapi.Controllers.Processor
    -> 00007F69D0033588 testwebapi.Controllers.CustomerCache
    -> 00007F69D00335A0 System.Collections.Generic.List`1[[testwebapi.Controllers.Customer, DiagnosticScenarios]]
    -> 00007F6C000148A0 testwebapi.Controllers.Customer[]
    -> 00007F6AD0942258 testwebapi.Controllers.Customer
    -> 00007F6AD09421F8 System.String

Found 2 roots.
```

Puede ver que el objeto `Customer` mantiene directamente `String` y un objeto `CustomerCache` lo hace indirectamente.

Puede seguir volcando objetos para ver que la mayoría de los objetos `String` siguen un patrón similar. En este punto, la investigación proporcionó suficiente información para identificar la causa principal en su código.

Este procedimiento general le permite identificar el origen de las principales fugas de memoria.

## <a name="clean-up-resources"></a>Limpiar los recursos

En este tutorial, inició un servidor web de ejemplo. Este servidor debería haberse apagado como se explica en la sección [Reinicio del proceso con errores](#restart-the-failed-process).

También puede eliminar el archivo de volcado de memoria que se creó.

## <a name="next-steps"></a>Pasos siguientes

Enhorabuena por completar este tutorial.

Todavía estamos publicando más tutoriales de diagnóstico. Puede leer las versiones de borrador en el repositorio [dotnet/diagnostics](https://github.com/dotnet/diagnostics/tree/master/documentation/tutorial).

En este tutorial se han tratado los aspectos básicos de las herramientas de diagnóstico de .NET clave. Para el uso avanzado, consulte la siguiente documentación de referencia:

* [dotnet-trace](dotnet-trace.md) para mostrar procesos.
* [dotnet-counters](dotnet-counters.md) para comprobar el uso de memoria administrada.
* [dotnet-dump](dotnet-dump.md) para recopilar y analizar un archivo de volcado de memoria.
