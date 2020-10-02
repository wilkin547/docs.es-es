---
title: Escritura de un host en tiempo de ejecución personalizado de .NET Core
description: Obtenga información sobre cómo hospedar el entorno de tiempo de ejecución de .NET Core desde código nativo para admitir escenarios avanzados que necesitan controlar cómo funciona dicho entorno.
author: mjrousos
ms.topic: how-to
ms.date: 12/21/2018
ms.openlocfilehash: 03cf188fc74e8a70798c0bcc4a6940730abfc07c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91180469"
---
# <a name="write-a-custom-net-core-host-to-control-the-net-runtime-from-your-native-code"></a>Escritura de un host personalizado de .NET Core para controlar el entorno de tiempo de ejecución de .NET desde el código nativo

Como todo el código administrado, las aplicaciones de .NET Core se ejecutan mediante un host. El host es responsable de iniciar el entorno de ejecución (incluidos componentes como el JIT y el recolector de elementos no utilizados) y de invocar puntos de entrada administrados.

Hospedar el runtime de .NET Core es un escenario avanzado y, en la mayoría de los casos, los desarrolladores de .NET Core no necesitan preocuparse sobre el hospedaje porque los procesos de compilación de .NET Core proporcionan un host predeterminado para ejecutar aplicaciones de .NET Core. En cambio, en algunas circunstancias especializadas, puede ser útil hospedar explícitamente el runtime de .NET Core, como un medio para invocar código administrado en un proceso nativo o para obtener más control sobre el funcionamiento del runtime.

En este artículo se proporciona información general sobre los pasos necesarios para iniciar el entorno de ejecución .NET Core desde código nativo y ejecutar código administrado en él.

## <a name="prerequisites"></a>Requisitos previos

Como los hosts son aplicaciones nativas, este tutorial trata la creación de una aplicación de C++ para hospedar .NET Core. Necesitará un entorno de desarrollo de C++ (como el que se proporciona mediante [Visual Studio](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)).

