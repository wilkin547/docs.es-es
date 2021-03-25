---
title: Seguimiento de aplicaciones de .NET con PerfCollect.
description: Tutorial en el que se le guía través de la recopilación de un seguimiento con perfcollect en .NET.
ms.topic: tutorial
ms.date: 10/23/2020
ms.openlocfilehash: 20e1bf56714fb32b5231d45b0ba35cdfcedaea2e
ms.sourcegitcommit: e3cf8227573e13b8e1f4e3dc007404881cdafe47
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/11/2021
ms.locfileid: "103189935"
---
# <a name="trace-net-applications-with-perfcollect"></a>Seguimiento de aplicaciones de .NET con PerfCollect

**Este artículo se aplica a: ✔️** SDK de .NET Core 2.1 y versiones posteriores

Cuando se producen problemas de rendimiento en Linux, la recopilación de un seguimiento con `perfcollect` se puede usar para recopilar información detallada sobre lo que ocurre en el equipo en el momento del problema de rendimiento.

`perfcollect` es un script de bash que aprovecha [Linux Tracing Tookit-Next Generation (LTTng)](https://lttng.org), el kit de herramientas de seguimiento de Linux de próxima generación, para recopilar eventos escritos en el entorno de ejecución o cualquier elemento [EventSource](xref:System.Diagnostics.Tracing.EventListener), así como [perf](https://perf.wiki.kernel.org/) para recopilar ejemplos de CPU del proceso de destino.

## <a name="prepare-your-machine"></a>Preparación del equipo

Siga estos pasos para preparar el equipo a fin de recopilar un seguimiento de rendimiento con `perfcollect`.

> [!NOTE]
> Si está en un entorno de contenedor, el contenedor debe tener la funcionalidad `SYS_ADMIN`. Para obtener más información sobre el seguimiento de aplicaciones dentro de contenedores con PerfCollect, vea [Recopilación de diagnósticos en contenedores](./diagnostics-in-containers.md).

1. Descargue `perfcollect`.

    > ```bash
    > curl -OL https://aka.ms/perfcollect
    > ```

2. Haga que el script sea ejecutable.

    > ```bash
    > chmod +x perfcollect
    > ```

3. Instale los requisitos previos de seguimiento; son las bibliotecas de seguimiento reales.

    > ```bash
    > sudo ./perfcollect install
    > ```

    Esto instalará los siguientes requisitos previos en el equipo:

    1. `perf`: subsistema de eventos de rendimiento de Linux y aplicación complementaria del visor o recopilación de modo de usuario. `perf` forma parte del origen del kernel de Linux, pero normalmente no se instala de forma predeterminada.

    2. `LTTng`: se usa para capturar datos de eventos emitidos en tiempo de ejecución por CoreCLR. Después, estos datos se usan para analizar el comportamiento de varios componentes del entorno de ejecución, como el GC, JIT y el grupo de subprocesos.

Las versiones recientes de .NET Core y la herramienta perf de Linux admiten la resolución automática de nombres de método para el código del marco. Si trabaja con la versión 3.1 o anterior de .NET Core, se necesita un paso adicional. Para obtener más información, vea [Resolución de símbolos de marco](#resolve-framework-symbols).

Para resolver los nombres de métodos de archivos DLL nativos del entorno de ejecución (como libcoreclr.so), `perfcollect` resolverá sus símbolos al convertir los datos, pero solo si los símbolos de estos archivos binarios están presentes. Para obtener más información, vea la sección [Obtención de símbolos para el entorno de ejecución nativo](#get-symbols-for-the-native-runtime).

## <a name="collect-a-trace"></a>Recopilación de un seguimiento

1. Debe tener dos shells disponibles: uno para controlar el seguimiento, denominado **[Trace]** , y otro para ejecutar la aplicación, denominado **[App]** .

2. **[Trace]** Inicie la recolección.

    > ```bash
    > sudo ./perfcollect collect sampleTrace
    > ```

    Salida esperada:

    > ```bash
    > Collection started.  Press CTRL+C to stop.
    > ```

3. **[App]** Configure el shell de aplicaciones con las variables de entorno siguientes; esto habilita la configuración de seguimiento de CoreCLR.

    > ```bash
    > export COMPlus_PerfMapEnabled=1
    > export COMPlus_EnableEventLog=1
    > ```

4. **[App]** Ejecute la aplicación; permita que se ejecute siempre que sea necesario para capturar el problema de rendimiento. La longitud exacta puede ser tan breve como sea necesario, siempre y cuando capture el período de tiempo en el que se produce el problema de rendimiento que se quiere investigar.

    > ```bash
    > dotnet run
    > ```

5. **[Trace]** Detenga la recolección; presione Ctrl + C.

    > ```bash
    > ^C
    > ...STOPPED.
    >
    > Starting post-processing. This may take some time.
    >
    > Generating native image symbol files
    > ...SKIPPED
    > Saving native symbols
    > ...FINISHED
    > Exporting perf.data file
    > ...FINISHED
    > Compressing trace files
    > ...FINISHED
    > Cleaning up artifacts
    > ...FINISHED
    >
    > Trace saved to sampleTrace.trace.zip
    > ```

    Ahora el archivo de seguimiento comprimido se almacena en el directorio de trabajo actual.

## <a name="view-a-trace"></a>Visualización de un seguimiento

Hay una serie de opciones para ver el seguimiento que se ha recopilado. Los seguimientos se ven mejor con [PerfView](https://aka.ms/perfview) en Windows, pero se pueden ver directamente en Linux mediante el propio `PerfCollect` o `TraceCompass`.

### <a name="use-perfcollect-to-view-the-trace-file"></a>Uso de PerfCollect para ver el archivo de seguimiento

Puede usar perfcollect para ver el seguimiento que se ha recopilado. Para ello, ejecute el siguiente comando:

```bash
./perfcollect view sampleTrace.trace.zip
```

De forma predeterminada, se mostrará el seguimiento de la CPU de la aplicación mediante `perf`.

Para examinar los eventos recopilados a través de `LTTng`, puede pasar la marca `-viewer lttng` a fin de ver los eventos individuales:

```bash
./perfcollect view sampleTrace.trace.zip -viewer lttng
```

Se usará el visor `babeltrace` para imprimir la carga de eventos:

```bash
# [01:02:18.189217659] (+0.020132603) ubuntu-xenial DotNETRuntime:ExceptionThrown_V1: { cpu_id = 0 }, { ExceptionType = "System.Exception", ExceptionMessage = "An exception happened", ExceptionEIP = 139875671834775, ExceptionHRESULT = 2148734208, ExceptionFlags = 16, ClrInstanceID = 0 }
# [01:02:18.189250227] (+0.020165171) ubuntu-xenial DotNETRuntime:ExceptionCatchStart: { cpu_id = 0 }, { EntryEIP = 139873639728404, MethodID = 139873626968120, MethodName = "void [helloworld] helloworld.Program::Main(string[])", ClrInstanceID = 0 }
```

### <a name="use-perfview-to-open-the-trace-file"></a>Uso de PerfView para abrir el archivo de seguimiento

Para ver una vista agregada del ejemplo de CPU y de los eventos, puede usar `PerfView` en un equipo Windows.

1. Copie el archivo trace.zip de Linux en un equipo Windows.

2. Descargue PerfView de <https://aka.ms/perfview>.

3. Ejecución de PerfView.exe

    > ```cmd
    > PerfView.exe <path to trace.zip file>
    > ```

PerfView mostrará la lista de vistas que se admiten en función de los datos contenidos en el archivo de seguimiento.

- Para las investigaciones de CPU, elija **CPU stacks** (Pilas de CPU).

- Para obtener información detallada sobre la recolección de elementos no utilizados, elija **GCStats**.

- Para obtener información de JIT en función de un proceso, módulo o método, elija **JITStats**.

- Si no hay ninguna vista de la información que necesita, puede intentar buscar los eventos en la vista de eventos sin procesar.  Elija **Events** (Eventos).

Para obtener más información sobre cómo interpretar las vistas en PerfView, vea los vínculos de ayuda en la propia vista, o bien elija **Help > Users Guide** (Ayuda > Guía de usuarios) en la ventana principal de PerfView.

> [!NOTE]
> Los eventos escritos mediante la API <xref:System.Diagnostics.Tracing.EventSource?displayProperty=nameWithType> (incluidos los de Framework) no se mostrarán bajo el nombre de su proveedor. En su lugar, se escriben como eventos `EventSourceEvent` en el proveedor `Microsoft-Windows-DotNETRuntime` y sus cargas se serializan en JSON.

### <a name="use-tracecompass-to-open-the-trace-file"></a>Uso de TraceCompass para abrir el archivo de seguimiento

[Eclipse TraceCompass](https://www.eclipse.org/tracecompass/) es otra opción que puede usar para ver los seguimientos. `TraceCompass` también funciona en equipos Linux, por lo que no es necesario trasladar el seguimiento a un equipo Windows. Para usar `TraceCompass` y abrir el archivo de seguimiento, tendrá que descomprimirlo.

```bash
unzip myTrace.trace.zip
```

`perfcollect` guardará el seguimiento de LTTng que ha recopilado en un formato de archivo CTF en un subdirectorio de `lttngTrace`. En concreto, el archivo CTF se ubicará en un directorio como `lttngTrace/auto-20201025-101230\ust\uid\1000\64-bit\`.

Puede abrir el archivo de seguimiento CTF en `TraceCompass` si selecciona `File -> Open Trace` y, después, el archivo `metadata`.

Para obtener más información, consulte la [documentación de `TraceCompass`](https://www.eclipse.org/tracecompass/).

## <a name="resolve-framework-symbols"></a>Resolución de símbolos de marco

Los símbolos de marco se deben generar manualmente en el momento de recopilar el seguimiento. Son diferentes de los símbolos de nivel de aplicación porque el marco se compila previamente, mientras que el código de la aplicación se compila Just-In-Time. Para el código de marco precompilado en código nativo, debe llamar a `crossgen`, que sabe cómo generar la asignación desde el código nativo al nombre de los métodos.

`perfcollect` puede administrar de forma automática la mayoría de los detalles, pero debe tener `crossgen` disponible. De forma predeterminada, no se instala con la distribución de .NET. Si `crossgen` no está presente, `perfcollect` muestra una advertencia y le remite a estas instrucciones. Para corregirlo todo, tendrá que capturar exactamente la versión correcta de crossgen para el entorno de ejecución que use. Si coloca la herramienta crossgen en el mismo directorio que los archivos DLL del entorno de ejecución de .NET (por ejemplo, libcoreclr.so), `perfcollect` puede encontrarla y agregar de forma automática los símbolos de marco al archivo de seguimiento.

Normalmente, al crear una aplicación de .NET, genera el archivo DLL para el código que se ha escrito y usa una copia compartida del entorno de ejecución para el resto.   Pero también puede generar lo que se denomina una versión "independiente" de una aplicación, que contendrá todos los archivos DLL del entorno de ejecución. `crossgen` forma parte del paquete NuGet que se usa para crear aplicaciones independientes, por lo que una manera de obtener la versión correcta de `crossgen` es crear un paquete independiente de la aplicación.

Por ejemplo:

   >```bash
   > mkdir helloWorld
   > cd helloWorld
   > dotnet new console
   > dotnet publish --self-contained -r linux-x64
   >```

Esto crea una aplicación Hola mundo y la compila como una aplicación independiente.

Como efecto secundario de la creación de la aplicación independiente, la herramienta dotnet descargará un paquete NuGet denominado runtime.linux-x64.microsoft.netcore.app y lo colocará en el directorio ~/.nuget/packages/runtime.linux-x64.microsoft.netcore.app/VERSIÓN, donde VERSIÓN es el número de versión del entorno de ejecución de .NET Core (por ejemplo, 2.1.0). En él hay un directorio de herramientas, que contiene la herramienta crossgen que necesita. A partir de .NET Core 3.0, la ubicación del paquete es ~/.nuget/packages/microsoft.netcore.app.runtime.linux-x64/VERSIÓN.

La herramienta `crossgen` se debe colocar junto al entorno de ejecución que se usa realmente en la aplicación. Normalmente, la aplicación usa la versión compartida de .NET Core que se instala en /usr/share/dotnet/shared/Microsoft.NETCore.App/VERSIÓN, donde VERSIÓN es el número de versión del entorno de ejecución de .NET. Se trata de una ubicación compartida, por lo que debe ser superusuario para modificarla. Si VERSIÓN es 2.1.0, los comandos para actualizar `crossgen` serían los siguientes:

   >```bash
   > sudo bash
   > cp ~/.nuget/packages/runtime.linux-x64.microsoft.netcore.app/2.1.0/tools/crossgen /usr/share/dotnet/shared/Microsoft.NETCore.App/2.1.0
   >```

Una vez que haya hecho esto, `perfcollect` usará crossgen para incluir símbolos de marco. La advertencia que `perfcollect` solía emitir debería desaparecer. Esto solo debe pasar una vez por equipo (hasta que actualice el entorno de ejecución).

### <a name="alternative-turn-off-use-of-precompiled-code"></a>Alternativa: Desactivación del uso de código precompilado

Si no tiene la capacidad de actualizar el entorno de ejecución de .NET (para agregar `crossgen`), o bien si el procedimiento anterior no ha funcionado por algún motivo, hay otro enfoque para obtener los símbolos de marco. Puede indicarle al entorno de ejecución que simplemente no use el código de marco precompilado. El código se compilará Just-In-Time y `crossgen` no será necesario.

> [!NOTE]
> La elección de este enfoque puede aumentar el tiempo de inicio de la aplicación.

Para hacerlo, puede agregar la siguiente variable de entorno:

```bash
export COMPlus_ZapDisable=1
```

Con este cambio, debería obtener los símbolos para todo el código de .NET.

## <a name="get-symbols-for-the-native-runtime"></a>Obtención de símbolos para el entorno de ejecución nativo

En la mayoría de los casos le interesará el código propio, que `perfcollect` resuelve de forma predeterminada. En ocasiones resulta útil ver lo que ocurre dentro de los archivos DLL de .NET (el objetivo de la última sección), pero a veces es interesante lo que sucede en los archivos DLL del entorno de ejecución nativo (normalmente libcoreclr.so).  `perfcollect` resolverá los símbolos para estos archivos DLL al convertir sus datos, pero solo si los símbolos están presentes (y cerca de la biblioteca para la que están destinados).

Hay un comando global denominado [dotnet-symbol](https://github.com/dotnet/symstore/blob/master/src/dotnet-symbol/README.md#symbol-downloader-dotnet-cli-extension) que se encarga de ello. Para usar dotnet-symbol a fin de obtener símbolos del entorno de ejecución nativo:

1. Instale `dotnet-symbol`:

    ```bash
    dotnet tool install -g dotnet-symbol
    ```

2. Descargue los símbolos. Si la versión instalada del entorno de ejecución de .NET Core es la 2.1.0, el comando para hacerlo es el siguiente:

    ```bash
    mkdir mySymbols
    dotnet symbol --symbols --output mySymbols  /usr/share/dotnet/shared/Microsoft.NETCore.App/2.1.0/lib*.so
    ```

3. Copie los símbolos en el lugar correcto.

    ```bash
    sudo cp mySymbols/* /usr/share/dotnet/shared/Microsoft.NETCore.App/2.1.0
    ```

    Si no lo puede hacer porque no tiene acceso de escritura al directorio adecuado, puede usar `perf buildid-cache` para agregar los símbolos.

Después, debe obtener nombres simbólicos para los archivos DLL nativos al ejecutar `perfcollect`.

## <a name="collect-in-a-docker-container"></a>Recopilación en un contenedor de Docker

Para obtener más información sobre cómo usar `perfcollect` en entornos de contenedor, vea [Recopilación de diagnósticos en contenedores](./diagnostics-in-containers.md).

## <a name="learn-more-about-collection-options"></a>Más información sobre las opciones de recopilación

Puede especificar las siguientes marcas opcionales con `perfcollect` para que se adapte mejor a sus necesidades de diagnóstico.

### <a name="collect-for-a-specific-duration"></a>Recopilación con una duración específica

Si quiere recopilar un seguimiento con una duración específica, puede usar la opción `-collectsec` seguida de un número que especifique el total de segundos durante los que se va a recopilar el seguimiento.

### <a name="collect-threadtime-traces"></a>Recopilación de seguimientos de tiempo de subproceso

Si especifica `-threadtime` con `perfcollect`, podrá recopilar datos de uso de CPU por subproceso. Esto le permite analizar el lugar en el que está consumiendo su tiempo de CPU cada subproceso.

### <a name="collect-traces-for-managed-memory-and-garbage-collector-performance"></a>Recopilación de seguimientos de memoria administrada y rendimiento del recolector de elementos no utilizados

Las siguientes opciones le permiten recopilar específicamente los eventos de GC del entorno de ejecución.

* `perfcollect collect -gccollectonly`

Recopile solo un conjunto mínimo de eventos de recopilación de GC. Este es el perfil de recopilación de eventos de GC menos detallado y con el menor impacto en el rendimiento de la aplicación de destino. Este comando es análogo al comando `PerfView.exe /GCCollectOnly collect` en PerfView.

* `perfcollect collect -gconly`

Recopile eventos de recopilación de GC más detallados con eventos JIT, Loader y de excepción. Esto solicita eventos más detallados (como la información de asignación y la información de combinación de GC) y tendrá un impacto mayor en el rendimiento de la aplicación de destino que la opción `-gccollectonly`. Este comando es análogo al comando `PerfView.exe /GCOnly collect` en PerfView.

* `perfcollect collect -gcwithheap`

Recopile los eventos de recopilación de GC más detallados; incluye también un seguimiento de los movimientos y la supervivencia del montón. Esto proporciona un análisis exhaustivo del comportamiento del GC, pero incurrirá en un costo de alto rendimiento, ya que cada GC puede tardar más del doble. Es recomendable que comprenda la implicación del rendimiento del uso de esta opción de seguimiento cuando realice el seguimiento en entornos de producción.
