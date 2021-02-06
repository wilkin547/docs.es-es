---
description: 'Más información sobre: los perfiles CLR y las aplicaciones de la tienda Windows'
title: Aplicaciones de la Tienda Windows y generadores de perfiles CLR
ms.date: 03/30/2017
dev_langs:
- csharp
applies_to:
- Windows 10
- Windows 8
helpviewer_keywords:
- profiling API
- profiling API [.NET Framework]
- profiling managed code
- profiling managed code [Windows Store Apps]
ms.assetid: 1c8eb2e7-f20a-42f9-a795-71503486a0f5
ms.openlocfilehash: e864f67aff106659194b91814bc2509d50cbf701
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99649281"
---
# <a name="clr-profilers-and-windows-store-apps"></a>Aplicaciones de la Tienda Windows y generadores de perfiles CLR

En este tema se explica lo que hay que tener en cuenta al escribir herramientas de diagnóstico que analizan el código administrado que se ejecuta dentro de una aplicación de la tienda Windows. También se proporcionan instrucciones para modificar las herramientas de desarrollo existentes para que sigan funcionando cuando las ejecute en aplicaciones de la tienda Windows. Para entender esta información, es mejor si está familiarizado con la API de generación de perfiles de Common Language Runtime, ya ha usado esta API en una herramienta de diagnóstico que se ejecuta correctamente en las aplicaciones de escritorio de Windows y ahora está interesado en modificar la herramienta para que se ejecute correctamente en las aplicaciones de la tienda Windows.

## <a name="introduction"></a>Introducción

Si lo ha hecho más allá del párrafo de introducción, ya está familiarizado con la API de generación de perfiles de CLR. Ya ha escrito una herramienta de diagnóstico que funciona bien con las aplicaciones de escritorio administradas. Ahora tiene curiosidad sobre lo que debe hacer para que la herramienta funcione con una aplicación administrada de la tienda Windows. Es posible que ya haya intentado realizar este trabajo y haya descubierto que no es una tarea sencilla. En realidad, hay una serie de consideraciones que es posible que no sean obvias para todos los desarrolladores de herramientas. Por ejemplo:

- Las aplicaciones de la tienda Windows se ejecutan en un contexto con permisos muy reducidos.

- Los archivos de metadatos de Windows tienen características únicas en comparación con los módulos administrados tradicionales.

- Las aplicaciones de la tienda Windows tienen el hábito de suspenderse cuando la interactividad deja de funcionar.

- Es posible que los mecanismos de comunicación entre procesos ya no funcionen por varias razones.

En este tema se enumeran las cosas que debe tener en cuenta y cómo tratarlas correctamente.

Si no está familiarizado con la API de generación de perfiles de CLR, vaya a los recursos al final de este tema para encontrar más información introductoria.

También está fuera del ámbito de este tema el suministro de detalles sobre las API específicas de Windows y cómo deben usarse. Considere este tema un punto de partida y consulte MSDN para obtener más información sobre las API de Windows a las que se hace referencia aquí.

## <a name="architecture-and-terminology"></a>Arquitectura y terminología

Normalmente, una herramienta de diagnóstico tiene una arquitectura como la que se muestra en la siguiente ilustración. Usa el término "Profiler", pero muchas de estas herramientas van más allá de la generación de perfiles de memoria o rendimiento típica en áreas como la cobertura de código, marcos de objetos ficticios, depuración de viaje de tiempo, supervisión de aplicaciones, etc. Para simplificar, en este tema se seguirá haciendo referencia a todas estas herramientas como generadores de perfiles.

En este tema se usa la siguiente terminología:

**Aplicación**

Se trata de la aplicación que está analizando el generador de perfiles. Normalmente, el desarrollador de esta aplicación está usando ahora el generador de perfiles para ayudar a diagnosticar problemas con la aplicación. Tradicionalmente, esta aplicación sería una aplicación de escritorio de Windows, pero en este tema veremos las aplicaciones de la tienda Windows.

**DLL del generador de perfiles**

Este es el componente que se carga en el espacio de proceso de la aplicación que se está analizando. Este componente, también conocido como "agente" de Profiler, implementa las interfaces de la interfaz [ICorProfilerCallback](icorprofilercallback-interface.md)[ICorProfilerCallback](icorprofilercallback-interface.md)(2, 3, etc.) y consume las interfaces [ICorProfilerInfo](icorprofilerinfo-interface.md)(2, 3, etc.) para recopilar datos sobre la aplicación analizada y, potencialmente, modificar aspectos del comportamiento de la aplicación.

**IU de Profiler**

Se trata de una aplicación de escritorio con la que interactúa el usuario del generador de perfiles. Es responsable de mostrar el estado de la aplicación al usuario y de ofrecer al usuario los medios para controlar el comportamiento de la aplicación analizada. Este componente siempre se ejecuta en su propio espacio de proceso, independiente del espacio de proceso de la aplicación de la que se está generando el archivo. La interfaz de usuario del generador de perfiles también puede actuar como "asociar desencadenador", que es el proceso que llama al método [ICLRProfiling:: AttachProfiler](iclrprofiling-attachprofiler-method.md) , para que la aplicación analizada cargue la dll del generador de perfiles en aquellos casos en los que no se cargó la dll del generador de perfiles al iniciarse.

> [!IMPORTANT]
> La interfaz de usuario del generador de perfiles debe permanecer en una aplicación de escritorio de Windows, incluso cuando se utiliza para controlar y generar informes en una aplicación de la tienda Windows. No se espera poder empaquetar y enviar la herramienta de diagnóstico en la tienda Windows. La herramienta debe hacer cosas que las aplicaciones de la tienda Windows no pueden hacer, y muchas de esas cosas residen dentro de la interfaz de usuario del generador de perfiles.

