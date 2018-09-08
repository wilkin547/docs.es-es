---
title: Los generadores de perfiles CLR y las aplicaciones de Windows Store
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
ms.openlocfilehash: f1747d99fbfbc31fb592aee570d10d574b8480b0
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44129159"
---
# <a name="clr-profilers-and-windows-store-apps"></a>Los generadores de perfiles CLR y las aplicaciones de Windows Store

En este tema se describe lo que debe pensar cuando las herramientas de diagnóstico de escritura que analizan administra el código que se ejecuta dentro de una aplicación de Windows Store.  También proporciona instrucciones para modificar las herramientas de desarrollo existentes para que siguen funcionando cuando se ejecutan en las aplicaciones de Windows Store.  Para entender esta información, es mejor que si está familiarizado con la API de generación de perfiles de en tiempo de ejecución de lenguaje común, ya ha usado esta API en una herramienta de diagnóstico que se ejecuta correctamente en las aplicaciones de escritorio de Windows y, ahora está interesado en la modificación de la herramienta Para ejecutar correctamente en las aplicaciones de Windows Store.  
  
## <a name="introduction"></a>Introducción

 Si ha realizado más allá del párrafo de introducción, a continuación, que está familiarizado con la API de generación de perfiles de CLR.  Ya ha escrito una herramienta de diagnóstico que funciona bien con aplicaciones de escritorio administradas.  Ahora tiene curiosidad qué hacer para que la herramienta funciona con una aplicación de Windows Store administrada.  Quizás ya ha intentado realizar este trabajo y han descubierto que no es una tarea sencilla.  De hecho, hay una serie de cuestiones que podría no ser evidente para todos los desarrolladores de herramientas.  Por ejemplo:  
  
-   Las aplicaciones de Windows Store se ejecutan en un contexto con permisos reducidos gravemente.  
  
-   Los archivos de metadatos de Windows tienen características únicas en comparación con los módulos administrados tradicionales.  
  
-   Windows Store apps tienen la costumbre de suspender a sí mismos cuando interactividad deja de funcionar.  
  
-   Es posible que los mecanismos de comunicación entre procesos dejarán de funcionar por diversos motivos.  
  
 En este tema se enumera las cosas que debe tener en cuenta y cómo tratar con ellos correctamente.  
  
 Si está familiarizado con la API de generación de perfiles de CLR, omitir hasta los recursos al final de este tema para encontrar la mejor información de introducción.  
  
 Proporcionar detalles sobre las API específicas de Windows y cómo debe usarse también está fuera del ámbito de este tema.  Considere la posibilidad de este tema, un punto de partida y consulte MSDN para obtener más información sobre las API de Windows que se hace referencia aquí.  
  
## <a name="architecture-and-terminology"></a>Arquitectura y terminología

 Normalmente, una herramienta de diagnóstico tiene una arquitectura, como se muestra en la siguiente ilustración. Usa el término "generador de perfiles", pero muchas de estas herramientas ir mucho más allá de los típicos en el rendimiento o la generación de perfiles de memoria en áreas como la cobertura de código, simulación de marcos de objetos, el tiempo de viaje depuración, la aplicación de supervisión y así sucesivamente.  Por motivos de simplicidad, continuará en este tema hacer referencia a todas estas herramientas como los generadores de perfiles.  
  
 La siguiente terminología se utiliza a lo largo de este tema:  
  
**Aplicación**

Se trata de la aplicación que está analizando el generador de perfiles.  Normalmente, el desarrollador de esta aplicación está utilizando el generador de perfiles para ayudar a diagnosticar problemas con la aplicación.  Tradicionalmente, esta aplicación sería una aplicación de escritorio de Windows, pero en este tema, vamos a examinar las aplicaciones de Windows Store.  
  
**DLL de Profiler**

