---
title: Los generadores de perfiles CLR y aplicaciones de la tienda de Windows
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 20a1ed9b6b613b1e4d3e5363ab9995cc81295091
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33462291"
---
# <a name="clr-profilers-and-windows-store-apps"></a>Los generadores de perfiles CLR y aplicaciones de la tienda de Windows
En este tema se describe lo que debe pensar cuando herramientas de diagnóstico de escritura que analizan los administra el código que se ejecuta dentro de una aplicación de la tienda de Windows.  También proporciona instrucciones para modificar sus herramientas de desarrollo existentes, por lo que pueden seguir funcionando cuando se ejecutan en aplicaciones de la tienda de Windows.  Para entender esta información, es mejor que si está familiarizado con la API de generación de perfiles de Common Language en tiempo de ejecución, ya ha usado esta API en una herramienta de diagnóstico que se ejecuta correctamente en aplicaciones de escritorio de Windows y ahora está interesado en modificar la herramienta Para ejecutar correctamente en aplicaciones de la tienda de Windows.  
  
 Este tema consta de las siguientes secciones:  
  
 [Introducción](#Intro)  
 [Arquitectura y terminología](#Arch)  
 [Dispositivos Windows RT](#RT)  
[API de Windows en tiempo de ejecución de consumo](#Consuming)  
[Cargar el archivo DLL del generador de perfiles](#Loading)  
 [Consideraciones comunes para el inicio y adjuntar cargas](#Common)  
 [Carga de inicio](#Startup)  
 [Adjuntar carga](#Attach)  
[Ejecuta dentro de la aplicación de la tienda de Windows](#Running)  
 [Pegar a las API de la aplicación de tienda Windows](#APIs)  
 [Permisos restringidos](#Permissions)  
 [Comunicación entre procesos](#Interprocess)  
 [Ninguna notificación de cierre](#Shutdown)  
[Archivos de metadatos en tiempo de ejecución de Windows](#Metadata)  
 [Archivos de Winmd administrado y no administrado](#WMDs)  
 [Archivos de WinMD aspecto de los módulos CLR](#CLRModules)  
 [Leer metadatos de Winmd](#Reading)  
 [Modificar los metadatos de Winmd](#Modifying)  
 [Resolver las referencias de ensamblado con archivos Winmd](#Resolving)  
[Generadores de perfiles de memoria](#Profilers)  
 [ForceGC crea un subproceso administrado](#ForceGC)  
 [ConditionalWeakTableReferences](#WeakTable)  
[Conclusión](#Conclusion)  
[Recursos](#Resources)  
  
<a name="Intro"></a>   
## <a name="introduction"></a>Introducción  
 Si ha realizado más allá del párrafo de introducción, a continuación, que está familiarizado con la API de generación de perfiles de CLR.  Ya se ha escrito una herramienta de diagnóstico que funciona bien con aplicaciones de escritorio administradas.  Ahora tiene curiosidad qué hacer para que la herramienta funciona con una aplicación de la tienda de Windows administrada.  Quizás ya se probó solucionar este problema y ha detectado que no es una tarea sencilla.  De hecho, existen una serie de cuestiones que podrían no detectarse a todos los desarrolladores de herramientas.  Por ejemplo:  
  
-   Aplicaciones de la tienda de Windows se ejecutan en un contexto con permisos reducidos graves.  
  
-   Archivos de metadatos de Windows tienen características únicas en comparación con los módulos administrados tradicionales.  
  
-   Aplicaciones de la tienda de Windows tienen un hábito de suspender por sí mismos cuando interactividad deja de funcionar.  
  
-   Los mecanismos de comunicación entre procesos ya no funcionen por distintas razones.  
  
 En este tema se enumera las cosas que debe tener en cuenta y cómo tratar con ellos correctamente.  
  
 Si está familiarizado con la API de generación de perfiles de CLR, omitir hasta los recursos al final de este tema para buscar la mejor información de introducción.  
  
 Proporciona información sobre la API específicas de Windows y cómo debería usarse también está fuera del ámbito de este tema.  Considere la posibilidad de este tema un punto de partida y consulte MSDN para obtener más información sobre las API de Windows al que hace referencia aquí.  
  
<a name="Arch"></a>   
## <a name="architecture-and-terminology"></a>Arquitectura y terminología  
 Normalmente, una herramienta de diagnóstico tiene una arquitectura como se muestra en la siguiente ilustración. Usa el término "generador de perfiles", pero muchas de estas herramientas ir más allá de rendimiento típico o la generación de perfiles de memoria en áreas como la cobertura de código, simular marcos de objeto, viaje en el tiempo de depuración, aplicación de supervisión y así sucesivamente.  Para simplificar, este tema continuará hacer referencia a todas estas herramientas como los generadores de perfiles.  
  
 En este tema se utiliza la siguiente terminología:  
  
 Application  
 Se trata de la aplicación que está analizando el generador de perfiles.  Normalmente, el desarrollador de esta aplicación está utilizando el generador de perfiles para ayudar a diagnosticar problemas con la aplicación.  Tradicionalmente, esta aplicación sería una aplicación de escritorio de Windows, pero en este tema se analizan en aplicaciones de la tienda de Windows.  
  
 Archivo DLL del generador de perfiles  
 Éste es el componente que se carga en el espacio de procesos de la aplicación que se va a analizar.  Este componente, también conocido como el generador de perfiles "agente", implementa el [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)[ICorProfilerCallback (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)(2,3, etc.) e interfaces de consume el [ ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)(2,3, etc.) interfaces para recopilar datos acerca de la aplicación analizada y posiblemente modificarán aspectos del comportamiento de la aplicación.  
  
 Interfaz de usuario del generador de perfiles  
 Se trata de una aplicación de escritorio que interactúa el usuario del generador de perfiles.  Es responsable de mostrar el estado de la aplicación para el usuario y proporcionar al usuario los medios para controlar el comportamiento de la aplicación analizado.  Este componente siempre se ejecuta en su propio espacio de proceso independiente desde el espacio de proceso de la aplicación que se está generando el perfil.  La interfaz de usuario del generador de perfiles también pueden actuar como el "adjunta" desencadenador, que es el proceso que llama el [ICLRProfiling:: AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md) método, para hacer que la aplicación cargar la DLL del generador de perfiles en esos casos donde el archivo DLL del generador de perfiles no analizada cargar al inicio.  
  
> [!IMPORTANT]
>  La interfaz de usuario del generador de perfiles debe tener una aplicación de escritorio de Windows, incluso cuando se utiliza para el control y el informe en una aplicación de la tienda de Windows.  No se espera que sea capaz de empaquetar y distribuir la herramienta de diagnóstico en la tienda Windows.  La herramienta debe hacer cosas que no se pueden hacer aplicaciones de la tienda de Windows y muchos de esos elementos residen dentro de la interfaz de usuario del generador de perfiles.  
  
 En este documento, el código de ejemplo supone:  
  
-   La DLL del generador de perfiles está escrito en C++, porque debe ser un archivo DLL nativo, según los requisitos de la API de generación de perfiles de CLR.  
  
-   La interfaz de usuario del generador de perfiles está escrito en C#.  No es necesario, pero dado que no hay ningún requisito en el idioma para el proceso de la IU generador de perfiles, ¿por qué no seleccionar un idioma que sea conciso y simple?  
  
<a name="RT"></a>   
### <a name="windows-rt-devices"></a>Dispositivos Windows RT  
 Dispositivos Windows RT bastante están bloqueados.  Los generadores de perfiles de aplicaciones de terceros simplemente no se pueden cargadas en estos dispositivos.  Este documento se centra en equipos con Windows 8.  
  
<a name="Consuming"></a>   
## <a name="consuming-windows-runtime-apis"></a>API de Windows en tiempo de ejecución de consumo  
 En varios escenarios descritos en las secciones siguientes, la aplicación de escritorio de interfaz de usuario del generador de perfiles se debe consumir algunos nuevos Windows Runtime APIs.  Es conveniente consultar la documentación para entender las API de Windows en tiempo de ejecución se puedan usar desde aplicaciones de escritorio y si su comportamiento es diferente cuando llama desde la tienda Windows y aplicaciones de escritorio de aplicaciones.  
  
 Si la interfaz de usuario del generador de perfiles está escrita en código administrado, habrá unos pocos pasos que debe hacer para que consumen los Windows en tiempo de ejecución APIs fácil.  Consulte la [administrados de aplicaciones de escritorio y Windows Runtime](http://go.microsoft.com/fwlink/?LinkID=271858) artículo para obtener más información.  
  
<a name="Loading"></a>   
## <a name="loading-the-profiler-dll"></a>Cargar el archivo DLL del generador de perfiles  
 Esta sección describe cómo la interfaz de usuario del generador de perfiles hace que la aplicación de la tienda de Windows cargar la DLL del generador de perfiles.  El código que se tratan en esta sección pertenece a la aplicación de escritorio de interfaz de usuario del generador de perfiles y, por tanto, implica el uso de las API de Windows que sean seguros para aplicaciones de escritorio pero no necesariamente seguros para aplicaciones de la tienda de Windows.  
  
 La interfaz de usuario del generador de perfiles puede provocar la DLL del generador de perfiles debe cargarse en el espacio de proceso de la aplicación de dos maneras:  
  
-   Al iniciar la aplicación, ya que controla las variables de entorno.  
  
-   Si se adjunta a la aplicación después de inicio mediante una llamada a la [ICLRProfiling:: AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md) método.  
  
 Uno de los obstáculos primera obtendrá adjuntar-carga de la DLL del generador de perfiles para funcionar correctamente con aplicaciones de la tienda de Windows y carga de inicio.  Ambas formas de cargar comparten algunas consideraciones especiales, por eso comenzaremos con ellos.  
  
<a name="Common"></a>   
### <a name="common-considerations-for-startup-and-attach-loads"></a>Consideraciones comunes para el inicio y adjuntar cargas  
 **Firma el archivo DLL del generador de perfiles**  
 Cuando Windows intenta cargar la DLL del generador de perfiles, comprueba que la DLL del generador de perfiles está firmado correctamente.  De lo contrario, se produce un error en la carga de forma predeterminada. Existen dos modos para hacer esto:  
  
-   Asegúrese de que la DLL del generador de perfiles está firmado.  
  
-   Indicar que el usuario que debe instalar una licencia de desarrollador en su equipo Windows 8 antes de usar la herramienta.  Esto puede hacerse automáticamente desde Visual Studio o manualmente desde un símbolo del sistema.  Para obtener más información, consulte [obtener una licencia de desarrollador](https://msdn.microsoft.com/library/windows/apps/Hh974578.aspx).  
  
 **Permisos de sistema de archivos**  
 La aplicación de la tienda de Windows debe tener permiso para cargar y ejecutar la DLL del generador de perfiles desde la ubicación en el sistema de archivos en el que reside.  De forma predeterminada, la aplicación de la tienda de Windows no tiene este permiso en la mayoría de los directorios y cualquier intento para cargar la DLL del generador de perfiles producirá una entrada en el registro de eventos de aplicación de Windows que es algo parecido a esto:  
  
```Output  
NET Runtime version 4.0.30319.17929 - Loading profiler failed during CoCreateInstance.  Profiler CLSID: '{xxxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx}'.  HRESULT: 0x80070005.  Process ID (decimal): 4688.  Message ID: [0x2504].  
```  
  
 Por lo general, solo se permiten aplicaciones de la tienda de Windows para tener acceso a un conjunto limitado de ubicaciones en el disco.  Cada aplicación de la tienda de Windows puede tener acceso a sus propias carpetas de datos de aplicación, así como algunas otras áreas del sistema de archivos para los que tienen acceso todas las aplicaciones de la tienda de Windows.  Es mejor instalar la DLL del generador de perfiles y sus dependencias en algún lugar en los archivos de programa o archivos de programa (x86), dado que todas las aplicaciones de la tienda de Windows han permisos read y execute no existe de forma predeterminada.  
  
<a name="Startup"></a>   
### <a name="startup-load"></a>Carga de inicio  
 Normalmente, en una aplicación de escritorio, la interfaz de usuario del generador de perfiles le solicita una carga de inicio de la DLL del generador de perfiles mediante la inicialización de un bloque de entorno que contiene las variables de entorno necesarias de API de generación de perfiles de CLR (es decir, `COR_PROFILER`, `COR_ENABLE_PROFILING`, y `COR_PROFILER_PATH`), y a continuación, crear un nuevo proceso con ese bloque de entorno.  Lo mismo sucede para aplicaciones de la tienda de Windows, pero los mecanismos son diferentes.  
  
 **No se ejecutan con privilegios elevados**  
 Si el proceso intenta generar la aplicación de la tienda de Windows B de proceso, un proceso se debería ejecutar en integridad media nivel, no en el nivel de integridad alta (que no es, elevado).  Esto significa que la interfaz de usuario del generador de perfiles se debe ejecutar en el nivel de integridad media, o debe generar otro proceso escritorio en nivel de integridad medio a cargo de iniciar la aplicación de la tienda de Windows.  
  
 **Elegir una aplicación de la tienda de Windows al perfil**  
 En primer lugar, deberá pedir a los usuarios del generador de perfiles qué aplicación de la tienda de Windows para iniciar.  Para aplicaciones de escritorio, quizás le mostrará un cuadro de diálogo de exploración de archivos, y el usuario podría buscar y seleccionar un archivo .exe.  Pero aplicaciones de la tienda de Windows son diferentes y, mediante un cuadro de diálogo de examinar no tiene sentido.  En su lugar, es mejor mostrar al usuario una lista de aplicaciones de la tienda de Windows instalado para que seleccione en el usuario.  
  
 Puede usar el [PackageManager clase](https://msdn.microsoft.com/library/windows/apps/windows.management.deployment.packagemanager.aspx) para generar esta lista.  `PackageManager` es una clase en tiempo de ejecución de Windows que está disponible para aplicaciones de escritorio y de hecho es *sólo* disponibles para aplicaciones de escritorio.  
  
 El siguiente ejemplo de código de una interfaz de usuario de generador de perfiles hipotética escrito como una aplicación de escritorio en C# yses la `PackageManager` para generar una lista de aplicaciones de Windows:  
  
```csharp  
string currentUserSID = WindowsIdentity.GetCurrent().User.ToString();  
IAppxFactory appxFactory = (IAppxFactory) new AppxFactory();  
PackageManager packageManager = new PackageManager();  
IEnumerable<Package> packages = packageManager.FindPackagesForUser(currentUserSID);  
```  
  
 **Especifica el bloque de entorno personalizado**  
 Una nueva interfaz de COM, [IPackageDebugSettings](https://msdn.microsoft.com/library/hh438393\(v=vs.85\).aspx), le permite personalizar el comportamiento de ejecución de una aplicación de tienda Windows para facilitar algunas formas de diagnóstico.  Uno de sus métodos, [EnableDebugging](https://msdn.microsoft.com/library/hh438395\(v=vs.85\).aspx), permite pasar un bloque de entorno para la aplicación de la tienda de Windows cuando se inicia, junto con otros efectos útiles igual que la desactivación de la suspensión de proceso automático.  El bloque de entorno es importante porque es donde debe especificar las variables de entorno (`COR_PROFILER`, `COR_ENABLE_PROFILING`, y `COR_PROFILER_PATH)`) utilizados por el CLR para cargar la DLL del generador de perfiles.  
  
 Considere el fragmento de código siguiente:  
  
```csharp  
IPackageDebugSettings pkgDebugSettings = new PackageDebugSettings();  
pkgDebugSettings.EnableDebugging(packgeFullName, debuggerCommandLine,   
                                                                 (IntPtr)fixedEnvironmentPzz);  
```  
  
 Hay un par de elementos que necesite realizar correctamente:  
  
-   `packageFullName` se puede determinar al recorrer en iteración los paquetes y arrastrar `package.Id.FullName`.  
  
-   `debuggerCommandLine` es un poco más interesante.  Para pasar el bloque de entorno personalizado para la aplicación de la tienda de Windows, debe escribir al suyo propio, simplista depurador ficticio.  Genera de Windows, la aplicación de la tienda de Windows suspendido y, a continuación, asocia al depurador al ejecutar al depurador con una línea de comandos como en este ejemplo:  
  
    ```Output  
    MyDummyDebugger.exe -p 1336 -tid 1424  
    ```  
  
     donde `-p 1336` significa que la aplicación de la tienda de Windows tiene 1336 de Id. de proceso, y `-tid 1424` significa 1424 de Id. de subproceso es el subproceso que está suspendido.  El depurador ficticio haría analizar ThreadID desde la línea de comandos, reanudar ese subproceso y, a continuación, salir.  
  
     Presentamos algunos ejemplos de código de C++ para hacer esto (asegúrese de agregar la comprobación de errores!):  
  
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
  
     Debe implementar este depurador ficticio como parte de la instalación de la herramienta de diagnóstico y, a continuación, especifique la ruta de acceso a este depurador en el `debuggerCommandLine` parámetro.  
  
 **Iniciar la aplicación de tienda Windows**  
 Por último, ha llegado el momento para iniciar la aplicación de la tienda de Windows. Si ya ya has intentado hacer usted mismo, es podrán que haya observado que [CreateProcess](https://msdn.microsoft.com/library/windows/desktop/ms682425\(v=vs.85\).aspx) es no, cómo crear un proceso de aplicación de tienda Windows.  En su lugar, debe utilizar el [IApplicationActivationManager::ActivateApplication](https://msdn.microsoft.com/library/windows/desktop/Hh706903\(v=vs.85\).aspx) método.  Para ello, debe obtener el identificador de modelo de usuario de aplicación de la aplicación de la tienda de Windows que está iniciando.  Y eso significa que debe hacer un poco indagar en el manifiesto.  
  
 Al recorrer en iteración los paquetes (vea "Elegir un almacén de aplicación al perfil de Windows" en la [carga inicio](#Startup) sección anterior), deseará agarre el conjunto de aplicaciones incluidas en el manifiesto del paquete actual:  
  
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
  
 Sí, un paquete puede tener varias aplicaciones, y cada aplicación tiene su propio identificador de modelo de usuario de aplicación.  Por lo que debe tener preguntar al usuario qué aplicación al perfil y agarre el identificador de modelo de aplicación de usuario de esa aplicación en particular:  
  
```csharp  
while (appsEnum.GetHasCurrent() != 0)  
{  
    IAppxManifestApplication app = appsEnum.GetCurrent();  
    string appUserModelId = app.GetAppUserModelId();  
…  
```  
  
 Por último, ahora tiene lo que necesita para iniciar la aplicación de la tienda de Windows:  
  
```csharp  
IApplicationActivationManager appActivationMgr = new ApplicationActivationManager();  
appActivationMgr.ActivateApplication(appUserModelId, appArgs, ACTIVATEOPTIONS.AO_NONE, out pid);  
```  
  
 **No olvide llamar a DisableDebugging**  
 Cuando llama a [IPackageDebugSettings::EnableDebugging](https://msdn.microsoft.com/library/hh438395\(v=VS.85\).aspx), realiza una promesa que debería realizar una limpieza después usted mismo mediante una llamada a la [IPackageDebugSettings::DisableDebugging](https://msdn.microsoft.com/library/hh438394\(v=vs.85\).aspx) método, por lo que debe asegurarse de realizar que cuando la sesión de generación de perfiles es a través.  
  
<a name="Attach"></a>   
### <a name="attach-load"></a>Adjuntar carga  
 Cuando la interfaz de usuario del generador de perfiles desea adjuntar su DLL del generador de perfiles a una aplicación que ya ha empezado a ejecutarse, utiliza [ICLRProfiling:: AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md).  Lo mismo sucede con las aplicaciones de la tienda de Windows.  Pero además de las consideraciones comunes enumeradas anteriormente, debe asegurarse de que la aplicación de la tienda de Windows de destino no se suspende.  
  
 **EnableDebugging**  
 Al igual que con la carga de inicio, llame a la [IPackageDebugSettings::EnableDebugging](https://msdn.microsoft.com/library/hh438395\(v=VS.85\).aspx) método.  No necesita para pasar un bloque de entorno, pero necesita uno de sus otras funcionalidades: deshabilitar la suspensión de proceso automático.  En caso contrario, cuando se llama a la interfaz de usuario del generador de perfiles [AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md), se puede suspender la aplicación de la tienda de Windows de destino.  De hecho, esto es probable que si el usuario ahora está interactuando con la interfaz de usuario del generador de perfiles y la aplicación de la tienda de Windows no está activa en cualquiera de las pantallas del usuario.  Y si la tienda de Windows se suspende la aplicación, no podrá responder a alguna señal que CLR se envía a ella para asociar la DLL del generador de perfiles.  
  
 Por lo que desea hacer algo parecido a esto:  
  
```csharp  
IPackageDebugSettings pkgDebugSettings = new PackageDebugSettings();  
pkgDebugSettings.EnableDebugging(packgeFullName, null /* debuggerCommandLine */,   
                                                                 IntPtr.Zero /* environment */);  
```  
  
 Se trata de la misma llamada haría que en el caso de carga de inicio, salvo que no especifica una línea de comandos del depurador o un bloque de entorno.  
  
 **DisableDebugging**  
 Como siempre, no olvide llamar a [IPackageDebugSettings::DisableDebugging](https://msdn.microsoft.com/library/hh438394\(v=vs.85\).aspx) cuando se completa la sesión de generación de perfiles.  
  
<a name="Running"></a>   
## <a name="running-inside-the-windows-store-app"></a>Ejecuta dentro de la aplicación de la tienda de Windows  
 Por lo que la aplicación de la tienda de Windows finalmente ha cargado la DLL del generador de perfiles.  Ahora la DLL del generador de perfiles debe ser imparten cómo reproducir las distintas reglas necesarias para aplicaciones de la tienda de Windows, incluidos los que están permitidas las API y cómo ejecutar con permisos reducen.  
  
<a name="APIs"></a>   
### <a name="stick-to-the-windows-store-app-apis"></a>Pegar a las API de la aplicación de tienda Windows  
 A medida que explora la API de Windows, observará que se documenta todas las API como aplicable a las aplicaciones de escritorio, aplicaciones de la tienda de Windows o ambos.  Por ejemplo, el **requisitos** sección de la documentación de la [InitializeCriticalSectionAndSpinCount](https://msdn.microsoft.com/library/windows/desktop/ms683476\(v=vs.85\).aspx) función indica que la función se aplica a solo las aplicaciones de escritorio. En cambio, el [InitializeCriticalSectionEx](https://msdn.microsoft.com/library/windows/desktop/ms683477\(v=vs.85\).aspx) función está disponible para aplicaciones de escritorio y aplicaciones de la tienda de Windows.  
  
 Al desarrollar la DLL del generador de perfiles, tratarlo como si fuera una aplicación de la tienda de Windows y sólo usen las API que se documentan como disponibles para aplicaciones de la tienda de Windows.  Analizar sus dependencias (por ejemplo, puede ejecutar `link /dump /imports` en la DLL del generador de perfiles para auditar) y, a continuación, buscar los documentos para ver cuál de las dependencias son Aceptar y cuáles no.  En la mayoría de los casos, se pueden corregir sus infracciones simplemente reemplazarlos con una forma más reciente de la API que se documenta como seguro (por ejemplo, reemplace [InitializeCriticalSectionAndSpinCount](https://msdn.microsoft.com/library/windows/desktop/ms683476\(v=vs.85\).aspx) con [ InitializeCriticalSectionEx](https://msdn.microsoft.com/library/windows/desktop/ms683477\(v=vs.85\).aspx)).  
  
 Puede observar que la DLL del generador de perfiles llama a algunas API que se aplican a solo las aplicaciones de escritorio y aún parecen funciona incluso cuando la DLL del generador de perfiles se carga dentro de una aplicación de la tienda de Windows.  Tenga en cuenta que es muy arriesgado utilizar cualquier API no documentado para su uso con aplicaciones de la tienda de Windows en la DLL del generador de perfiles cuando se carga en un proceso de aplicación de tienda Windows:  
  
-   No se garantiza que estas API para que funcione cuando se llama en el contexto único que se ejecutan aplicaciones de la tienda de Windows en.  
  
-   Estas API no podrían funcionar de manera coherente cuando se llama desde dentro de distintos procesos de aplicación de tienda Windows.  
  
-   Estas API pueden parecer que funcionan correctamente desde aplicaciones de la tienda de Windows en la versión actual de Windows, pero se pueden dividir o deshabilitarse en versiones futuras de Windows.  
  
 Lo mejor es corregir todas las infracciones de sus y evitar el riesgo.  
  
 Es posible que sea absolutamente no puede hacer sin una API concreta y no se puede encontrar un sustituto adecuado para aplicaciones de la tienda de Windows.  En tal caso, como mínimo:  
  
-   Probar, probar, probar el daylights vivo fuera de su uso de esta API.  
  
-   Comprender que la API de repente podría interrumpir o desaparecer si se llama desde dentro de la tienda Windows aplicaciones en versiones futuras de Windows.  Esto no se considera un problema de compatibilidad con Microsoft, y admite el uso del mismo no será una prioridad.  
  
<a name="Permissions"></a>   
### <a name="reduced-permissions"></a>Permisos restringidos  
 Está fuera del ámbito de este tema para enumerar todas las formas en que los permisos de aplicación de tienda Windows difieren de las aplicaciones de escritorio.  Pero, por supuesto, el comportamiento será diferente cada vez que la DLL del generador de perfiles (cuando se cargan en una aplicación de tienda Windows en comparación con una aplicación de escritorio) intenta tener acceso a los recursos.  El sistema de archivos es el ejemplo más común.  Hay pero algunas se coloca en el disco que se puede tener acceso a una determinada aplicación de tienda Windows (vea [acceso y los permisos de archivo (aplicaciones de Windows Runtime](https://msdn.microsoft.com/library/windows/apps/hh967755.aspx)), y será la DLL del generador de perfiles en las mismas restricciones.  Probar exhaustivamente el código.  
  
<a name="Interprocess"></a>   
### <a name="inter-process-communication"></a>Comunicación entre procesos  
 Como se muestra en el diagrama al principio de este documento, probablemente tenga para comunicarse con el generador de perfiles de interfaz de usuario (que se ejecuta en un espacio de proceso de una aplicación de escritorio independiente) a través de su propio proceso personalizado entre la DLL del generador de perfiles (cargado en el espacio de procesos de aplicación de tienda Windows) canal de comunicación entre procesos (IPC).  La interfaz de usuario del generador de perfiles envía señales a la DLL del generador de perfiles para modificar su comportamiento y la DLL del generador de perfiles devuelve datos desde la aplicación de tienda Windows analizada a la interfaz de usuario del generador de perfiles para posteriores al procesamiento y mostrar al usuario del generador de perfiles.  
  
 La mayoría de los generadores de perfiles necesitan para que funcione este modo, pero las opciones de mecanismos IPC están más limitadas al cargar la DLL del generador de perfiles en una aplicación de la tienda de Windows.  Por ejemplo, las canalizaciones con nombre no forman parte de la aplicación de la tienda de Windows SDK, por lo que no se pueden usar.  
  
 Pero, por supuesto, los archivos todavía están en, aunque de forma más limitada.  Eventos también están disponibles.  
  
 **Comunique a través de archivos**  
 La mayoría de los datos probablemente pasará entre el archivo DLL del generador de perfiles y la interfaz de usuario del generador de perfiles a través de archivos.  La clave consiste en elegir una ubicación del archivo que han leído del archivo DLL del generador de perfiles (en el contexto de una aplicación de la tienda de Windows) y la interfaz de usuario del generador de perfiles y el acceso de escritura a.  Por ejemplo, la ruta de acceso de la carpeta temporal es una ubicación que pueden tener acceso la DLL del generador de perfiles y la interfaz de usuario del generador de perfiles, pero no puede tener acceso a ningún otro paquete de aplicación de tienda Windows (Blindaje, por tanto, cualquier información de que registro desde otros paquetes de aplicación de tienda Windows).  
  
 La interfaz de usuario del generador de perfiles y el archivo DLL del generador de perfiles pueden determinar esta ruta de acceso por separado.  La interfaz de usuario del generador de perfiles, cuando se recorre en iteración todos los paquetes instalados para el usuario actual (vea el ejemplo de código anterior), se obtiene acceso a la `PackageId` (clase), desde el que la ruta de acceso de la carpeta temporal puede obtenerse con código similar de este fragmento de código.  (Como siempre, comprobación de errores se omite por razones de brevedad).  
  
```csharp  
// C# code for the Profiler UI.  
ApplicationData appData =  
    ApplicationDataManager.CreateForPackageFamily(  
        packageId.FamilyName);  
  
tempDir = appData.TemporaryFolder.Path;  
```  
  
 Mientras tanto, la DLL del generador de perfiles puede hacer lo mismo básicamente, aunque es posible más llegar fácilmente a la [ApplicationData](https://msdn.microsoft.com/library/windows/apps/windows.storage.applicationdata.aspx) clase mediante el uso de la [ApplicationData.Current](https://msdn.microsoft.com/library/windows/apps/windows.storage.applicationdata.current.aspx) propiedad.  
  
 **Comunique a través de eventos**  
 Si desea que la semántica de señalización simple entre la interfaz de usuario del generador de perfiles y el archivo DLL del generador de perfiles, puede usar los eventos de aplicaciones de la tienda de Windows, así como aplicaciones de escritorio.  
  
 Desde el archivo de DLL del generador de perfiles, puede llamar simplemente la [CreateEventEx](https://msdn.microsoft.com/library/windows/desktop/ms682400\(v=vs.85\).aspx) función para crear un evento con nombre con cualquier nombre que quiera.  Por ejemplo:  
  
```cpp  
// Profiler DLL in Windows Store app (C++).  
CreateEventEx(   
    NULL,  // Not inherited  
    "MyNamedEvent"  
    CREATE_EVENT_MANUAL_RESET, /* explicit ResetEvent() required; leave initial state unsignaled */  
    EVENT_ALL_ACCESS);  
```  
  
 La interfaz de usuario del generador de perfiles, a continuación, debe buscar ese evento con nombre en el espacio de nombres de la aplicación de la tienda Windows.  Por ejemplo, podría llamar la interfaz de usuario del generador de perfiles [CreateEventEx](https://msdn.microsoft.com/library/windows/desktop/ms682400\(v=vs.85\).aspx), especificar el nombre de evento como  
  
 `AppContainerNamedObjects\<acSid>\MyNamedEvent`  
  
 `<acSid>` es AppContainer SID la aplicación de la tienda Windows.  Una sección anterior de este tema se ha explicado cómo recorrer en iteración los paquetes instalados para el usuario actual.  De ese código de ejemplo, puede obtener el identificador de paquete.  Y desde el identificador de paquete, puede obtener el `<acSid>` con código similar al siguiente:  
  
```csharp  
IntPtr acPSID;  
DeriveAppContainerSidFromAppContainerName(packageId.FamilyName, out acPSID);  
  
string acSid;  
ConvertSidToStringSid(acPSID, out acSid);  
  
string acDir;  
GetAppContainerFolderPath(acSid, out acDir);  
```  
  
<a name="Shutdown"></a>   
### <a name="no-shutdown-notifications"></a>Ninguna notificación de cierre  
 Cuando se ejecuta en una aplicación de la tienda de Windows, la DLL del generador de perfiles no debe confiar en cualquier [ICorProfilerCallback:: Shutdown](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-shutdown-method.md) o incluso [DllMain](https://msdn.microsoft.com/library/windows/desktop/ms682583\(v=vs.85\).aspx) (con `DLL_PROCESS_DETACH`) que se llama para notificar a la DLL del generador de perfiles que se está cerrando la aplicación de la tienda de Windows.  De hecho, debe esperar nunca se llamará.  Históricamente, muchos archivos DLL del generador de perfiles ha usado las notificaciones como lugares adecuados para vaciar las memorias caché de disco, cerrar archivos, enviar notificaciones a la interfaz de usuario del generador de perfiles, etcetera.  Pero ahora, la DLL del generador de perfiles debe estar organizada de forma ligeramente diferente.  
  
 La DLL del generador de perfiles debe ser la información de registro a medida que pasa.  Por motivos de rendimiento, puede que desee procesar por lotes información en la memoria y vaciar en el disco a medida que crece el lote de tamaño más allá de determinado umbral.  Pero suponga que se puede perder toda la información aún no se vacían en el disco.  Esto significa que desea elegir con cuidado el umbral y que la interfaz de usuario del generador de perfiles debe ser protegido para tratar con información incompleta escribiendo la DLL del generador de perfiles.  
  
<a name="Metadata"></a>   
## <a name="windows-runtime-metadata-files"></a>Archivos de metadatos en tiempo de ejecución de Windows  
 Está fuera del ámbito de este documento se describe con detalle en los metadatos de Windows Runtime (WinMD) son archivos.    En esta sección se limita a cómo la API de generación de perfiles de CLR reacciona cuando se cargan los archivos de WinMD por la aplicación de la tienda de Windows que está analizando la DLL del generador de perfiles.  
  
<a name="WMDs"></a>   
### <a name="managed-and-non-managed-winmds"></a>Archivos de Winmd administrado y no administrado  
 Si un desarrollador usa Visual Studio para crear un nuevo proyecto de componente de Windows en tiempo de ejecución, una compilación del proyecto genera un archivo de WinMD que describe los metadatos (las descripciones de tipo de clases, interfaces, etc.) creado por el desarrollador.  Si este proyecto es un proyecto de lenguaje administrado escrito en C# o VB, ese mismo archivo de WinMD también contiene la implementación de esos tipos (es decir, que contiene IL compilado a partir de código de origen del desarrollador).  Estos archivos se conocen como archivos de WinMD administrados.  Sean más interesantes en que contienen metadatos en tiempo de ejecución de Windows y la implementación subyacente.  
  
 En cambio, si un desarrollador crea un proyecto de componente de Windows en tiempo de ejecución de C++, una compilación del proyecto crea un archivo de WinMD que solo contiene metadatos y la implementación se compila en un archivo DLL nativo independiente.  De forma similar, los archivos de WinMD que se incluyen en el SDK de Windows contienen sólo metadatos, con la implementación que se compilan en archivos DLL nativos independientes que se incluyen como parte de Windows.  
  
 La siguiente información se aplica a ambos archivos Winmd administrado, que contienen la implementación y los metadatos, y archivos Winmd no administrado, que contiene sólo metadatos.  
  
<a name="CLRModules"></a>   
### <a name="winmd-files-look-like-clr-modules"></a>Archivos de WinMD aspecto de los módulos CLR  
 En lo que se refiere el CLR, todos los archivos de WinMD son módulos.  Por consiguiente, la API de generación de perfiles de CLR indica la DLL del generador de perfiles cuando se cargan archivos de WinMD y cuáles son sus los ModuleIDs, en la misma forma que para otros módulos administrados.  
  
 La DLL del generador de perfiles puede distinguir los archivos de WinMD desde otros módulos mediante una llamada a la [ICorProfilerInfo3:: Getmoduleinfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getmoduleinfo2-method.md) método e inspeccionando el `pdwModuleFlags` para el parámetro de salida el [COR_PRF_MODULE_WINDOWS_ En tiempo de ejecución](../../../../docs/framework/unmanaged-api/profiling/cor-prf-module-flags-enumeration.md) marca.  (Se establece únicamente si el identificador de módulo representa un archivo WinMD).  
  
<a name="Reading"></a>   
### <a name="reading-metadata-from-winmds"></a>Leer metadatos de Winmd  
 Archivos de WinMD, similar a los módulos regulares, contienen metadatos que se pueden leer mediante el [Metadata APIs](../../../../docs/framework/unmanaged-api/metadata/index.md).  Sin embargo, CLR asigna tipos de Windows Runtime a tipos de .NET Framework cuando lee que archivos de WinMD para que los desarrolladores programar en código administrado y consumir el archivo WinMD pueden tener una experiencia de programación más natural.  Algunos ejemplos de estas asignaciones, consulte [compatibilidad de .NET Framework Windows almacén de aplicaciones y en tiempo de ejecución de Windows](../../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md).  
  
 ¿Por lo que la vista que el generador de perfiles obtendrá cuando utiliza las API de metadatos: la vista en tiempo de ejecución de Windows sin formato o la vista de .NET Framework asignada?  La respuesta: es para usted.  
  
 Cuando se llama a la [ICorProfilerInfo:: GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) método en un archivo WinMD para obtener una interfaz de metadatos, como [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md), puede elegir establecer [ofNoTransform](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md)en la `dwOpenFlags` parámetro para desactivar esta asignación.  En caso contrario, de forma predeterminada, se habilitará la asignación.  Normalmente, un generador de perfiles mantendrá la asignación está habilitada, por lo que las cadenas que se obtiene de la DLL del generador de perfiles de los metadatos de WinMD (por ejemplo, los nombres de tipos) tendrá un aspecto natural para el usuario del generador de perfiles y familiar.  
  
<a name="Modifying"></a>   
### <a name="modifying-metadata-from-winmds"></a>Modificar los metadatos de Winmd  
 No se admite la modificación de metadatos en archivos Winmd.  Si se llama a la [ICorProfilerInfo:: GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) método para un archivo WinMD archivo y especifique [marca ofWrite](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) en el `dwOpenFlags` parámetro o solicite una interfaz de metadatos puede escribir como [ IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md), [GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) se producirá un error.  Esto es de particular importancia para la reescritura IL los generadores de perfiles, que es necesario modificar los metadatos para admitir su instrumental (por ejemplo, para agregar nuevos métodos o AssemblyRefs).  Por lo que debe comprobar si hay [COR_PRF_MODULE_WINDOWS_RUNTIME](../../../../docs/framework/unmanaged-api/profiling/cor-prf-module-flags-enumeration.md) primero (como se describe en la sección anterior) y absténgase solicitan interfaces de metadatos grabable en estos módulos.  
  
<a name="Resolving"></a>   
### <a name="resolving-assembly-references-with-winmds"></a>Resolver las referencias de ensamblado con archivos Winmd  
 Muchos de los generadores de perfiles necesitan resolver las referencias a metadatos manualmente para ayudar a Instrumental o inspección de tipo.  Tales generadores de perfiles necesitan tener en cuenta cómo el CLR resuelve las referencias de ensamblado que apuntan a archivos Winmd, puesto que esas referencias se resuelven de forma totalmente diferente que las referencias de ensamblados estándar.  
  
<a name="Profilers"></a>   
## <a name="memory-profilers"></a>Generadores de perfiles de memoria  
 El recolector de elementos no utilizados y el montón administrado no son fundamentalmente diferentes en una aplicación de la tienda de Windows y una aplicación de escritorio.  Sin embargo, hay algunas diferencias sutiles que deben tener en cuenta los autores del generador de perfiles.  
  
<a name="ForceGC"></a>   
### <a name="forcegc-creates-a-managed-thread"></a>ForceGC crea un subproceso administrado  
 Cuando se realiza la generación de perfiles de memoria, la DLL del generador de perfiles crea normalmente un subproceso independiente desde el que se va a llamar a la [ForceGC (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-forcegc-method.md) método.  Esto no es nada nuevo.  Pero lo que podría ser sorprendente es que el hecho de realizar una recolección de elementos dentro de una aplicación de la tienda de Windows puede transformar el subproceso en un subproceso administrado (por ejemplo, un API ThreadID de generación de perfiles se creará para ese subproceso).  
  
 Para entender las consecuencias de hacerlo, es importante comprender las diferencias entre las llamadas sincrónicas y asincrónicas de acuerdo con la API de generación de perfiles de CLR. Tenga en cuenta que esto es muy diferente desde el concepto de llamadas asincrónicas en aplicaciones de la tienda de Windows.  Consulte el blog [por qué tenemos CORPROF_E_UNSUPPORTED_CALL_SEQUENCE](https://blogs.msdn.microsoft.com/davbr/2008/12/23/why-we-have-corprof_e_unsupported_call_sequence/) para obtener más información.  
  
 El punto relevante es que las llamadas realizadas en los subprocesos creados por el generador de perfiles siempre se consideran sincrónicas, incluso si las llamadas realizadas desde fuera de una implementación de uno de la DLL generador de perfiles [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) métodos.  Como mínimo, que usa sea el caso.  Ahora que el CLR ha desactivado el subproceso del generador de perfiles en un subproceso administrado debido a la llamada a [ForceGC (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-forcegc-method.md), que subproceso ya no se considera subproceso del generador de perfiles.  Por lo tanto, el CLR aplica una definición más estricta de lo que se consideran como sincrónico para ese subproceso, es decir, que una llamada debe originarse a partir dentro de uno de la DLL generador de perfiles [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) métodos para calificar como sincrónica.  
  
 ¿Qué significa esto en la práctica?  La mayoría [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) métodos solo son seguros para ser llamado de forma sincrónica e inmediatamente producirá un error en caso contrario.  Por tanto, si la DLL del generador de perfiles vuelve a utilizar su [ForceGC (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-forcegc-method.md) subproceso para otras llamadas que suelen realizadas en los subprocesos creados por el generador de perfiles (por ejemplo, para [RequestProfilerDetach](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-requestprofilerdetach-method.md), [RequestReJIT](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrejit-method.md), o [RequestRevert](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrevert-method.md)), va a tener problemas.  Incluso una función con seguridad asincrónica como [DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) tiene reglas especiales cuando se llama desde los subprocesos administrados. (Consulte el blog [el recorrido de pila de generador de perfiles: conceptos básicos y posteriores](https://blogs.msdn.microsoft.com/davbr/2005/10/06/profiler-stack-walking-basics-and-beyond/) para obtener más información.)  
  
 Por lo tanto, se recomienda que cualquier subproceso que crea la DLL del generador de perfiles para llamar a [ForceGC (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-forcegc-method.md) debe utilizarse *sólo* con el fin de activar catálogos globales y, a continuación, responde a las devoluciones de llamada de GC.  No debe llamar a la API de generación de perfiles para realizar otras tareas como la pila de muestreo o separar.  
  
<a name="WeakTable"></a>   
### <a name="conditionalweaktablereferences"></a>ConditionalWeakTableReferences  
 A partir de .NET Framework 4.5, hay una devolución de llamada de GC nueva, [ConditionalWeakTableElementReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md), que proporciona el generador de perfiles se complete más información acerca de *identificadores dependientes*. Estos identificadores de forma eficaz agregar una referencia de un objeto de origen a un objeto de destino con el fin de administración de la duración de GC.  Los identificadores dependientes son nada nuevo y los desarrolladores que programan en código administrado han sido capaces de crear sus propios identificadores dependientes mediante el <xref:System.Runtime.CompilerServices.ConditionalWeakTable%602?displayProperty=nameWithType> clase incluso antes de que Windows 8 y .NET Framework 4.5.  
  
 Sin embargo, las aplicaciones administradas XAML Windows Store ahora hacen un uso intensivo de identificadores dependientes.  En concreto, el CLR usa para ayudar con la administración de ciclos de referencia entre objetos administrados a los objetos administrados y en tiempo de ejecución de Windows.  Esto significa que es más importante ahora que alguna vez para los generadores de perfiles de memoria estar informado de estos identificadores dependientes para que se pueden visualizar junto con el resto de los bordes en el gráfico de montón.  La DLL del generador de perfiles debe usar [RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md), [ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md), y [ConditionalWeakTableElementReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md) juntos para formar una visión completa del gráfico de montón .  
  
<a name="Conclusion"></a>   
## <a name="conclusion"></a>Conclusión  
 Es posible utilizar la API de generación de perfiles de CLR para analizar código administrado que se ejecuta dentro de aplicaciones de la tienda de Windows.  De hecho, puede tomar un generador de perfiles existente que esté desarrollando y realizar algunos cambios específicos para que pueden usar como destino aplicaciones de la tienda de Windows.   La interfaz de usuario del generador de perfiles debe usar las nuevas API para activar la aplicación de tienda Windows en modo de depuración.  Asegúrese de que la DLL del generador de perfiles consume solo las API aplicable para aplicaciones de la tienda de Windows.  El mecanismo de comunicación entre el archivo DLL del generador de perfiles y la interfaz de usuario del generador de perfiles debe escribirse con las restricciones de API de aplicación de tienda Windows en mente y con el reconocimiento de los permisos restringidos en su lugar para aplicaciones de la tienda de Windows.  La DLL del generador de perfiles debe tener en cuenta que el CLR trata los archivos Winmd, y cómo el comportamiento del recolector de elementos no utilizados es diferente con respecto a los subprocesos administrados.  
  
<a name="Resources"></a>   
## <a name="resources"></a>Recursos  
 **Common Language Runtime**  
 -   [Referencia de la API de generación de perfiles de CLR](../../../../docs/framework/unmanaged-api/profiling/index.md)  
  
-   [Referencia de API de metadatos CLR](../../../../docs/framework/unmanaged-api/metadata/index.md)  
  
 **Interacción de CLR con el tiempo de ejecución de Windows**  
 [Compatibilidad de .NET Framework con las aplicaciones de la Tienda Windows y Windows Runtime](../../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)  
  
 **Aplicaciones de la Tienda Windows**  
 -   [Acceso a archivos y permisos (aplicaciones de Windows en tiempo de ejecución](https://msdn.microsoft.com/library/windows/apps/hh967755.aspx)  
  
-   [Obtener una licencia de desarrollador](https://msdn.microsoft.com/library/windows/apps/Hh974578.aspx)  
  
-   [Interfaz IPackageDebugSettings](https://msdn.microsoft.com/library/hh438393\(v=vs.85\).aspx)  
  
## <a name="see-also"></a>Vea también  
 [Generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/index.md)