En este documento, el código de ejemplo asume que:

- La DLL del generador de perfiles se escribe en C++, porque debe ser una DLL nativa, según los requisitos de la API de generación de perfiles de CLR.

- La interfaz de usuario del generador de perfiles está escrita en C#. Esto no es necesario, pero como no hay ningún requisito en el lenguaje para el proceso de la interfaz de usuario del generador de perfiles, ¿por qué no elegir un lenguaje que sea conciso y sencillo?

### <a name="windows-rt-devices"></a>Dispositivos Windows RT

Los dispositivos Windows RT están bastante bloqueados. Simplemente no se pueden cargar los perfiles de terceros en estos dispositivos. Este documento se centra en los equipos con Windows 8.

## <a name="consuming-windows-runtime-apis"></a>Consumo de API de Windows Runtime

En una serie de escenarios descritos en las secciones siguientes, la aplicación de escritorio de la interfaz de usuario del generador de perfiles debe consumir algunas nuevas API de Windows Runtime. Querrá consultar la documentación para saber qué Windows Runtime API se pueden usar desde aplicaciones de escritorio y si su comportamiento es diferente cuando se llama desde aplicaciones de escritorio y aplicaciones de la tienda Windows.

Si la interfaz de usuario del generador de perfiles está escrita en código administrado, habrá que realizar algunos pasos para que el consumo de esas Windows Runtime API sea fácil. Para obtener más información, consulte el artículo [aplicaciones de escritorio administradas y Windows Runtime](/previous-versions/windows/apps/jj856306(v=win.10)) .

## <a name="loading-the-profiler-dll"></a>Carga del archivo DLL del generador de perfiles

En esta sección se describe cómo la interfaz de usuario del generador de perfiles hace que la aplicación de la tienda Windows cargue el archivo DLL del generador de perfiles. El código que se describe en esta sección pertenece a la aplicación de escritorio de la interfaz de usuario del generador de perfiles y, por lo tanto, implica el uso de las API de Windows seguras para aplicaciones de escritorio, pero no necesariamente seguras para aplicaciones de la tienda Windows

La interfaz de usuario del generador de perfiles puede hacer que la DLL del generador de perfiles se cargue en el espacio de proceso de la aplicación de dos maneras:

- En el inicio de la aplicación, tal y como lo controlan las variables de entorno.

- Al adjuntar a la aplicación después de que se complete el inicio, se llama al método [ICLRProfiling:: AttachProfiler](iclrprofiling-attachprofiler-method.md) .

Uno de los primeros obstáculos será la carga de inicio y la carga de conexión de la DLL del generador de perfiles para que funcione correctamente con las aplicaciones de la tienda Windows. Ambas formas de carga comparten algunas consideraciones especiales en común, por lo que vamos a comenzar con ellas.

### <a name="common-considerations-for-startup-and-attach-loads"></a>Consideraciones comunes para el inicio y la Asociación de cargas

**Firma de la DLL del generador de perfiles**

Cuando Windows intenta cargar el archivo DLL del generador de perfiles, comprueba que la DLL del generador de perfiles está firmada correctamente. En caso contrario, se produce un error de carga de forma predeterminada. Existen dos formas de hacerlo:

- Asegúrese de que la DLL del generador de perfiles está firmada.

- Indique al usuario que debe instalar una licencia de Desarrollador en su máquina con Windows 8 antes de usar la herramienta. Esto puede realizarse automáticamente desde Visual Studio o manualmente desde un símbolo del sistema. Para obtener más información, consulte [obtener una licencia de desarrollador](/previous-versions/windows/apps/hh974578(v=win.10)).

**Permisos del sistema de archivos**

La aplicación de la tienda Windows debe tener permiso para cargar y ejecutar el archivo DLL del generador de perfiles desde la ubicación en el sistema de archivos en la que se residesBy de forma predeterminada, la aplicación de la tienda Windows no tiene este permiso en la mayoría de los directorios y cualquier intento fallido de cargar el archivo DLL del generador de perfiles producirá una entrada en el registro de eventos de aplicación de Windows que :

```output
NET Runtime version 4.0.30319.17929 - Loading profiler failed during CoCreateInstance.  Profiler CLSID: '{xxxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx}'.  HRESULT: 0x80070005.  Process ID (decimal): 4688.  Message ID: [0x2504].
```

Por lo general, las aplicaciones de la tienda Windows solo pueden tener acceso a un conjunto limitado de ubicaciones en el disco. Cada aplicación de la tienda Windows puede tener acceso a sus propias carpetas de datos de la aplicación, así como a algunas otras áreas del sistema de archivos para las que se concede acceso a todas las aplicaciones de la tienda Windows. Es mejor instalar el archivo DLL del generador de perfiles y sus dependencias en algún lugar de archivos de programa o archivos de programa (x86), ya que todas las aplicaciones de la tienda Windows tienen permisos de lectura y ejecución de forma predeterminada.

### <a name="startup-load"></a>Carga de inicio

Normalmente, en una aplicación de escritorio, la interfaz de usuario del generador de perfiles solicita una carga de inicio de la DLL del generador de perfiles mediante la inicialización de un bloque de entorno que contiene las variables de entorno de la API de generación de perfiles de CLR necesarias (es decir,, `COR_PROFILER` `COR_ENABLE_PROFILING` y `COR_PROFILER_PATH` ) y, después, la creación de un nuevo proceso con ese bloque de entorno. Lo mismo se aplica a las aplicaciones de la tienda Windows, pero los mecanismos son diferentes.