Éste es el componente que se carga en el espacio de proceso de la aplicación que se está analizando.  Este componente, también conocido como el generador de perfiles "agente", se implementa el [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)[ICorProfilerCallback (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)(2,3, etc.) e interfaces consume el [ ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)(2,3, etc.) interfaces para recopilar datos acerca de la aplicación analizada y posiblemente modificarán aspectos del comportamiento de la aplicación.  
  
**Interfaz de usuario de Profiler**

Se trata de una aplicación de escritorio que interactúa el usuario del generador de perfiles.  Es responsable de mostrar el estado de la aplicación al usuario y proporcionar al usuario los medios para controlar el comportamiento de la aplicación analizado.  Este componente siempre se ejecuta en su propio espacio de proceso independiente desde el espacio de proceso de la aplicación está generando el perfil.  La interfaz de usuario de Profiler puede actuar también como el "asociación de desencadenador," que es el proceso que llama a la [ICLRProfiling:: AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md) método, para hacer que la aplicación cargar la DLL de Profiler en esos casos donde el archivo DLL del generador de perfiles no analizada cargar al inicio.  
  
> [!IMPORTANT]
> La interfaz de usuario de Profiler debe permanecer en una aplicación de escritorio de Windows, incluso cuando se usa para controlar e informar de una aplicación de Windows Store.  No espere poder empaquetar y distribuir la herramienta de diagnóstico en el Store de Windows.  La herramienta necesita hacer cosas que no se pueden hacer las aplicaciones de Windows Store, y muchas de esas cosas residen dentro de la interfaz de usuario de Profiler.  
  
 En este documento, el código de ejemplo supone que:  
  
- El archivo DLL de Profiler está escrito en C++, porque debe ser una DLL nativa, según los requisitos de la API de generación de perfiles de CLR.  
  
- La interfaz de usuario de Profiler está escrito en C#.  Esto no es necesario, pero dado que no hay ningún requisito en el idioma para el proceso de la IU de Profiler, ¿por qué no elija un idioma que es sencillo y conciso?  
  
### <a name="windows-rt-devices"></a>Dispositivos Windows RT

Dispositivos Windows RT bastante están bloqueados.  Los generadores de perfiles de otros fabricantes simplemente no se puede cargadas en estos dispositivos.  Este documento se centra en los equipos Windows 8.  
  
## <a name="consuming-windows-runtime-apis"></a>Consumo de API de Windows en tiempo de ejecución

 Su aplicación de escritorio de la interfaz de usuario de Profiler en una serie de escenarios que se describen en las secciones siguientes, debe usar algunas nuevas APIs de Runtime de Windows.  Puede consultar la documentación para entender las API de Windows en tiempo de ejecución se pueden usar desde aplicaciones de escritorio y, si su comportamiento es diferente cuando llama desde aplicaciones de escritorio y Windows Store apps.  
  
 Si la interfaz de usuario de Profiler está escrito en código administrado, habrá algunos pasos que deberá hacer para que el consumo de esos Windows en tiempo de ejecución APIs fácil.  Consulte la [administrados de aplicaciones de escritorio y Windows Runtime](https://go.microsoft.com/fwlink/?LinkID=271858) artículo para obtener más información.  
  
## <a name="loading-the-profiler-dll"></a>Al cargar la DLL de Profiler

 En esta sección se describe cómo la interfaz de usuario de Profiler hace que la aplicación de Windows Store para cargar el archivo DLL de Profiler.  El código tratado en esta sección pertenece a la aplicación de escritorio de la interfaz de usuario de Profiler y, por lo tanto, implica el uso de las API de Windows que son seguros para las aplicaciones de escritorio pero no necesariamente seguros para las aplicaciones de Windows Store.  
  
 La interfaz de usuario de Profiler para hacer que el archivo DLL de Profiler para cargarse en el espacio de proceso de la aplicación de dos maneras:  
  
-   Al iniciarse la aplicación, que se controla mediante las variables de entorno.  
  
-   Mediante la conexión a la aplicación después de inicio mediante una llamada a la [ICLRProfiling:: AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md) método.  
  
 Uno de los primeros obstáculos obtendrá adjuntar-carga de la DLL de Profiler para trabajar correctamente con aplicaciones de Windows Store y carga de inicio.  Ambos formatos de carga tienen algunas consideraciones especiales en común, por eso comenzaremos con ellos.  
  
### <a name="common-considerations-for-startup-and-attach-loads"></a>Consideraciones comunes para el inicio y adjuntar cargas

 **Firma el archivo DLL de Profiler**  
 Cuando Windows intenta cargar el archivo DLL de Profiler, comprueba que el archivo DLL de Profiler está debidamente firmado.  Si no es así, se produce un error en la carga de forma predeterminada. Existen dos modos para hacer esto:  
  
-   Asegúrese de que el archivo DLL de Profiler está firmado.  
  
-   Indicar al usuario que debe instalar una licencia de desarrollador en su equipo de Windows 8 antes de usar la herramienta.  Esto puede hacerse automáticamente desde Visual Studio o manualmente desde un símbolo del sistema.  Para obtener más información, consulte [obtener una licencia de desarrollador](https://msdn.microsoft.com/library/windows/apps/Hh974578.aspx).  
  
 **Permisos de sistema de archivos**  
 La aplicación de Windows Store debe tener permiso para cargar y ejecutar el archivo DLL de Profiler desde la ubicación en el sistema de archivos en el que reside.  De forma predeterminada, la aplicación de Windows Store no tiene ese permiso en la mayoría de los directorios y cualquier intento con error al cargar la DLL de Profiler generará una entrada en el registro de eventos de aplicación de Windows es algo parecido a esto:  
  
```Output  
NET Runtime version 4.0.30319.17929 - Loading profiler failed during CoCreateInstance.  Profiler CLSID: '{xxxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx}'.  HRESULT: 0x80070005.  Process ID (decimal): 4688.  Message ID: [0x2504].  
```  
  
 Por lo general, solo se permiten aplicaciones de Windows Store para tener acceso a un conjunto limitado de ubicaciones en el disco.  Cada aplicación de Windows Store puede tener acceso a sus propias carpetas de datos de aplicación, así como algunas otras áreas del sistema de archivos para el que todas las aplicaciones de Windows Store se les concede acceso.  Es mejor instalar la DLL de Profiler y sus dependencias en algún lugar en los archivos de programa o archivos de programa (x86), porque todas las aplicaciones de Windows Store leído y hay permisos de ejecución de forma predeterminada.  
  
### <a name="startup-load"></a>Carga de inicio

 Normalmente, en una aplicación de escritorio, la interfaz de usuario de Profiler solicita una carga de inicio del archivo DLL Profiler mediante la inicialización de un bloque de entorno que contiene las variables de entorno necesarias de API de generación de perfiles de CLR (es decir, `COR_PROFILER`, `COR_ENABLE_PROFILING`, y `COR_PROFILER_PATH`), y a continuación, crea un proceso nuevo con ese bloque de entorno.  Lo mismo sucede para las aplicaciones de Windows Store, pero los mecanismos son diferentes.  
  
 **No se ejecutan con privilegios elevados**  
 Si el proceso un intenta generar Windows Store app B de proceso, un proceso debe ejecutarse en integridad medio nivel, no a nivel de integridad alto (que es, no elevado).  Esto significa que debe ejecutar la interfaz de usuario de Profiler en el nivel de integridad media, o lo debe generar otro proceso escritorio en el nivel de integridad medio que se encargue de iniciar la aplicación de Windows Store.  
  
 **Elección de una aplicación de Windows Store al perfil**  
 En primer lugar, querrá pedirle a su usuario de profiler qué aplicación de Windows Store para iniciar.  Para aplicaciones de escritorio, quizás podría mostrar un cuadro de diálogo de exploración de archivo y el usuario podría buscar y seleccionar un archivo .exe.  Pero Windows Store apps son diferentes y, mediante un cuadro de diálogo de exploración no tiene sentido.  En su lugar, es mejor mostrar al usuario una lista de aplicaciones de Windows Store instalado para que seleccione en el usuario.  
  
 Puede usar el [PackageManager clase](https://msdn.microsoft.com/library/windows/apps/windows.management.deployment.packagemanager.aspx) para generar esta lista.  `PackageManager` es una clase en tiempo de ejecución de Windows que está disponible para las aplicaciones de escritorio y de hecho es *sólo* disponibles para las aplicaciones de escritorio.  
  
 El siguiente ejemplo de código desde una interfaz de usuario de Profiler hipotético escrito como una aplicación de escritorio en C# yses el `PackageManager` para generar una lista de aplicaciones de Windows:  
  
```csharp  
string currentUserSID = WindowsIdentity.GetCurrent().User.ToString();  
IAppxFactory appxFactory = (IAppxFactory) new AppxFactory();  
PackageManager packageManager = new PackageManager();  
IEnumerable<Package> packages = packageManager.FindPackagesForUser(currentUserSID);  
```  
  
 **Especifica el bloque de entorno personalizado**  
 Una nueva interfaz de COM, [IPackageDebugSettings](https://msdn.microsoft.com/library/hh438393\(v=vs.85\).aspx), le permite personalizar el comportamiento de ejecución de una aplicación de Windows Store para facilitar algunas formas de diagnóstico.  Uno de sus métodos, [EnableDebugging](https://msdn.microsoft.com/library/hh438395\(v=vs.85\).aspx), le permite pasar un bloque de entorno a la aplicación de Windows Store cuando se inicia, junto con otros efectos útiles, por ejemplo, deshabilitar la suspensión del proceso automático.  El bloque de entorno es importante ya que es donde debe especificar las variables de entorno (`COR_PROFILER`, `COR_ENABLE_PROFILING`, y `COR_PROFILER_PATH)`) usa CLR para cargar el archivo DLL de Profiler.  
  
 Tenga en cuenta el siguiente fragmento de código:  
  
```csharp  
IPackageDebugSettings pkgDebugSettings = new PackageDebugSettings();  
pkgDebugSettings.EnableDebugging(packgeFullName, debuggerCommandLine,   
                                                                 (IntPtr)fixedEnvironmentPzz);  
```  
  
 Hay un par de elementos, deberá realizar correctamente:  
  
-   `packageFullName` se puede determinar al recorrer en iteración los paquetes y captamos `package.Id.FullName`.  
  
-   `debuggerCommandLine` es un poco más interesante.  Para pasar el bloque de entorno personalizadas a la aplicación de Windows Store, deberá escribir a su propio depurador ficticio simplista.  Genera de Windows, la aplicación de Windows Store suspendido y, a continuación, asocia al depurador, inicie al depurador con una línea de comandos, como en este ejemplo:  
  
    ```Output  
    MyDummyDebugger.exe -p 1336 -tid 1424  
    ```  
  
     donde `-p 1336` significa que la aplicación de Windows Store tiene 1336 de Id. de proceso, y `-tid 1424` significa 1424 de Id. de subproceso es el subproceso que está suspendido.  El depurador ficticio podría analizar ThreadID desde la línea de comandos, reanudar ese subproceso y, a continuación, salir.  
  
     Le presentamos algunos ejemplos de código de C++ para hacer esto (no olvide agregar comprobación de errores!):  
  
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
  
     Deberá implementar este depurador ficticio como parte de la instalación de la herramienta de diagnóstico y, a continuación, especifique la ruta de acceso a este depurador en el `debuggerCommandLine` parámetro.  
  
 **Iniciar la aplicación de Windows Store**  
 Ha llegado el momento para iniciar la aplicación de Windows Store. Si ya ya ha intentado realizar usted mismo, es posible que haya observado que [CreateProcess](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-createprocessa) es no, cómo crear un proceso de aplicación de Windows Store.  En su lugar, deberá usar el [IApplicationActivationManager::ActivateApplication](/windows/desktop/api/shobjidl_core/nf-shobjidl_core-iapplicationactivationmanager-activateapplication) método.  Para ello, deberá obtener el identificador de modelo de aplicación de usuario de la aplicación de Windows Store que se inicia.  Por tanto, deberá hacer un poco indagar en el manifiesto.  
  
 Al recorrer en iteración los paquetes (vea "Elegir un Windows Store App para generar perfiles" en el [carga inicio](#Startup) sección anterior), deseará tomar el conjunto de aplicaciones incluidas en el manifiesto del paquete actual:  
  
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
  
 Sí, un paquete puede tener varias aplicaciones, y cada aplicación tiene su propio identificador de modelo de aplicación de usuario.  Por lo que querrá preguntar al usuario qué aplicación al perfil y obtener el identificador de modelo de aplicación de usuario desde esa aplicación en particular:  
  
```csharp  
while (appsEnum.GetHasCurrent() != 0)  
{  
    IAppxManifestApplication app = appsEnum.GetCurrent();  
    string appUserModelId = app.GetAppUserModelId();  
    //...
}
```  
  
 Por último, ahora tiene lo que necesita iniciar la aplicación de Windows Store:  
  
```csharp  
IApplicationActivationManager appActivationMgr = new ApplicationActivationManager();  
appActivationMgr.ActivateApplication(appUserModelId, appArgs, ACTIVATEOPTIONS.AO_NONE, out pid);  
```  
  
 **No olvide llamar a DisableDebugging**  
 Cuando llama a [IPackageDebugSettings::EnableDebugging](https://msdn.microsoft.com/library/hh438395\(v=VS.85\).aspx), realizan una promesa que se limpiarían ensuciado mediante una llamada a la [IPackageDebugSettings::DisableDebugging](https://msdn.microsoft.com/library/hh438394\(v=vs.85\).aspx) método, por lo que debe asegurarse de realizar que cuando la sesión de generación de perfiles es a través.  
  
### <a name="attach-load"></a>Adjuntar carga

 Cuando la interfaz de usuario de Profiler desea asociar su DLL Profiler a una aplicación que ya ha empezado a ejecutarse, utiliza [ICLRProfiling:: AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md).  Lo mismo sucede con las aplicaciones de Windows Store.  Pero además de las consideraciones comunes enumeradas anteriormente, asegúrese de que el objeto que no se suspende la aplicación de Windows Store de destino.  
  
 **EnableDebugging**  
 Al igual que con la carga de inicio, llame a la [IPackageDebugSettings::EnableDebugging](https://msdn.microsoft.com/library/hh438395\(v=VS.85\).aspx) método.  Ya no lo necesita para pasar un bloque de entorno, pero necesita una de las otras características: deshabilitar la suspensión del proceso automático.  En caso contrario, cuando se llama la interfaz de usuario de Profiler [AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md), es posible que se suspenda la aplicación de Windows Store de destino.  De hecho, esto es probable que si el usuario está interactuando con la interfaz de usuario de Profiler y la aplicación de Windows Store no está activa en cualquiera de las pantallas del usuario.  Y si la Windows Store app está suspendido, no podrá responder a cualquier señal de que el CLR se envía a ella para adjuntar el archivo DLL de Profiler.  
  
 Por lo que desea hacer algo como esto:  
  
```csharp  
IPackageDebugSettings pkgDebugSettings = new PackageDebugSettings();  
pkgDebugSettings.EnableDebugging(packgeFullName, null /* debuggerCommandLine */,   
                                                                 IntPtr.Zero /* environment */);  
```  
  
 Se trata de la misma llamada haría que el caso de carga de inicio, excepto que no especifica una línea de comandos del depurador o un bloque de entorno.  
  
 **DisableDebugging**  
 Como siempre, no se olvide de llamar a [IPackageDebugSettings::DisableDebugging](https://msdn.microsoft.com/library/hh438394\(v=vs.85\).aspx) cuando se completa la sesión de generación de perfiles.  
  
<a name="Running"></a>   
## <a name="running-inside-the-windows-store-app"></a>Que se ejecuta dentro de la aplicación de Windows Store  
 Por lo que la aplicación de Windows Store, por último, ha cargado la DLL de Profiler.  Ahora el archivo DLL de Profiler debe ser impartido cómo se juega según las reglas diferentes requeridas por las aplicaciones de Windows Store, incluidas las API que están permitidas y cómo ejecutar con permisos reducción.  
  
<a name="APIs"></a>   
### <a name="stick-to-the-windows-store-app-apis"></a>Ceñirse a las API de Windows Store app  
 Al explorar la API de Windows, observará que se documenta todas las API como aplicable a las aplicaciones de escritorio, aplicaciones de Windows Store o ambos.  Por ejemplo, el **requisitos** sección de la documentación para el [InitializeCriticalSectionAndSpinCount](/windows/desktop/api/synchapi/nf-synchapi-initializecriticalsectionandspincount) función indica que la función se aplica a solo las aplicaciones de escritorio. En cambio, el [InitializeCriticalSectionEx](/windows/desktop/api/synchapi/nf-synchapi-initializecriticalsectionex) función está disponible para aplicaciones de escritorio y aplicaciones de Windows Store.  
  
 Al desarrollar el archivo DLL de Profiler, trátelo como si fuera una aplicación de Windows Store y solo usan las API que se documentan como disponible para las aplicaciones de Windows Store.  Análisis de las dependencias (por ejemplo, puede ejecutar `link /dump /imports` contra el archivo DLL de Profiler para auditar) y, a continuación, busque los documentos para ver cuál de las dependencias son Aceptar y cuáles no.  En la mayoría de los casos, se pueden corregir sus infracciones simplemente reemplazarlos con un formato más reciente de la API que está documentado como seguras para (por ejemplo, reemplace [InitializeCriticalSectionAndSpinCount](/windows/desktop/api/synchapi/nf-synchapi-initializecriticalsectionandspincount) con [ InitializeCriticalSectionEx](/windows/desktop/api/synchapi/nf-synchapi-initializecriticalsectionex)).  
  
 Es posible que observe que algunas API que se aplica a las aplicaciones de escritorio solo llama a la DLL de Profiler y todavía parece funcionar incluso cuando se carga el archivo DLL de Profiler dentro de una aplicación de Windows Store.  Tenga en cuenta que es muy arriesgado utilizar cualquier API no documentada para su uso con aplicaciones de Windows Store en el archivo DLL de Profiler cuando se carga en un proceso de aplicación de Windows Store:  
  
-   Estas API no se garantiza que funcionen cuando se llama en el contexto único que se ejecutan las aplicaciones de Windows Store en.  
  
-   Estas API no podrían funcionar de manera coherente cuando se llama desde dentro de distintos procesos de aplicación de Windows Store.  
  
-   Estas API pueden parecer que funcionan correctamente desde aplicaciones de Windows Store en la versión actual de Windows, pero pueden interrumpir o deshabilitarse en las versiones futuras de Windows.  
  
 El mejor consejo es corregir todas las infracciones de sus y evitar el riesgo.  
  
 Es posible que sea absolutamente no puede prescindir de una API concreta y no se puede encontrar un sustituto adecuado para aplicaciones de Windows Store.  En tal caso, como mínimo:  
  
-   Realice pruebas y probar el daylights vivos fuera de su uso de dicha API.  
  
-   Comprender que la API puede, de repente, interrumpir o desaparecer si se llama desde dentro de Windows Store apps en versiones futuras de Windows.  Esto no se considera un problema de compatibilidad de Microsoft y que admiten el uso del mismo no será una prioridad.  
  
### <a name="reduced-permissions"></a>Permisos restringidos

 Está fuera del ámbito de este tema para enumerar todas las formas en que los permisos de aplicación de Windows Store difieren de las aplicaciones de escritorio.  Pero sin duda el comportamiento será diferente cada vez que el archivo DLL de Profiler (cuando se cargan en una aplicación de Windows Store en comparación con una aplicación de escritorio) intenta tener acceso a todos los recursos.  El sistema de archivos es el ejemplo más común.  Existen pero algunos se coloca en el disco que se puede tener acceso a una aplicación determinada de Windows Store (consulte [acceso y permisos de archivos (aplicaciones de Windows Runtime](https://msdn.microsoft.com/library/windows/apps/hh967755.aspx)), y será el archivo DLL de Profiler en las mismas restricciones.  Probar exhaustivamente el código.  
  
### <a name="inter-process-communication"></a>Comunicación entre procesos

 Como se muestra en el diagrama al principio de este documento, el archivo DLL de Profiler (cargado en el espacio de procesos de Windows Store app) probablemente tendrá que comunicarse con la IU de Profiler (que se ejecuta en un espacio de proceso de aplicación de escritorio independiente) a través de su propio proceso personalizado entre canal de comunicación entre procesos (IPC).  La interfaz de usuario de Profiler envía señales a la DLL de Profiler para modificar su comportamiento y el archivo DLL de Profiler envía datos desde la aplicación de Windows Store analizada a la interfaz de usuario de Profiler para posteriores al procesamiento y mostrar al usuario del generador de perfiles.  
  
 La mayoría de los generadores de perfiles necesitan trabajar de este modo, pero las opciones de mecanismos de IPC son más limitadas, cuando se carga el archivo DLL de Profiler en una aplicación de Windows Store.  Por ejemplo, canalizaciones con nombre no forman parte de la aplicación de Windows Store SDK, por lo que no puede usarlos.  
  
 Pero por supuesto, los archivos están todavía en, aunque de forma más limitada.  Los eventos también están disponibles.  
  
 **Comunicarse a través de archivos**  
 La mayoría de los datos probablemente pasará entre la DLL de Profiler y la interfaz de usuario de Profiler a través de archivos.  La clave consiste en seleccionar una ubicación del archivo que han leído la DLL de Profiler (en el contexto de una aplicación de Windows Store) y la interfaz de usuario de Profiler y el acceso de escritura a.  Por ejemplo, la ruta de acceso de carpeta temporal es una ubicación que pueden tener acceso la DLL de Profiler y la interfaz de usuario de Profiler, pero no puede tener acceso a ningún otro paquete de aplicación de Windows Store (Blindaje, por tanto, cualquier información que se inicie desde otros paquetes de aplicación de Windows Store).  
  
 Su interfaz de usuario de Profiler y el archivo DLL de Profiler pueden determinar esta ruta de acceso de forma independiente.  La interfaz de usuario de Profiler, cuando recorre en iteración todos los paquetes instalados para el usuario actual (vea el código de ejemplo anterior), se obtiene acceso a la `PackageId` (clase), desde el que se puede derivar la ruta de acceso de carpeta temporal con código similar a este fragmento de código.  (Como siempre, comprobación de errores se omite para mayor brevedad).  
  
```csharp  
// C# code for the Profiler UI.  
ApplicationData appData =  
    ApplicationDataManager.CreateForPackageFamily(  
        packageId.FamilyName);  
  
tempDir = appData.TemporaryFolder.Path;  
```  
  
 Mientras tanto, el archivo DLL de Profiler puede hacer básicamente lo mismo, aunque es posible más llegar fácilmente a la [ApplicationData](https://msdn.microsoft.com/library/windows/apps/windows.storage.applicationdata.aspx) clase utilizando el [ApplicationData.Current](https://msdn.microsoft.com/library/windows/apps/windows.storage.applicationdata.current.aspx) propiedad.  
  
 **Comunicarse a través de eventos**  
 Si desea que la semántica de señalización simple entre la interfaz de usuario de Profiler y el archivo DLL de Profiler, puede usar los eventos dentro de aplicaciones de Windows Store, así como las aplicaciones de escritorio.  
  
 Desde el archivo DLL de Profiler, podemos llamar simplemente la [CreateEventEx](/windows/desktop/api/synchapi/nf-synchapi-createeventexa) función para crear un evento con nombre con cualquier nombre que desee.  Por ejemplo:  
  
```cpp  
// Profiler DLL in Windows Store app (C++).  
CreateEventEx(   
    NULL,  // Not inherited  
    "MyNamedEvent"  
    CREATE_EVENT_MANUAL_RESET, /* explicit ResetEvent() required; leave initial state unsignaled */  
    EVENT_ALL_ACCESS);  
```  
  
 La interfaz de usuario de Profiler, a continuación, debe buscar ese evento con nombre en el espacio de nombres de la aplicación de Windows Store.  Por ejemplo, podría llamar la interfaz de usuario de Profiler [CreateEventEx](/windows/desktop/api/synchapi/nf-synchapi-createeventexa), especificando el nombre del evento como  
  
 `AppContainerNamedObjects\<acSid>\MyNamedEvent`  
  
 `<acSid>` es el SID de la aplicación de Windows Store AppContainer.  Una sección anterior de este tema se ha explicado cómo recorrer en iteración los paquetes instalados para el usuario actual.  A partir de ese código de ejemplo, puede obtener el identificador de paquete.  Y desde el identificador de paquete, se puede obtener el `<acSid>` con código similar al siguiente:  
  
```csharp  
IntPtr acPSID;  
DeriveAppContainerSidFromAppContainerName(packageId.FamilyName, out acPSID);  
  
string acSid;  
ConvertSidToStringSid(acPSID, out acSid);  
  
string acDir;  
GetAppContainerFolderPath(acSid, out acDir);  
```  
  
### <a name="no-shutdown-notifications"></a>No hay notificaciones de apagado

 Cuando se ejecuta dentro de una aplicación de Windows Store, el archivo DLL de Profiler no deben depender cualquiera [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-shutdown-method.md) o incluso [DllMain](/windows/desktop/Dlls/dllmain) (con `DLL_PROCESS_DETACH`) que se llama para notificar a la DLL de Profiler que se está cerrando la aplicación de Windows Store.  De hecho, debe esperar nunca se llamará.  Históricamente, muchos archivos DLL de Profiler han utilizado esas notificaciones como los lugares adecuados para vaciar las memorias caché de disco, cerrar archivos, enviar notificaciones a la interfaz de usuario de Profiler, etcetera.  Pero ahora el archivo DLL de Profiler debe organizarse de forma ligeramente diferente.  
  
 El archivo DLL de Profiler debe ser la información de registro conforme avanza.  Por motivos de rendimiento, puede procesar por lotes de información en la memoria y en el disco a medida que crece el lote de tamaño más allá de un umbral de vaciado.  Pero suponga que se puede perder ninguna información aún no se han vaciado en disco.  Esto significa que desea elegir con cuidado el umbral y que la interfaz de usuario de Profiler debe ser protegida para tratar con información incompleta escrita por el archivo DLL de Profiler.  
  
## <a name="windows-runtime-metadata-files"></a>Archivos de metadatos en tiempo de ejecución de Windows

 Está fuera del ámbito de este documento entraré en detalles sobre qué metadatos en tiempo de ejecución de Windows (WinMD) son archivos.    En esta sección se limita a cómo reacciona ante la API de generación de perfiles de CLR cuando se cargan los archivos de WinMD por la aplicación de Windows Store que está analizando el archivo DLL de Profiler.  
  
### <a name="managed-and-non-managed-winmds"></a>Archivos de Winmd administrado y no administrado

 Si un desarrollador usa Visual Studio para crear un nuevo proyecto de componente de Windows en tiempo de ejecución, una compilación del proyecto genera un archivo WinMD que describe los metadatos (las descripciones de tipo de clases, interfaces, etc.) creados por el desarrollador.  Si este proyecto es un lenguaje administrado escrito en C# o VB, ese mismo archivo de WinMD también contiene la implementación de esos tipos (es decir, que contiene todo el IL compilado a partir de código de fuente del desarrollador).  Estos archivos se conocen como archivos de WinMD administrados.  Son interesantes, ya que contienen los metadatos de Windows Runtime y la implementación subyacente.  
  
 En cambio, si un desarrollador crea un proyecto de componente de Windows en tiempo de ejecución de C++, una compilación del proyecto genera un archivo WinMD que solo contiene metadatos y la implementación se compila en un archivo DLL nativa independiente.  De forma similar, los archivos de WinMD que se incluyen en el SDK de Windows contienen solo metadatos, con la implementación que se compilan en archivos DLL nativos independientes que se incluyen como parte de Windows.  
  
 La siguiente información se aplica a ambos archivos de Winmd administrados, que contienen metadatos y la implementación, y para archivos Winmd no administrado, que contienen solo metadatos.  
  
### <a name="winmd-files-look-like-clr-modules"></a>Archivos de WinMD aspecto módulos CLR

 En cuanto a CLR, todos los archivos de WinMD son módulos.  Por consiguiente, la API de generación de perfiles de CLR indica la DLL de Profiler al cargarán los archivos de WinMD y cuáles son sus los ModuleIDs, en la misma manera que otros módulos administrados.  
  
 El archivo DLL de Profiler puede distinguir los archivos de WinMD desde otros módulos mediante una llamada a la [ICorProfilerInfo3:: Getmoduleinfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getmoduleinfo2-method.md) método e inspeccionar el `pdwModuleFlags` para el parámetro de salida el [COR_PRF_MODULE_WINDOWS_ En tiempo de ejecución](../../../../docs/framework/unmanaged-api/profiling/cor-prf-module-flags-enumeration.md) marca.  (Se establece solo si el identificador de módulo representa un archivo WinMD).  
  
### <a name="reading-metadata-from-winmds"></a>Leer metadatos de Winmd

 Archivos de WinMD, como módulos normales, contienen metadatos que se pueden leer mediante el [Metadata APIs](../../../../docs/framework/unmanaged-api/metadata/index.md).  Sin embargo, CLR asigna tipos en tiempo de ejecución de Windows a tipos de .NET Framework cuando lee que archivos de WinMD para que los desarrolladores que programar en código administrado y consumen el archivo WinMD pueden tener una experiencia de programación más natural.  Para ver algunos ejemplos de estas asignaciones, vea [soporte técnico para Windows Store aplicaciones de .NET Framework y Windows Runtime](../../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md).  
  
 ¿Por lo que la vista que el generador de perfiles obtendrá cuando se usan las API de metadatos: la vista en tiempo de ejecución de Windows sin formato o la vista de .NET Framework asignada?  La respuesta: es para usted.  
  
 Cuando se llama a la [GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) método en un archivo WinMD para obtener una interfaz de metadatos, como [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md), puede elegir establecer [ofNoTransform](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md)en el `dwOpenFlags` parámetro para desactivar esta asignación.  En caso contrario, de forma predeterminada, se habilitará la asignación.  Normalmente, un generador de perfiles mantendrá la asignación está habilitada, para que las cadenas que se obtiene de la DLL de Profiler de los metadatos de WinMD (por ejemplo, los nombres de tipos) tendrá un aspecto familiar y natural para el usuario del generador de perfiles.  
  
### <a name="modifying-metadata-from-winmds"></a>Modificar los metadatos de Winmd

 No se admite la modificación de los metadatos de Winmd.  Si se llama a la [GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) método para un archivo WinMD archivo y especifique [marca ofWrite](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) en el `dwOpenFlags` parámetro o solicitar una interfaz de metadatos pueden escribir como [ IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md), [GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) se producirá un error.  Esto es de especial importancia para la reescritura IL los generadores de perfiles, que es necesario modificar los metadatos para admitir su instrumentación (por ejemplo, para agregar nuevos métodos o AssemblyRefs).  Por lo que debe comprobar para [COR_PRF_MODULE_WINDOWS_RUNTIME](../../../../docs/framework/unmanaged-api/profiling/cor-prf-module-flags-enumeration.md) primero (como se describe en la sección anterior) y no usándolas pide interfaces de metadatos puede escribir en estos módulos.  
  
### <a name="resolving-assembly-references-with-winmds"></a>Resolver las referencias de ensamblado con archivos Winmd

 Muchos de los generadores de perfiles necesitan resolver las referencias de metadatos manualmente para ayudar con la inspección del tipo o de instrumentación.  Estos generadores de perfiles deben tener en cuenta cómo el CLR resuelve las referencias de ensamblado que apuntan a archivos de Winmd, porque esas referencias se resuelven de manera completamente diferente que las referencias de ensamblado estándar.  
  
## <a name="memory-profilers"></a>Generadores de perfiles de memoria

 El recolector de elementos no utilizados y el montón administrado no son fundamentalmente diferentes en una aplicación de Windows Store y una aplicación de escritorio.  Sin embargo, hay algunas diferencias sutiles que deben tener en cuenta los autores del generador de perfiles.  
  
### <a name="forcegc-creates-a-managed-thread"></a>ForceGC crea un subproceso administrado

 Cuando se realiza la generación de perfiles de memoria, el archivo DLL de Profiler normalmente crea un subproceso independiente del que se va a llamar a la [ForceGC (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-forcegc-method.md) método.  Esto no es nada nuevo.  Pero lo que podría ser sorprendente es que el acto de realizar una recolección de elementos dentro de una aplicación de Windows Store puede transformar el subproceso en un subproceso administrado (por ejemplo, una API de generación de perfiles, ThreadID se crearán para ese subproceso).  
  
 Para entender las consecuencias de hacerlo, es importante comprender las diferencias entre las llamadas sincrónicas y asincrónicas, como se define en la API de generación de perfiles de CLR. Tenga en cuenta que esto es muy diferente desde el concepto de las llamadas asincrónicas en las aplicaciones de Windows Store.  Consulte el blog [porqué tenemos CORPROF_E_UNSUPPORTED_CALL_SEQUENCE](https://blogs.msdn.microsoft.com/davbr/2008/12/23/why-we-have-corprof_e_unsupported_call_sequence/) para obtener más información.  
  
 El punto relevante es que las llamadas realizadas en los subprocesos creados por el generador de perfiles siempre se consideran sincrónicas, incluso si esas llamadas se realizan desde fuera de una implementación de uno de los DLL de Profiler [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) métodos.  Al menos, que solía ser el caso.  Ahora que el CLR ha desactivado el subproceso del generador de perfiles en un subproceso administrado debido a la llamada a [ForceGC (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-forcegc-method.md), que subprocesos dejan de subproceso del generador de perfiles.  Por lo tanto, el CLR aplica una definición más estricta de ¿qué se entiende como sincrónico para ese subproceso, es decir, que una llamada debe originarse a partir dentro de uno de los DLL de Profiler [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) métodos para calificar como sincrónica.  
  
 ¿Qué significa esto en la práctica?  La mayoría [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) métodos son sólo seguros para llamarse de forma sincrónica e inmediatamente producirá un error en caso contrario.  Por tanto, si el archivo DLL de Profiler reutiliza la [ForceGC (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-forcegc-method.md) subproceso para otras llamadas realizadas normalmente en los subprocesos creados por el generador de perfiles (por ejemplo, para [RequestProfilerDetach](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-requestprofilerdetach-method.md), [RequestReJIT](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrejit-method.md), o [RequestRevert](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrevert-method.md)), va a tener problemas.  Incluso una función asincrónica safe como [DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) tiene reglas especiales cuando se llama desde los subprocesos administrados. (Consulte el blog [recorridos de pila de Profiler: conceptos básicos y mucho más](https://blogs.msdn.microsoft.com/davbr/2005/10/06/profiler-stack-walking-basics-and-beyond/) para obtener más información.)  
  
 Por lo tanto, se recomienda que cualquier subproceso que crea el archivo DLL de Profiler para llamar a [ForceGC (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-forcegc-method.md) debe usarse *sólo* con el fin de desencadenar GC y, a continuación, responder a las devoluciones de llamada de GC.  No debe llamar a la API de generación de perfiles para realizar otras tareas como la pila de muestreo o desasociar.  
  
### <a name="conditionalweaktablereferences"></a>ConditionalWeakTableReferences

 A partir de .NET Framework 4.5, hay una devolución de llamada de GC nueva, [ConditionalWeakTableElementReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md), que proporciona el generador de perfiles complete más información acerca de *identificadores dependientes*. Estos identificadores eficazmente agrega una referencia desde un objeto de origen a un objeto de destino con el fin de administración de la duración de GC.  Identificadores dependientes son nada nuevo, y los desarrolladores que programan en código administrado han sido capaces de crear sus propios identificadores dependientes mediante el <xref:System.Runtime.CompilerServices.ConditionalWeakTable%602?displayProperty=nameWithType> clase incluso antes de que Windows 8 y .NET Framework 4.5.  
  
 Sin embargo, las aplicaciones administradas de XAML Windows Store ahora hacen un uso intensivo de identificadores dependientes.  En concreto, el CLR usa para ayudar con la administración de ciclos de referencia entre los objetos administrados y no administrados en tiempo de ejecución de Windows.  Esto significa que es más importante ya que nunca los procesos de los generadores de perfiles de memoria para mantenerse informado de estos identificadores dependientes para que se pueden visualizar junto con el resto de los bordes del gráfico de montón.  Debe usar el archivo DLL de Profiler [RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md), [ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md), y [ConditionalWeakTableElementReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md) juntos para formar una visión completa del gráfico de montón .  
  
## <a name="conclusion"></a>Conclusión

 Es posible utilizar la API de generación de perfiles de CLR para analizar código administrado que se ejecuta dentro de las aplicaciones de Windows Store.  De hecho, puede tomar un generador de perfiles existente que se va a desarrollar y realizar algunos cambios específicos para que pueden tener como destino aplicaciones de Windows Store.   La interfaz de usuario de Profiler debería usar las nuevas API para activar la aplicación de Windows Store en modo de depuración.  Asegúrese de que el archivo DLL de Profiler consume solo esas API aplicable para las aplicaciones de Windows Store.  El mecanismo de comunicación entre la DLL de Profiler y la interfaz de usuario de Profiler debe escribirse con las restricciones de API de Windows Store app en mente y con el conocimiento de los permisos restringidos en su lugar para las aplicaciones de Windows Store.  Debe tener en cuenta que el CLR trata los archivos de Winmd, el archivo DLL de Profiler y cómo el comportamiento del recolector de elementos no utilizados es diferente con respecto a los subprocesos administrados.  
  
## <a name="resources"></a>Recursos

 **Common Language Runtime**  
 -   [Referencia de API de generación de perfiles de CLR](../../../../docs/framework/unmanaged-api/profiling/index.md)  
  
-   [Referencia de API de metadatos CLR](../../../../docs/framework/unmanaged-api/metadata/index.md)  
  
 **Interacción de CLR con el tiempo de ejecución de Windows**  
 [Compatibilidad de .NET Framework con las aplicaciones de la Tienda Windows y Windows Runtime](../../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)  
  
 **Aplicaciones de la Tienda Windows**  
 -   [Acceso a archivos y permisos (aplicaciones de Windows Runtime](https://msdn.microsoft.com/library/windows/apps/hh967755.aspx)  
  
-   [Obtener una licencia de desarrollador](https://msdn.microsoft.com/library/windows/apps/Hh974578.aspx)  
  
-   [Interfaz IPackageDebugSettings](https://msdn.microsoft.com/library/hh438393\(v=vs.85\).aspx)  
  
## <a name="see-also"></a>Vea también

[Generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/index.md)  
