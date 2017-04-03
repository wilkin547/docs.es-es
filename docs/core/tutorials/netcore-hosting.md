---
title: Hospedaje de .NET Core | Microsoft Docs
description: "Hospedar el runtime de .NET Core desde código nativo"
keywords: .NET, .NET Core, hospedaje, hospedaje de .NET Core
author: mjrousos
ms.author: mikerou
ms.date: 2/3/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 13edec8b-614d-47ed-9e95-ed6d3b94ec0c
translationtype: Human Translation
ms.sourcegitcommit: 9d770d008ff1223499de36b2b7b731d8ff6f0f2b
ms.openlocfilehash: 7618af5bed33d2e1801b1a9c1351a1d09d49b86e
ms.lasthandoff: 03/08/2017

---

# <a name="hosting-net-core"></a>Hospedaje de .NET Core

Como todo el código administrado, las aplicaciones de .NET Core se ejecutan mediante un host. El host es el responsable de iniciar el runtime (incluidos los componentes como el JIT y el recolector de elementos no utilizados), crear AppDomains e invocar puntos de entrada administrados.

Hospedar el runtime de .NET Core es un escenario avanzado y, en la mayoría de los casos, los desarrolladores de .NET Core no necesitan preocuparse sobre el hospedaje porque los procesos de compilación de .NET Core proporcionan un host predeterminado para ejecutar aplicaciones de .NET Core. En cambio, en algunas circunstancias especializadas, puede ser útil hospedar explícitamente el runtime de .NET Core, como un medio para invocar código administrado en un proceso nativo o para obtener más control sobre el funcionamiento del runtime.

En este artículo se proporciona información general sobre los pasos necesarios para iniciar el runtime de .NET Core desde código nativo, crear un dominio de aplicación inicial (@System.AppDomain) y ejecutar código administrado en él.

## <a name="prerequisites"></a>Requisitos previos