**No ejecutar con privilegios elevados**

Si el proceso a intenta generar el proceso de la aplicación de la tienda Windows B, el proceso A se debe ejecutar en el nivel de integridad medio, no en un nivel de integridad alto (es decir, no elevado). Esto significa que la interfaz de usuario del generador de perfiles debe ejecutarse en el nivel de integridad medio, o bien debe generar otro proceso de escritorio en el nivel de integridad medio para poder iniciar la aplicación de la tienda Windows.

**Elegir una aplicación de la tienda Windows para generar perfiles**

En primer lugar, querrá preguntar al usuario de Profiler qué aplicación de la tienda Windows se va a iniciar. En el caso de las aplicaciones de escritorio, quizás muestre un cuadro de diálogo de búsqueda de archivos y el usuario encontraría y seleccione un archivo. exe. Pero las aplicaciones de la tienda Windows son diferentes y el uso de un cuadro de diálogo de exploración no tiene sentido. En su lugar, es mejor mostrar al usuario una lista de las aplicaciones de la tienda Windows instaladas para que el usuario las seleccione.

Puede utilizar la <xref:Windows.Management.Deployment.PackageManager> clase para generar esta lista. `PackageManager` es una clase Windows Runtime que está disponible para las aplicaciones de escritorio y, de hecho, *solo* está disponible para las aplicaciones de escritorio.

El siguiente ejemplo de código de una interfaz de usuario hipotética del generador de perfiles que se escribe como una aplicación de escritorio en C# utiliza `PackageManager` para generar una lista de aplicaciones de Windows:

```csharp
string currentUserSID = WindowsIdentity.GetCurrent().User.ToString();
IAppxFactory appxFactory = (IAppxFactory) new AppxFactory();
PackageManager packageManager = new PackageManager();
IEnumerable<Package> packages = packageManager.FindPackagesForUser(currentUserSID);
```

**Especificar el bloque de entorno personalizado**

Una nueva interfaz COM, [IPackageDebugSettings](/windows/desktop/api/shobjidl_core/nn-shobjidl_core-ipackagedebugsettings), le permite personalizar el comportamiento de ejecución de una aplicación de la tienda Windows para facilitar algunas formas de diagnóstico. Uno de sus métodos, [EnableDebugging](/windows/desktop/api/shobjidl_core/nf-shobjidl_core-ipackagedebugsettings-enabledebugging), le permite pasar un bloque de entorno a la aplicación de la tienda Windows cuando se inicia, junto con otros efectos útiles como la deshabilitación de la suspensión automática del proceso. El bloque de entorno es importante porque es donde debe especificar las variables de entorno ( `COR_PROFILER` , `COR_ENABLE_PROFILING` y) que `COR_PROFILER_PATH)` usa CLR para cargar el archivo DLL del generador de perfiles.

Tenga en cuenta el fragmento de código siguiente:

```csharp
IPackageDebugSettings pkgDebugSettings = new PackageDebugSettings();
pkgDebugSettings.EnableDebugging(packageFullName, debuggerCommandLine,
                                                                 (IntPtr)fixedEnvironmentPzz);
```

Hay un par de elementos que debe tener derecho:

- `packageFullName` se puede determinar al recorrer en iteración los paquetes y la captura `package.Id.FullName` .

- `debuggerCommandLine` es un poco más interesante. Para pasar el bloque de entorno personalizado a la aplicación de la tienda Windows, debe escribir su propio depurador ficticio simplista. Windows genera la aplicación de la tienda Windows suspendida y, a continuación, asocia el depurador iniciando el depurador con una línea de comandos como en este ejemplo:

    ```console
    MyDummyDebugger.exe -p 1336 -tid 1424
    ```

     donde `-p 1336` significa que la aplicación de la tienda Windows tiene el identificador de proceso 1336 y `-tid 1424` significa que el ID. de subproceso 1424 es el subproceso que se suspende. El depurador ficticio analizaría el ThreadID desde la línea de comandos, reanudaría dicho subproceso y, a continuación, se cerrará.

     Este es un ejemplo de código de C++ para hacerlo (Asegúrese de agregar la comprobación de errores):

    ```cpp
    int wmain(int argc, wchar_t* argv[])
    {
        // …
        // Parse command line here
        // …

        HANDLE hThread = OpenThread(THREAD_SUSPEND_RESUME,
                                                                  FALSE /* bInheritHandle */, nThreadID);
        ResumeThread(hThread);
        CloseHandle(hThread);
        return 0;
    }
    ```

     Deberá implementar este depurador ficticio como parte de la instalación de la herramienta de diagnóstico y, a continuación, especificar la ruta de acceso a este depurador en el `debuggerCommandLine` parámetro.

**Inicio de la aplicación de la tienda Windows**

Ya llegó el momento de iniciar la aplicación de la tienda Windows. Si ya lo ha intentado, es posible que haya observado que [CreateProcess](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-createprocessa) no es la forma en que crea un proceso de aplicación de la tienda Windows. En su lugar, debe usar el método [IApplicationActivationManager:: ActivateApplication](/windows/desktop/api/shobjidl_core/nf-shobjidl_core-iapplicationactivationmanager-activateapplication) . Para ello, tendrás que obtener el identificador de modelo de usuario de la aplicación de la tienda Windows que estás iniciando. Y eso significa que tendrá que hacer algo más en el manifiesto.