También querrá una aplicación de .NET Core sencilla con la que probar el host, por lo que debe instalar el [SDK de .NET Core](https://dotnet.microsoft.com/download) y [crear una pequeña aplicación de prueba de .NET Core](with-visual-studio.md) (como una aplicación "Hola a todos"). La aplicación "Hola a todos" que se ha creado mediante la nueva plantilla de proyecto de la consola de .NET Core es suficiente.

## <a name="hosting-apis"></a>API de hospedaje

Hay tres API distintas que pueden usarse para hospedar .NET Core. En este artículo (y sus [ejemplos](https://github.com/dotnet/samples/tree/master/core/hosting) asociados) se tratan todas las opciones.

* El método preferido para hospedar el tiempo de ejecución de .NET Core en .NET Core 3.0 y superior es con las APIs de las bibliotecas `nethost` y `hostfxr`. Estos puntos de entrada tratan la complejidad de buscar y configurar el entorno de ejecución para la inicialización y permiten tanto el inicio de una aplicación administrada como la llamada a un método administrado estático.
* El método preferido para hospedar el entorno de ejecución .NET Core antes de la versión .NET Core 3.0 es con la API de [`coreclrhost.h`](https://github.com/dotnet/runtime/blob/master/src/coreclr/src/hosts/inc/coreclrhost.h). Esta API expone funciones para iniciar y detener fácilmente el entorno de ejecución e invocar código administrado (ya sea mediante el inicio de un archivo .exe administrado o una llamada a métodos estáticos administrados).

## <a name="sample-hosts"></a>Hosts de ejemplo

Hay [hosts de ejemplo](https://github.com/dotnet/samples/tree/master/core/hosting) que muestran los pasos descritos en los tutoriales siguientes en el repositorio dotnet/samples de GitHub. Los comentarios de los ejemplos asocian claramente los pasos numerados de estos tutoriales con el lugar donde se realizan en el ejemplo. Para obtener instrucciones de descarga, vea [Ejemplos y tutoriales](../../samples-and-tutorials/index.md#view-and-download-samples).

Tenga en cuenta que los hosts de ejemplo están pensados para usarse con fines de aprendizaje, por lo que pasan por encima de la comprobación de errores y están diseñados para enfatizar la legibilidad sobre la eficacia.

## <a name="create-a-host-using-nethosth-and-hostfxrh"></a>Creación de un host mediante `nethost.h` y `hostfxr.h`

En los siguientes pasos se explica cómo usar las bibliotecas `nethost` y `hostfxr` para iniciar el entorno de ejecución de .NET Core en una aplicación nativa y llamar a un método estático administrado. En el [ejemplo](https://github.com/dotnet/samples/tree/master/core/hosting/HostWithHostFxr) se utiliza el encabezado `nethost` y la biblioteca instalados con el SDK de .NET así como copias de los archivos [`coreclr_delegates.h`](https://github.com/dotnet/core-setup/blob/master/src/corehost/cli/coreclr_delegates.h) y [`hostfxr.h`](https://github.com/dotnet/core-setup/blob/master/src/corehost/cli/hostfxr.h) del repositorio [dotnet/core-setup](https://github.com/dotnet/core-setup).

### <a name="step-1---load-hostfxr-and-get-exported-hosting-functions"></a>Paso 1: Carga de `hostfxr` y obtención de funciones de hospedaje exportadas

La biblioteca `nethost` proporciona la función `get_hostfxr_path` para buscar la biblioteca `hostfxr`. La biblioteca `hostfxr` expone funciones para hospedar el entorno de ejecución de .NET Core. Encontrará la lista completa de funciones en [`hostfxr.h`](https://github.com/dotnet/core-setup/blob/master/src/corehost/cli/hostfxr.h) y en el [documento de diseño de hospedaje nativo](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/native-hosting.md). El ejemplo y este tutorial usan lo siguiente:

* `hostfxr_initialize_for_runtime_config`: Inicializa un contexto de host y se prepara para la inicialización del entorno de ejecución de .NET Core mediante la configuración del entorno de ejecución especificado.
* `hostfxr_get_runtime_delegate`: Obtiene un delegado para la funcionalidad del entorno de ejecución.
* `hostfxr_close`: Cierra un contexto del host.

La biblioteca `hostfxr` se encuentra mediante `get_hostfxr_path`. Después, se carga y se recuperan las exportaciones.

[!code-cpp[HostFxrHost#LoadHostFxr](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithHostFxr/src/NativeHost/nativehost.cpp#LoadHostFxr)]

### <a name="step-2---initialize-and-start-the-net-core-runtime"></a>Paso 2: Inicialización e inicio del entorno de ejecución de .NET Core

Las funciones `hostfxr_initialize_for_runtime_config` y `hostfxr_get_runtime_delegate` inicializan e inician el entorno de ejecución de .NET Core con la configuración del entorno de ejecución para el componente administrado que se va a cargar. La función `hostfxr_get_runtime_delegate` se utiliza para obtener un delegado del entorno de ejecución que permite cargar un ensamblado administrado y obtener un puntero de función para un método estático en ese ensamblado.

[!code-cpp[HostFxrHost#Initialize](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithHostFxr/src/NativeHost/nativehost.cpp#Initialize)]

### <a name="step-3---load-managed-assembly-and-get-function-pointer-to-a-managed-method"></a>Paso 3: Carga del ensamblado administrado y obtención un puntero de función a un método administrado

Se llama al delegado del entorno de ejecución para cargar el ensamblado administrado y obtener un puntero de función a un método administrado. El delegado necesita la ruta de acceso de ensamblado, el nombre del tipo y el nombre del método como entradas y devuelve un puntero de función que se puede utilizar para llamar al método administrado.

[!code-cpp[HostFxrHost#LoadAndGet](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithHostFxr/src/NativeHost/nativehost.cpp#LoadAndGet)]

Al pasar `nullptr` como nombre de tipo de delegado al llamar al delegado del entorno de ejecución, el ejemplo utiliza una firma predeterminada para el método administrado:

```csharp
public delegate int ComponentEntryPoint(IntPtr args, int sizeBytes);
```

Se puede utilizar una firma diferente si se especifica el nombre del tipo de delegado al llamar al delegado en entorno de ejecución.

### <a name="step-4---run-managed-code"></a>Paso 4: Ejecutar el código administrado

El host nativo ahora puede llamar al método administrado y pasarle los parámetros deseados.

[!code-cpp[HostFxrHost#CallManaged](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithHostFxr/src/NativeHost/nativehost.cpp#CallManaged)]

## <a name="create-a-host-using-coreclrhosth"></a>Creación de un host mediante `coreclrhost.h`

En los siguientes pasos se explica cómo usar la API de `coreclrhost.h` para iniciar el entorno de ejecución de .NET Core en una aplicación nativa y llamar a un método estático administrado. Los fragmentos de código de este documento usan algunas API específicas de Windows, pero el [host de ejemplo completo](https://github.com/dotnet/samples/tree/master/core/hosting/HostWithCoreClrHost) muestra las rutas de acceso de código de Windows y Linux.

El [host Unix CoreRun](https://github.com/dotnet/runtime/tree/master/src/coreclr/src/hosts/unixcorerun) muestra un ejemplo más complejo y real de hospedaje mediante `coreclrhost.h`.

### <a name="step-1---find-and-load-coreclr"></a>Paso 1: Buscar y cargar CoreCLR

Las API del entorno de ejecución .NET Core están en *coreclr.dll* (en Windows), en *libcoreclr.so* (en Linux) o en *libcoreclr.dylib* (en macOS). El primer paso para el hospedaje de .NET Core es cargar la biblioteca de CoreCLR. Algunos hosts sondean diferentes rutas de acceso o usan parámetros de entrada para buscar la biblioteca, mientras que otros saben cargarla desde una ruta de acceso determinada (junto al host, por ejemplo, o desde una ubicación de todo el equipo).

Una vez encontrada, la biblioteca se carga con `LoadLibraryEx` (en Windows) o `dlopen` (en Linux o macOS).

[!code-cpp[CoreClrHost#1](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithCoreClrHost/src/SampleHost.cpp#1)]

### <a name="step-2---get-net-core-hosting-functions"></a>Paso 2: Obtener las funciones de hospedaje de .NET Core

CoreClrHost tiene varios métodos importantes de utilidad para el hospedaje de .NET Core:

* `coreclr_initialize`: Inicia el entorno de ejecución .NET Core y configura el valor AppDomain predeterminado (y único).
* `coreclr_execute_assembly`: Ejecuta un ensamblado administrado.
* `coreclr_create_delegate`: Crea un puntero de función a un método administrado.
* `coreclr_shutdown`: Cierra el entorno de ejecución .NET Core.
* `coreclr_shutdown_2`: Es igual que `coreclr_shutdown`, pero además recupera el código de salida del código administrado.

Después de cargar la biblioteca de CoreCLR, el siguiente paso es obtener referencias a estas funciones mediante `GetProcAddress` (en Windows) o `dlsym` (en Linux o macOS).

[!code-cpp[CoreClrHost#2](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithCoreClrHost/src/SampleHost.cpp#2)]

### <a name="step-3---prepare-runtime-properties"></a>Paso 3: Preparar las propiedades del entorno de ejecución

Antes de iniciar el entorno de ejecución, es necesario preparar algunas propiedades para especificar el comportamiento (especialmente las relacionadas con el cargador de ensamblados).

Algunas propiedades comunes incluyen:

* `TRUSTED_PLATFORM_ASSEMBLIES` Esta es una lista de rutas de acceso de ensamblado (delimitadas por ";" en Windows y ":" en Linux) que el entorno de ejecución puede resolver de forma predeterminada. Algunos hosts tienen manifiestos codificados de forma rígida que enumeran los ensamblados que pueden cargar. Otros colocan cualquier biblioteca en determinadas ubicaciones (junto a *coreclr.dll*, por ejemplo) en esta lista.
* `APP_PATHS` Esta es una lista de rutas de acceso para explorar un ensamblado si este no puede encontrarse en la lista de ensamblados de plataforma de confianza (TPA). Dado que el host tiene más control sobre los ensamblados que se cargan mediante la lista TPA, es recomendable que los hosts determinen qué ensamblados esperan cargar y los muestren de forma explícita. Pero si es necesario sondear en tiempo de ejecución, esta propiedad se lo permite.
* `APP_NI_PATHS` Esta lista es similar a APP_PATHS, excepto que son las rutas de acceso las que se sondean en busca de imágenes nativas.
* `NATIVE_DLL_SEARCH_DIRECTORIES` Esta propiedad es una lista de rutas de acceso que el cargador debe sondear cuando busca bibliotecas nativas llamadas mediante p/invoke.
* `PLATFORM_RESOURCE_ROOTS` Esta lista incluye rutas de acceso que se van a explorar para ensamblados satélite de recursos (en subdirectorios específicos de la referencia cultural).

En este host de ejemplo, la lista TPA se construye simplemente mediante la enumeración de todas las bibliotecas del directorio actual:

[!code-cpp[CoreClrHost#7](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithCoreClrHost/src/SampleHost.cpp#7)]

Dado que el ejemplo es simple, solo necesita la propiedad `TRUSTED_PLATFORM_ASSEMBLIES`:

[!code-cpp[CoreClrHost#3](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithCoreClrHost/src/SampleHost.cpp#3)]

### <a name="step-4---start-the-runtime"></a>Paso 4: Iniciar el entorno de ejecución

Las API de `coreclrhost.h` inician el tiempo de ejecución y crean el AppDomain predeterminado todos con una sola llamada. La función `coreclr_initialize` toma una ruta de acceso base, un nombre y las propiedades descritas anteriormente y devuelve un manipulador al host a través del parámetro `hostHandle`.

[!code-cpp[CoreClrHost#4](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithCoreClrHost/src/SampleHost.cpp#4)]

### <a name="step-5---run-managed-code"></a>Paso 5: Ejecutar el código administrado

Con el entorno de ejecución iniciado, el host puede llamar al código administrado. Esta operación se puede realizar de diferentes maneras. El código de ejemplo vinculado a este tutorial usa la función `coreclr_create_delegate` para crear un delegado para un método administrado estático. Esta API toma el [nombre del ensamblado](../../standard/assembly/names.md), el nombre de tipo calificado por el espacio de nombres y el nombre del método como entradas y devuelve un delegado que puede usarse para invocar al método.

[!code-cpp[CoreClrHost#5](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithCoreClrHost/src/SampleHost.cpp#5)]

En este ejemplo, el host ya puede llamar a `managedDelegate` para ejecutar el método `ManagedWorker.DoWork`.

También se puede usar la función `coreclr_execute_assembly` para iniciar un archivo ejecutable administrado. Esta API toma una ruta de acceso de ensamblado y una matriz de argumentos como parámetros de entrada. Carga el ensamblado en esa ruta de acceso e invoca a su método principal.

```c++
int hr = executeAssembly(
        hostHandle,
        domainId,
        argumentCount,
        arguments,
        "HelloWorld.exe",
        (unsigned int*)&exitCode);
```

### <a name="step-6---shutdown-and-clean-up"></a>Paso 6: Cerrar y limpiar

Por último, cuando el host termina de ejecutar el código administrado, el entorno de ejecución .NET Core se cierra con `coreclr_shutdown` o `coreclr_shutdown_2`.

[!code-cpp[CoreClrHost#6](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithCoreClrHost/src/SampleHost.cpp#6)]

CoreCLR no admite la reinicialización ni la descarga. No vuelva a llamar a `coreclr_initialize` ni descargue la biblioteca de CoreCLR.

## <a name="conclusion"></a>Conclusión
Una vez que se ha compilado el host, este puede probarse ejecutándose desde la línea de comandos y pasando cualquier argumento que espere el host. Al especificar la aplicación de .NET Core para el host que se va a ejecutar, asegúrese de usar el archivo .dll que ha generado `dotnet build`. Los archivos ejecutables (archivos .exe) que ha generado `dotnet publish` para las aplicaciones autocontenidas son realmente el host de .NET Core predeterminado (de manera que la aplicación pueda iniciarse directamente desde la línea de comandos en escenarios principales); el código de usuario se compila en un archivo .dll del mismo nombre.

Si las cosas no funcionan inicialmente, vuelva a comprobar que *coreclr.dll* está disponible en la ubicación que espera el host, que todas las bibliotecas de Framework necesarias están en la lista TPA y que el valor de bits de CoreCLR (32 o 64 bits) coincide con la manera en que se ha compilado el host.

Hospedar el runtime de .NET Core es un escenario avanzado que muchos desarrolladores no necesitarán, pero para los que necesiten iniciar el código administrado desde un proceso nativo, o que necesiten más control sobre el comportamiento del runtime de .NET Core, puede resultar muy útil.