Como los hosts son aplicaciones nativas, este tutorial tratará la creación de una aplicación de C++ para hospedar .NET Core. Necesitará un entorno de desarrollo de C++ (como el que se proporciona mediante [Visual Studio](https://www.visualstudio.com/downloads/)).

También querrá una aplicación de .NET Core sencilla con la que probar el host, por lo que debe instalar el [SDK de .NET Core](https://www.microsoft.com/net/core) y [crear una pequeña aplicación de prueba de .NET Core](../../csharp/getting-started/with-visual-studio.md) (como una aplicación "Hola a todos"). La aplicación "Hola a todos" que se ha creado mediante la nueva plantilla de proyecto de la consola de .NET Core es suficiente.

Este tutorial y su [ejemplo asociado](https://github.com/dotnet/docs/tree/master/samples/core/hosting) crean un host de Windows, pero vea las notas al final de este artículo sobre cómo hospedar en UNIX.

## <a name="creating-the-host"></a>Creación del host

Un host de ejemplo que muestra los pasos descritos en este artículo está disponible en nuestro repositorio de [ejemplos de .NET Core](https://github.com/dotnet/docs/tree/master/samples/core/hosting). Los comentarios en el archivo host.cpp de ejemplo asocian claramente los pasos numerados de este tutorial con el lugar en el que se realizan en el ejemplo.

Tenga en cuenta que el host de ejemplo está diseñado para usarse con fines de aprendizaje, por lo que es ligero en la comprobación de errores y está diseñado para enfatizar la legibilidad sobre la eficacia. Puede encontrar más ejemplos de host reales en el repositorio [dotnet/coreclr](https://github.com/dotnet/coreclr/tree/master/src/coreclr/hosts). El [host CoreRun](https://github.com/dotnet/coreclr/tree/master/src/coreclr/hosts/corerun), en concreto, es un buen host con fines generales para estudiarlo después de leer el ejemplo más sencillo.

### <a name="a-note-about-mscoreeh"></a>Una nota sobre mscoree.h
La interfaz de hospedaje principal de .NET Core (`ICLRRuntimeHost2`) se define en [MSCOREE.IDL](https://github.com/dotnet/coreclr/blob/master/src/inc/MSCOREE.IDL). Se genera una versión de encabezado de este archivo (mscoree.h), que su host necesitará para hacer referencias, mediante MIDL cuando se compila el [runtime de .NET Core](https://github.com/dotnet/coreclr/). Si no quiere compilar el runtime de .NET Core, mscoree.h también está disponible como un [encabezado pregenerado](https://github.com/dotnet/coreclr/tree/master/src/pal/prebuilt/inc) en el repositorio dotnet/coreclr. Puede encontrar [instrucciones sobre la compilación del runtime de .NET Core](https://github.com/dotnet/coreclr#building-the-repository) en este repositorio de GitHub. 

### <a name="step-1---identify-the-managed-entry-point"></a>Paso 1: Identificar el punto de entrada administrado
Después de hacer referencia a los encabezados necesarios ([mscoree.h](https://github.com/dotnet/coreclr/tree/master/src/pal/prebuilt/inc/mscoree.h) y stdio.h, por ejemplo), una de las primeras cosas que un host de .NET Core debe hacer es localizar el punto de entrada administrado que va a usar. En nuestro host de ejemplo, esto se realiza simplemente tomando el primer argumento de la línea de comandos para nuestro host como la ruta de acceso a un archivo binario administrado cuyo método `main` se va a ejecutar.

[!code-cpp[NetCoreHost#1](../../../samples/core/hosting/host.cpp#1)]

### <a name="step-2---find-and-load-coreclrdll"></a>Paso 2: Buscar y cargar CoreCLR.dll
Las API del runtime de .NET Core están en *CoreCLR.dll* (en Windows). Para obtener nuestra interfaz de hospedaje (`ICLRRuntimeHost2`), es necesario buscar y cargar *CoreCLR.dll*. Depende del host definir una convención sobre cómo localizar *CoreCLR.dll*. Algunos hosts esperan que el archivo esté presente en una ubicación bien conocida del equipo (como %programfiles%\dotnet\shared\Microsoft.NETCore.App\1.1.0). Otros esperan que *CoreCLR.dll* se cargará desde una ubicación junto al propio host o a la aplicación que se va a hospedar. Y otros pueden consultar una variable de entorno para buscar la biblioteca.

En Linux o Mac, la biblioteca en tiempo de ejecución principal es *libcoreclr.so* o *libcoreclr.dylib*, respectivamente.

Nuestro host de ejemplo explora algunas ubicaciones comunes para *CoreCLR.dll*. Una vez que lo encuentra, debe cargarse mediante `LoadLibrary` (o `dlopen` en Linux/Mac).

[!code-cpp[NetCoreHost#2](../../../samples/core/hosting/host.cpp#2)]

### <a name="step-3---get-an-iclrruntimehost2-instance"></a>Paso 3: Obtener una instancia de ICLRRuntimeHost2
La interfaz de hospedaje de `ICLRRuntimeHost2` se recupera llamando a `GetProcAddress` (o `dlsym` en Linux/Mac) en `GetCLRRuntimeHost` y, después, invocando esa función. 

[!code-cpp[NetCoreHost#3](../../../samples/core/hosting/host.cpp#3)]

### <a name="step-4---setting-startup-flags-and-starting-the-runtime"></a>Paso 4: Establecer marcas de inicio e iniciar el runtime
Con `ICLRRuntimeHost2` disponible, ahora podemos especificar marcas de inicio en el runtime e iniciarlo. Las marcas de inicio determinarán qué recolector de elementos no utilizados (GC) se va a usar (simultáneo o servidor), si usaremos un solo AppDomain o varios y qué directiva de optimización del cargador se va a usar (para la carga de ensamblados con dominio neutro).

[!code-cpp[NetCoreHost#4](../../../samples/core/hosting/host.cpp#4)]

El runtime se inicia con una llamada a la función `Start`.

```C++
hr = runtimeHost->Start();
```

### <a name="step-5---preparing-appdomain-settings"></a>Paso 5: Preparar la configuración de AppDomain
Una vez que se inicie el runtime, querremos configurar un AppDomain. En cambio, existen varias opciones que deben especificarse a la hora de crear un AppDomain de .NET, por lo que es necesario prepararlas primero.

Las marcas de AppDomain especifican comportamientos de AppDomain relacionados con la seguridad y la interoperabilidad. Los hosts antiguos de Silverlight usaban esta configuración en el código de usuario de espacio aislado, pero los hosts de .NET Core más modernos ejecutan el código de usuario como de plena confianza y habilitan la interoperabilidad.

[!code-cpp[NetCoreHost#5](../../../samples/core/hosting/host.cpp#5)]

Después de decidir qué marcas de AppDomain se van a usar, deben definirse sus propiedades. Las propiedades son pares clave-valor de cadenas. Muchas de las propiedades se refieren a la manera en que AppDomain cargará ensamblados.

Las propiedades comunes de AppDomain incluyen:

* `TRUSTED_PLATFORM_ASSEMBLIES` Esta es una lista de rutas de acceso de ensamblado (delimitadas por ";" en Windows y ":" en UNIX) a las que AppDomain debe priorizar su carga y proporcionarles confianza plena (incluso en dominios de confianza parcial). Esta lista está diseñada para contener ensamblados de "Framework" y otros módulos de confianza, similares a los GAC en escenarios de .NET Framework. Algunos hosts colocarán una biblioteca junto a *coreclr.dll* en esta lista, otros tienen manifiestos codificados de forma rígida que enumeran ensamblados de confianza para sus fines.
* `APP_PATHS` Esta es una lista de rutas de acceso para explorar un ensamblado si este no puede encontrarse en la lista de ensamblados de plataforma de confianza (TPA). Estas rutas de acceso están diseñadas para ser las ubicaciones donde pueden encontrarse los ensamblados de los usuarios. En un AppDomain de espacio aislado, a los ensamblados cargados desde estas rutas de acceso solo se les concederá confianza parcial. Las rutas de acceso APP_PATH comunes incluyen la ruta desde la que se ha cargado la aplicación de destino u otras ubicaciones donde se sabe que se encuentran los recursos del usuario.
*  `APP_NI_PATHS` Esta lista es muy similar a APP_PATHS excepto que está diseñada para ser rutas de acceso que se explorarán para imágenes nativas.
*  `NATIVE_DLL_SEARCH_DIRECTORIES` Esta propiedad es una lista de rutas de acceso que el cargador debe explorar cuando busca archivos DLL nativos que se han llamado mediante p/invoke.
*  `PLATFORM_RESOURCE_ROOTS` Esta lista incluye rutas de acceso que se van a explorar para ensamblados satélite de recursos (en subdirectorios específicos de la referencia cultural).
*  `AppDomainCompatSwitch` Esta cadena especifica qué modos de interpretación de compatibilidad deben usarse para los ensamblados sin un moniker de la versión de .NET Framework de destino explícito (un atributo de nivel de ensamblado que indica en qué marco está pensado que se ejecute un ensamblado). Normalmente, esto debe establecerse en `"UseLatestBehaviorWhenTFMNotSpecified"`, pero algunos hosts pueden preferir obtener en su lugar modos de interpretación de compatibilidad más antiguos de Silverlight o Windows Phone.

En nuestro [host de ejemplo sencillo](https://github.com/dotnet/docs/tree/master/samples/core/hosting), estas propiedades se configuran de la siguiente manera:

[!code-cpp[NetCoreHost#6](../../../samples/core/hosting/host.cpp#6)]

### <a name="step-6---create-the-appdomain"></a>Paso 6: Crear el AppDomain
Una vez que todas las propiedades y marcas de AppDomain están preparadas, `ICLRRuntimeHost2::CreateAppDomainWithManager` puede usarse para configurar el AppDomain. De manera opcional, esta función toma un nombre completo del ensamblado y el nombre de tipo que se va a usar como el administrador de AppDomain del dominio. Un administrador de AppDomain puede permitir un host para controlar algunos aspectos del comportamiento de AppDomain y puede proporcionar puntos de entrada para iniciar el código administrado si el host no pretende invocar el código de usuario directamente.   

[!code-cpp[NetCoreHost#7](../../../samples/core/hosting/host.cpp#7)]

### <a name="step-7---run-managed-code"></a>Paso 7: Ejecutar el código administrado
Con un AppDomain en funcionamiento, ahora el host puede comenzar a ejecutar el código administrado. La manera más sencilla de hacer esto es usar `ICLRRuntimeHost2::ExecuteAssembly` para invocar un método de punto de entrada del ensamblado administrado. Tenga en cuenta que esta función solo funciona en escenarios de dominio único.

[!code-cpp[NetCoreHost#8](../../../samples/core/hosting/host.cpp#8)]

Otra opción, si `ExecuteAssembly` no satisface las necesidades del host, es usar `CreateDelegate` para crear un puntero de función a un método administrado estático. Esto requiere que el host conozca la firma del método al que está llamando (para crear el tipo de puntero de función), pero permite a los hosts tener flexibilidad para invocar código que no sea el punto de entrada del ensamblado.

```C++
void *pfnDelegate = NULL;
hr = runtimeHost->CreateDelegate(
  domainId,
  L"HW, Version=1.0.0.0, Culture=neutral",    // Target managed assembly
  L"ConsoleApplication.Program",            // Target managed type
  L"Main",                                    // Target entry point (static method)
  (INT_PTR*)&pfnDelegate);

((MainMethodFp*)pfnDelegate)(NULL);
```

### <a name="step-8---clean-up"></a>Paso 8: Limpiar
Por último, el host debe limpiarse después descargando AppDomains, deteniendo el runtime y lanzando la referencia `ICLRRuntimeHost2`.

[!code-cpp[NetCoreHost#9](../../../samples/core/hosting/host.cpp#9)]

## <a name="about-hosting-net-core-on-unix"></a>Sobre el hospedaje de .NET Core en UNIX
.NET Core es un producto multiplataforma que se ejecuta en sistemas operativos Windows, Linux y Mac. En cambio, como las aplicaciones nativas, los hosts de diferentes plataformas tendrán algunas diferencias entre ellos. El proceso que se ha descrito anteriormente del uso de `ICLRRuntimeHost2` para iniciar el runtime, crear un AppDomain y ejecutar código administrado, debe funcionar en cualquier sistema operativo admitido. Pero, las interfaces que se definen en mscoree.h pueden resultar complicadas para funcionar en plataformas de UNIX, ya que mscoree realiza muchas suposiciones de Win32.

Para facilitar el hospedaje en UNIX, se encuentra disponible un conjunto de más contenedores de la API de hospedaje de plataforma neutra en [coreclrhost.h](https://github.com/dotnet/coreclr/blob/master/src/coreclr/hosts/inc/coreclrhost.h).

Puede verse un ejemplo del uso de coreclrhost.h (en lugar de mscoree.h directamente) en el [host UnixCoreRun](https://github.com/dotnet/coreclr/tree/master/src/coreclr/hosts). Los pasos para usar las API desde coreclrhost.h para hospedar el runtime son similares a los pasos al usar mscoree.h:

1. Identifique el código administrado que se va a ejecutar (por ejemplo, de los parámetros de la línea de comandos). 
2. Cargue la biblioteca CoreCLR.
    1. `dlopen("./libcoreclr.so", RTLD_NOW | RTLD_LOCAL);` 
3. Obtenga punteros de función para las funciones `coreclr_initialize`, `coreclr_create_delegate`, `coreclr_execute_assembly` y `coreclr_shutdown` de CoreCLR con `dlsym`.
    1. `coreclr_initialize_ptr coreclr_initialize = (coreclr_initialize_ptr)dlsym(coreclrLib, "coreclr_initialize");`
4. Configure las propiedades de AppDomain (como la lista TPA). Este es el mismo que el paso 5 del flujo de trabajo de mscoree anterior.
5. Use `coreclr_initialize` para iniciar el runtime y crear un AppDomain. Esto también creará un puntero `hostHandle` que se usará en futuras llamadas de hospedaje.
    1. Tenga en cuenta que esta función realiza los roles de los pasos 4 y 6 del flujo de trabajo anterior. 
6. Use `coreclr_execute_assembly` o `coreclr_create_delegate` para ejecutar el código administrado. Estas funciones son análogas a las funciones `ExecuteAssembly` y `CreateDelegate` de mscoree del paso 7 del flujo de trabajo anterior.
7. Use `coreclr_shutdown` para descargar el AppDomain y apagar el runtime. 

## <a name="conclusion"></a>Conclusión
Una vez que se ha compilado el host, este puede probarse ejecutándose desde la línea de comandos y pasando cualquier argumento (como la aplicación administrada que se va a ejecutar) que espere el host. Al especificar la aplicación de .NET Core para el host que se va a ejecutar, asegúrese de usar el archivo .dll que ha generado `dotnet build`. Los archivos ejecutables que ha generado `dotnet publish` para las aplicaciones independientes son realmente el host de .NET Core predeterminado (de manera que la aplicación pueda iniciarse directamente desde la línea de comandos en escenarios principales); el código de usuario se compila en un archivo .dll del mismo nombre. 

Si las cosas no funcionan inicialmente, vuelva a comprobar que *coreclr.dll* está disponible en la ubicación que espera el host, que todas las bibliotecas de Framework necesarias están en la lista TPA y que el valor de bits de CoreCLR (32 o 64 bits) coincide con la manera en que se ha compilado el host.

Hospedar el runtime de .NET Core es un escenario avanzado que muchos desarrolladores no necesitarán, pero para los que necesiten iniciar el código administrado desde un proceso nativo, o que necesiten más control sobre el comportamiento del runtime de .NET Core, puede resultar muy útil. Como .NET Core es capaz de ejecutarse en paralelo, es posible incluso crear hosts que inicialicen varias versiones del runtime de .NET Core y ejecuten aplicaciones en todos ellos en el mismo proceso. 