Al recorrer en iteración los paquetes (vea "elegir una aplicación de la tienda Windows para generar perfiles" en la sección [carga de inicio](#startup-load) anterior), querrá obtener el conjunto de aplicaciones contenidas en el manifiesto del paquete actual:

```csharp
string manifestPath = package.InstalledLocation.Path + "\\AppxManifest.xml";

AppxPackaging.IStream manifestStream;
SHCreateStreamOnFileEx(
                    manifestPath,
                    0x00000040,     // STGM_READ | STGM_SHARE_DENY_NONE
                    0,              // file creation attributes
                    false,          // fCreate
                    null,           // reserved
                    out manifestStream);

IAppxManifestReader manifestReader = appxFactory.CreateManifestReader(manifestStream);

IAppxManifestApplicationsEnumerator appsEnum = manifestReader.GetApplications();
```

Sí, un paquete puede tener varias aplicaciones y cada aplicación tiene su propio identificador de modelo de usuario de la aplicación. Por lo tanto, le interesará preguntar a su usuario qué aplicación se va a perfilar y obtener el identificador del modelo de usuario de la aplicación de esa aplicación en particular:

```csharp
while (appsEnum.GetHasCurrent() != 0)
{
    IAppxManifestApplication app = appsEnum.GetCurrent();
    string appUserModelId = app.GetAppUserModelId();
    //...
}
```

Por último, ahora tiene lo que necesita para iniciar la aplicación de la tienda Windows:

```csharp
IApplicationActivationManager appActivationMgr = new ApplicationActivationManager();
appActivationMgr.ActivateApplication(appUserModelId, appArgs, ACTIVATEOPTIONS.AO_NONE, out pid);
```

**Recuerde llamar a DisableDebugging**

Cuando llamó a [IPackageDebugSettings:: EnableDebugging](/windows/desktop/api/shobjidl_core/nf-shobjidl_core-ipackagedebugsettings-enabledebugging), ha hecho una promesa de que debe realizar la limpieza después de llamar al método [IPackageDebugSettings::D isabledebugging](/windows/desktop/api/shobjidl_core/nf-shobjidl_core-ipackagedebugsettings-disabledebugging) , por lo que debe asegurarse de hacerlo cuando la sesión de generación de perfiles se ha superado.

### <a name="attach-load"></a>Asociar carga

Cuando la interfaz de usuario del generador de perfiles desea adjuntar su DLL del generador de perfiles a una aplicación que ya ha empezado a ejecutarse, usa [ICLRProfiling:: AttachProfiler](iclrprofiling-attachprofiler-method.md). Lo mismo sucede con las aplicaciones de la tienda Windows. Pero además de las consideraciones comunes enumeradas anteriormente, asegúrese de que la aplicación de la tienda Windows de destino no esté suspendida.

**EnableDebugging**

Al igual que con la carga de inicio, llame al método [IPackageDebugSettings:: EnableDebugging](/windows/desktop/api/shobjidl_core/nf-shobjidl_core-ipackagedebugsettings-enabledebugging) . No es necesario para pasar un bloque de entorno, pero se necesita una de sus otras características: deshabilitar la suspensión automática del proceso. De lo contrario, cuando la interfaz de usuario del generador de perfiles llama a [AttachProfiler](iclrprofiling-attachprofiler-method.md), es posible que la aplicación de la tienda Windows de destino esté suspendida. De hecho, es probable que esto sea así si el usuario está interactuando con la interfaz de usuario del generador de perfiles y la aplicación de la tienda Windows no está activa en ninguna de las pantallas del usuario. Y, si la aplicación de la tienda Windows está suspendida, no podrá responder a ninguna señal que el CLR le envíe para adjuntar la DLL del generador de perfiles.

Por lo tanto, querrá hacer algo parecido a esto:

```csharp
IPackageDebugSettings pkgDebugSettings = new PackageDebugSettings();
pkgDebugSettings.EnableDebugging(packageFullName, null /* debuggerCommandLine */,
                                                                 IntPtr.Zero /* environment */);
```

Esta es la misma llamada que se haría para el caso de carga de inicio, salvo que no se especifica una línea de comandos del depurador o un bloque de entorno.

**DisableDebugging**

Como siempre, no se olvide de llamar a [IPackageDebugSettings::D isabledebugging](/windows/desktop/api/shobjidl_core/nf-shobjidl_core-ipackagedebugsettings-disabledebugging) cuando se complete la sesión de generación de perfiles.

## <a name="running-inside-the-windows-store-app"></a>Ejecutar dentro de la aplicación de la tienda Windows

Por lo tanto, la aplicación de la tienda Windows ha cargado la DLL del generador de perfiles. Ahora, la DLL del generador de perfiles se debe impartir cómo jugar con las distintas reglas requeridas por las aplicaciones de la tienda Windows, incluidas las API permitidas y cómo ejecutarlas con permisos reducidos.

### <a name="stick-to-the-windows-store-app-apis"></a>Ajustar a las API de la aplicación de la tienda Windows

Cuando examine la API de Windows, observará que todas las API se documentan como aplicables a las aplicaciones de escritorio, a las aplicaciones de la tienda Windows o a ambas. Por ejemplo, la sección de **requisitos** de la documentación de la función [InitializeCriticalSectionAndSpinCount](/windows/desktop/api/synchapi/nf-synchapi-initializecriticalsectionandspincount) indica que la función se aplica solo a las aplicaciones de escritorio. En cambio, la función [InitializeCriticalSectionEx](/windows/desktop/api/synchapi/nf-synchapi-initializecriticalsectionex) está disponible para aplicaciones de escritorio y aplicaciones de la tienda Windows.

Al desarrollar el archivo DLL del generador de perfiles, trate como si se tratase de una aplicación de la tienda Windows y use solo las API que estén documentadas como disponibles para las aplicaciones de la tienda Windows. Analice las dependencias (por ejemplo, puede ejecutar `link /dump /imports` en la dll del generador de perfiles para auditar) y, a continuación, busque los documentos para ver cuáles son las dependencias correctas y cuáles no. En la mayoría de los casos, las infracciones se pueden corregir simplemente reemplazándolo por una forma más reciente de la API que se documenta como segura (por ejemplo, reemplazando [InitializeCriticalSectionAndSpinCount](/windows/desktop/api/synchapi/nf-synchapi-initializecriticalsectionandspincount) por [InitializeCriticalSectionEx](/windows/desktop/api/synchapi/nf-synchapi-initializecriticalsectionex)).

Es posible que observe que el archivo DLL del generador de perfiles llama a algunas API que solo se aplican a las aplicaciones de escritorio, pero parecen funcionar incluso cuando el archivo DLL del generador de perfiles se carga en una aplicación de la tienda Windows. Tenga en cuenta que es arriesgado usar cualquier API no documentada para su uso con aplicaciones de la tienda Windows en el archivo DLL del generador de perfiles cuando se carga en un proceso de aplicación de la tienda Windows:

- No se garantiza que estas API funcionen cuando se llama en el contexto único en el que se ejecutan las aplicaciones de la tienda Windows.

- Es posible que estas API no funcionen de forma coherente cuando se llama desde dentro de distintos procesos de la aplicación de la tienda Windows.

- Es posible que estas API parezcan funcionar bien desde las aplicaciones de la tienda Windows en la versión actual de Windows, pero pueden interrumpirse o deshabilitarse en futuras versiones de Windows.

El mejor Consejo es corregir todas las infracciones y evitar el riesgo.

Es posible que no pueda hacer esto sin una API determinada y no pueda encontrar una sustitución adecuada para las aplicaciones de la tienda Windows. En tal caso, como mínimo:

- Pruebe, pruebe y pruebe los deshorarioos de la vida del uso de esa API.

- Comprenda que la API podría interrumpir o desaparecer repentinamente si se llama desde aplicaciones de la tienda Windows en versiones futuras de Windows. Esto no se considerará un problema de compatibilidad de Microsoft y el uso de este no será prioritario.

### <a name="reduced-permissions"></a>Permisos reducidos

Está fuera del ámbito de este tema para mostrar todas las formas en que los permisos de aplicación de la tienda Windows difieren de las aplicaciones de escritorio. Pero ciertamente, el comportamiento será diferente cada vez que el archivo DLL del generador de perfiles (cuando se carga en una aplicación de la tienda Windows en comparación con una aplicación de escritorio) intente tener acceso a los recursos. El sistema de archivos es el ejemplo más común. Hay algunos lugares en disco a los que puede tener acceso una aplicación determinada de la tienda Windows (vea [acceso a archivos y permisos (aplicaciones Windows Runtime](/previous-versions/windows/apps/hh967755(v=win.10))) y el archivo DLL del generador de perfiles tendrá las mismas restricciones. Pruebe el código exhaustivamente.

### <a name="inter-process-communication"></a>Comunicación entre procesos

Como se muestra en el diagrama al principio de este documento, es probable que el archivo DLL del generador de perfiles (cargado en el espacio de proceso de la aplicación de la tienda Windows) necesite comunicarse con la interfaz de usuario del generador de perfiles (que se ejecuta en un espacio de proceso de la aplicación de escritorio independiente) a través de su propio canal de comunicación entre procesos (IPC) personalizado. La interfaz de usuario del generador de perfiles envía señales a la DLL del generador de perfiles para modificar su comportamiento, y la DLL del generador de perfiles envía datos de la aplicación de la tienda Windows analizada de nuevo a la interfaz de usuario del generador de perfiles para su posterior procesamiento y mostrar al usuario de Profiler.

La mayoría de los generador de perfiles necesitan trabajar de esta manera, pero las opciones de los mecanismos IPC son más limitadas cuando el archivo DLL del generador de perfiles se carga en una aplicación de la tienda Windows. Por ejemplo, las canalizaciones con nombre no forman parte del SDK de aplicaciones de la tienda Windows, por lo que no puede usarlas.

Pero, por supuesto, los archivos siguen en, aunque de forma más limitada. También están disponibles los eventos.

**Comunicación a través de archivos**

La mayoría de los datos probablemente pasarán entre la DLL del generador de perfiles y la interfaz de usuario del generador de perfiles a través de archivos. La clave consiste en elegir una ubicación de archivo que el archivo DLL del generador de perfiles (en el contexto de una aplicación de la tienda Windows) y la interfaz de usuario del generador de perfiles tengan acceso de lectura y escritura a. Por ejemplo, la ruta de acceso de la carpeta temporal es una ubicación a la que pueden acceder tanto a la DLL del generador de perfiles como a la interfaz de usuario del generador de perfiles, pero ningún otro paquete de la aplicación de la tienda Windows puede acceder a él (con lo que se protege cualquier información que se registre desde otros paquetes de aplicaciones

La interfaz de usuario del generador de perfiles y la DLL del generador de perfiles pueden determinar esta ruta de acceso de forma independiente La interfaz de usuario del generador de perfiles, cuando recorre en iteración todos los paquetes instalados para el usuario actual (vea el código de ejemplo anterior), obtiene acceso a la `PackageId` clase, de la que la ruta de acceso de la carpeta temporal se puede derivar con código similar a este fragmento de código. (Como siempre, la comprobación de errores se omite por motivos de brevedad).

```csharp
// C# code for the Profiler UI.
ApplicationData appData =
    ApplicationDataManager.CreateForPackageFamily(
        packageId.FamilyName);

tempDir = appData.TemporaryFolder.Path;
```

Mientras tanto, el archivo DLL del generador de perfiles puede hacer básicamente lo mismo, aunque puede obtener más fácilmente la <xref:Windows.Storage.ApplicationData> clase mediante la propiedad [ApplicationData. Current](xref:Windows.Storage.ApplicationData.Current%2A) .

**Comunicación a través de eventos**

Si desea una semántica de señalización simple entre la interfaz de usuario del generador de perfiles y el archivo DLL del generador de perfiles, puede usar eventos dentro de las aplicaciones de la tienda Windows, así como aplicaciones de escritorio.

Desde el archivo DLL del generador de perfiles, puede llamar simplemente a la función [CreateEventEx](/windows/desktop/api/synchapi/nf-synchapi-createeventexa) para crear un evento con nombre con el nombre que desee. Por ejemplo:

```cpp
// Profiler DLL in Windows Store app (C++).
CreateEventEx(
    NULL,  // Not inherited
    "MyNamedEvent"
    CREATE_EVENT_MANUAL_RESET, /* explicit ResetEvent() required; leave initial state unsignaled */
    EVENT_ALL_ACCESS);
```

La interfaz de usuario del generador de perfiles debe encontrar ese evento con nombre en el espacio de nombres de la aplicación de la tienda Windows. Por ejemplo, la interfaz de usuario del generador de perfiles podría llamar a [CreateEventEx](/windows/desktop/api/synchapi/nf-synchapi-createeventexa), especificando el nombre del evento como

`AppContainerNamedObjects\<acSid>\MyNamedEvent`

`<acSid>` es el SID del AppContainer de la aplicación de la tienda Windows. En una sección anterior de este tema se ha mostrado cómo recorrer en iteración los paquetes instalados para el usuario actual. En ese código de ejemplo, puede obtener el packageId. Y, desde el packageId, puede obtener el `<acSid>` con código similar al siguiente:

```csharp
IntPtr acPSID;
DeriveAppContainerSidFromAppContainerName(packageId.FamilyName, out acPSID);

string acSid;
ConvertSidToStringSid(acPSID, out acSid);

string acDir;
GetAppContainerFolderPath(acSid, out acDir);
```

### <a name="no-shutdown-notifications"></a>No hay notificaciones de apagado

Al ejecutarse dentro de una aplicación de la tienda Windows, la DLL del generador de perfiles no debe basarse en [ICorProfilerCallback:: Shutdown](icorprofilercallback-shutdown-method.md) o incluso [DllMain](/windows/desktop/Dlls/dllmain) (con `DLL_PROCESS_DETACH` ) que se llama para notificar a la dll del generador de perfiles que se está cerrando la aplicación de la tienda Windows. De hecho, debería esperar que nunca se llamen. Históricamente, muchos archivos DLL del generador de perfiles han usado esas notificaciones como lugares convenientes para vaciar las cachés en el disco, cerrar archivos, enviar notificaciones de nuevo a la interfaz de usuario del generador de perfiles, etc. Pero ahora la DLL del generador de perfiles debe organizarse de un modo ligeramente diferente.

La DLL del generador de perfiles debe registrar la información a medida que va. Por motivos de rendimiento, puede que desee procesar por lotes la información en la memoria y vaciarla en el disco a medida que el lote aumente de tamaño más allá de un umbral. Pero supongamos que se puede perder toda la información que todavía no se ha vaciado en el disco. Esto significa que querrá elegir el umbral y que la interfaz de usuario del generador de perfiles debe reforzarse para tratar con la información incompleta escrita por el archivo DLL del generador de perfiles.

## <a name="windows-runtime-metadata-files"></a>Archivos de metadatos de Windows Runtime

Está fuera del ámbito de este documento profundizar en los archivos de metadatos de Windows Runtime (WinMD). Esta sección se limita a cómo reacciona la API de generación de perfiles de CLR cuando la aplicación de la tienda Windows carga archivos WinMD que el archivo DLL del generador de perfiles está analizando.

### <a name="managed-and-non-managed-winmds"></a>Archivos winmd administrados y no administrados

Si un desarrollador usa Visual Studio para crear un nuevo proyecto de componente de Windows Runtime, una compilación de ese proyecto genera un archivo WinMD que describe los metadatos (las descripciones de tipo de clases, interfaces, etc.) creadas por el desarrollador. Si este proyecto es un proyecto de lenguaje administrado escrito en C# o Visual Basic, el mismo archivo WinMD también contiene la implementación de esos tipos (lo que significa que contiene todo el IL compilado desde el código fuente del desarrollador). Estos archivos se conocen como archivos WinMD administrados. Son interesantes en que contienen metadatos de Windows Runtime y la implementación subyacente.

Por el contrario, si un desarrollador crea un proyecto de componente de Windows Runtime para C++, una compilación de ese proyecto genera un archivo WinMD que solo contiene metadatos y la implementación se compila en un archivo DLL nativo independiente. Del mismo modo, los archivos WinMD que se incluyen en el Windows SDK solo contienen metadatos, con la implementación compilada en archivos DLL nativos independientes que se incluyen como parte de Windows.

La información siguiente se aplica a los archivos winmd administrados, que contienen metadatos e implementación, y a archivos winmd no administrado, que solo contienen metadatos.

### <a name="winmd-files-look-like-clr-modules"></a>Los archivos WinMD son similares a los módulos CLR

En lo que respecta a CLR, todos los archivos WinMD son módulos. Por lo tanto, la API de generación de perfiles de CLR indica el archivo DLL del generador de perfiles cuando se cargan los archivos WinMD y cuáles son sus los moduleids, de la misma forma que para otros módulos administrados.

El archivo DLL del generador de perfiles puede distinguir los archivos WinMD de otros módulos llamando al método [ICorProfilerInfo3:: GetModuleInfo2 (](icorprofilerinfo3-getmoduleinfo2-method.md) e inspeccionando el `pdwModuleFlags` parámetro de salida de la marca de [COR_PRF_MODULE_WINDOWS_RUNTIME](cor-prf-module-flags-enumeration.md) . (Se establece si el valor de ModuleID representa un WinMD).

### <a name="reading-metadata-from-winmds"></a>Leer metadatos de archivos winmd

Los archivos WinMD, como los módulos normales, contienen metadatos que se pueden leer a través de las [API de metadatos](../metadata/index.md). Sin embargo, CLR asigna Windows Runtime tipos a tipos de .NET Framework cuando lee archivos WinMD para que los desarrolladores que programan en código administrado y utilicen el archivo WinMD puedan tener una experiencia de programación más natural. Para ver algunos ejemplos de estas asignaciones, consulte [.NET Framework Support for Windows store apps and Windows Runtime](../../cross-platform/support-for-windows-store-apps-and-windows-runtime.md).

Por lo tanto, ¿qué vista obtendrá el generador de perfiles cuando use las API de metadatos: la vista de Windows Runtime sin formato o la vista de .NET Framework asignada?  La respuesta es que depende de usted.

Al llamar al método [ICorProfilerInfo:: GetModuleMetaData (](icorprofilerinfo-getmodulemetadata-method.md) en un archivo WinMD para obtener una interfaz de metadatos, como [IMetaDataImport](../metadata/imetadataimport-interface.md), puede elegir establecer [ofNoTransform](../metadata/coropenflags-enumeration.md) en el `dwOpenFlags` parámetro para desactivar esta asignación. De lo contrario, de forma predeterminada, se habilitará la asignación. Normalmente, un generador de perfiles mantendrá habilitada la asignación, de modo que las cadenas que obtiene el archivo DLL del generador de perfiles de los metadatos de WinMD (por ejemplo, los nombres de tipos) resulten familiares y naturales para el usuario del generador de perfiles.

### <a name="modifying-metadata-from-winmds"></a>Modificar metadatos de archivos winmd

No se admite la modificación de metadatos en archivos winmd. Si llama al método [ICorProfilerInfo:: GetModuleMetaData (](icorprofilerinfo-getmodulemetadata-method.md) para un archivo WinMD y especifica [ALWrite](../metadata/coropenflags-enumeration.md) en el `dwOpenFlags` parámetro o solicita una interfaz de metadatos grabable como [IMetaDataEmit](../metadata/imetadataemit-interface.md), [GetModuleMetaData (](icorprofilerinfo-getmodulemetadata-method.md) producirá un error. Esta es de especial importancia para los perfiles de reescritura de IL, que necesitan modificar los metadatos para admitir su instrumentación (por ejemplo, para agregar AssemblyRefs o nuevos métodos). Por lo tanto, debe comprobar [COR_PRF_MODULE_WINDOWS_RUNTIME](cor-prf-module-flags-enumeration.md) primero (como se describe en la sección anterior) y abstenerse de solicitar interfaces de metadatos grabables en dichos módulos.

### <a name="resolving-assembly-references-with-winmds"></a>Resolver referencias de ensamblado con archivos winmd

Muchos de los perfiles necesitan resolver las referencias de metadatos manualmente para ayudar con la instrumentación o la inspección de tipos. Estos profileres deben tener en cuenta la forma en que CLR resuelve las referencias de ensamblado que apuntan a archivos winmd, ya que esas referencias se resuelven de una manera totalmente diferente que las referencias de ensamblado estándar.

## <a name="memory-profilers"></a>Perfiles de memoria

El recolector de elementos no utilizados y el montón administrado no son fundamentalmente diferentes en una aplicación de la tienda Windows y en una aplicación de escritorio. Sin embargo, hay algunas diferencias sutiles que los autores del generador de perfiles deben tener en cuenta.

### <a name="forcegc-creates-a-managed-thread"></a>Forcegc (crea un subproceso administrado

Al realizar la generación de perfiles de memoria, la DLL del generador de perfiles crea normalmente un subproceso independiente a partir del cual se llama al método [forcegc (](icorprofilerinfo-forcegc-method.md) . No es nada nuevo. Pero lo que podría ser sorprendente es que el hecho de realizar una recolección de elementos no utilizados dentro de una aplicación de la tienda Windows puede transformar el subproceso en un subproceso administrado (por ejemplo, se creará un ThreadID de la API de generación de perfiles para ese subproceso).

Para entender las consecuencias de esto, es importante comprender las diferencias entre las llamadas sincrónicas y asincrónicas, tal y como se define en la API de generación de perfiles de CLR. Tenga en cuenta que esto es muy diferente del concepto de llamadas asincrónicas en aplicaciones de la tienda Windows. Vea la entrada de blog [por qué tenemos CORPROF_E_UNSUPPORTED_CALL_SEQUENCE](/archive/blogs/davbr/why-we-have-corprof_e_unsupported_call_sequence) para obtener más información.

El punto relevante es que las llamadas realizadas en los subprocesos creados por el generador de perfiles siempre se consideran sincrónicas, incluso si esas llamadas se realizan desde fuera de una implementación de uno de los métodos [ICorProfilerCallback](icorprofilercallback-interface.md) del archivo DLL del generador de perfiles. Como mínimo, que solía ser el caso. Ahora que CLR ha convertido el subproceso del generador de perfiles en un subproceso administrado debido a su llamada al [método forcegc (](icorprofilerinfo-forcegc-method.md), ese subproceso ya no se considera el subproceso del generador de perfiles. Como tal, el CLR exige una definición más rigurosa de lo que se refiere como sincrónico para ese subproceso, es decir, que una llamada se debe originar desde dentro de uno de los métodos [ICorProfilerCallback](icorprofilercallback-interface.md) de la dll del generador de perfiles para calificarse como sincrónica.

¿Qué significa esto en la práctica? La mayoría de los métodos [ICorProfilerInfo](icorprofilerinfo-interface.md) solo se pueden llamar de forma sincrónica y, de lo contrario, se producirá un error inmediatamente. Por lo tanto, si el archivo DLL del generador de perfiles vuelve a usar el subproceso de [método forcegc (](icorprofilerinfo-forcegc-method.md) para otras llamadas que normalmente se realizan en subprocesos creados por el generador de perfiles (por ejemplo, en [RequestProfilerDetach](icorprofilerinfo3-requestprofilerdetach-method.md), [requestrejit (](icorprofilerinfo4-requestrejit-method.md)o [requestrevert (](icorprofilerinfo4-requestrevert-method.md)), se le va a tener problemas. Incluso una función segura asincrónica como [DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md) tiene reglas especiales cuando se llama desde subprocesos administrados. (Vea la entrada de blog sobre el recorrido de la [pila del generador de perfiles: conceptos básicos y más allá](/archive/blogs/davbr/profiler-stack-walking-basics-and-beyond) ).

Por lo tanto, se recomienda que todos los subprocesos que crea el archivo DLL del generador de perfiles para llamar al [método forcegc (](icorprofilerinfo-forcegc-method.md) se deben usar *únicamente* con el fin de desencadenar GC y después responder a las devoluciones de llamada GC. No debe llamar a la API de generación de perfiles para realizar otras tareas, como el muestreo o desasociación de la pila.

### <a name="conditionalweaktablereferences"></a>ConditionalWeakTableReferences

A partir de la .NET Framework 4,5, hay una nueva devolución de llamada GC, [conditionalweaktableelementreferences (](icorprofilercallback5-conditionalweaktableelementreferences-method.md), que proporciona al generador de perfiles información más completa sobre los *identificadores dependientes*. Estos controles agregan de manera eficaz una referencia de un objeto de origen a un objeto de destino con el fin de administrar la duración del GC. Los identificadores dependientes no son nada nuevo y los desarrolladores que programan en código administrado han podido crear sus propios identificadores dependientes mediante la <xref:System.Runtime.CompilerServices.ConditionalWeakTable%602?displayProperty=nameWithType> clase, incluso antes de Windows 8 y el .NET Framework 4,5.

Sin embargo, las aplicaciones de la tienda Windows XAML administradas ahora hacen un uso intensivo de los identificadores dependientes. En concreto, CLR los usa para ayudar a administrar los ciclos de referencia entre los objetos administrados y los objetos Windows Runtime no administrados. Esto significa que ahora es más importante que nunca para que los profileres de memoria estén informados de estos identificadores dependientes para que se puedan visualizar junto con el resto de los bordes en el gráfico del montón. El archivo DLL del generador de perfiles debe usar [RootReferences2 (](icorprofilercallback2-rootreferences2-method.md), [ObjectReferences](icorprofilercallback-objectreferences-method.md)y [conditionalweaktableelementreferences (](icorprofilercallback5-conditionalweaktableelementreferences-method.md) juntos para formar una vista completa del gráfico del montón.

## <a name="conclusion"></a>Conclusión

Es posible usar la API de generación de perfiles de CLR para analizar el código administrado que se ejecuta dentro de las aplicaciones de la tienda Windows. De hecho, puede tomar un generador de perfiles existente que está desarrollando y realizar algunos cambios específicos para que pueda tener como destino aplicaciones de la tienda Windows. La interfaz de usuario del generador de perfiles debe usar las nuevas API para activar la aplicación de la tienda Windows en modo de depuración. Asegúrese de que el archivo DLL del generador de perfiles consume solo las API aplicables a las aplicaciones de la tienda Windows. El mecanismo de comunicación entre el archivo DLL del generador de perfiles y la interfaz de usuario del generador de perfiles debe estar escrito con las restricciones de API de aplicaciones de la tienda Windows y con conocimiento de los permisos restringidos vigentes para las aplicaciones de la tienda Windows. El archivo DLL del generador de perfiles debe tener en cuenta el modo en que CLR trata archivos winmd y cómo el comportamiento del recolector de elementos no utilizados es diferente en lo que respecta a los subprocesos administrados.

## <a name="resources"></a>Recursos

**Common Language Runtime**

- [Generación de perfiles (referencia de la API no administrada)](index.md)

- [Metadatos (referencia de la API no administrada)](../metadata/index.md)

**Interacción del CLR con el Windows Runtime**

- [Compatibilidad de .NET Framework con las aplicaciones de la Tienda Windows y Windows Runtime](../../cross-platform/support-for-windows-store-apps-and-windows-runtime.md)

**Aplicaciones de la tienda Windows**

- [Acceso a archivos y permisos (aplicaciones de Windows Runtime](/previous-versions/windows/apps/hh967755(v=win.10))

- [Obtener una licencia de desarrollador](/previous-versions/windows/apps/hh974578(v=win.10))

- [Interfaz IPackageDebugSettings](/windows/desktop/api/shobjidl_core/nn-shobjidl_core-ipackagedebugsettings)
