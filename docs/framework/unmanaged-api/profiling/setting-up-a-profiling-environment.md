---
title: Configurar un entorno de generación de perfiles
ms.date: 03/30/2017
helpviewer_keywords:
- environment variables, profiling API
- profiling API [.NET Framework], setting up environment
- COR_PROFILER environment variable
- Windows Service applications, profiling
- profiling API [.NET Framework], Windows Service applications
- COR_ENABLE_PROFILING environment variable
- profiling API [.NET Framework], enabling
ms.assetid: fefca07f-7555-4e77-be86-3c542e928312
ms.openlocfilehash: 32ebb868ea64a24fba80133b1a0eb539f51cb411
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176973"
---
# <a name="setting-up-a-profiling-environment"></a>Configurar un entorno de generación de perfiles
> [!NOTE]
> Se han producido cambios sustanciales en la generación de perfiles en .NET Framework 4.  
  
 Cuando se inicia un proceso administrado (aplicación o servicio), se carga el Common Language Runtime (CLR). Cuando se inicializa el CLR, evalúa las siguientes dos variables de entorno para decidir si el proceso debería conectar con un generador de perfiles:  
  
- COR_ENABLE_PROFILING: CLR solamente se conecta a un generador de perfiles si esta variable de entorno existe y está establecida en 1.  
  
- COR_PROFILER: si la comprobación de COR_ENABLE_PROFILING es correcta, CLR conecta con el generador de perfiles que tiene este CLSID o ProgID, que se debe haber almacenado previamente en el Registro. La variable de entorno COR_PROFILER se define como una cadena, como se muestra en los dos ejemplos siguientes.  
  
    ```cpp  
    set COR_PROFILER={32E2F4DA-1BEA-47ea-88F9-C5DAF691C94A}  
    set COR_PROFILER="MyProfiler"  
    ```  
  
 Para generar el perfil de una aplicación CLR, debe establecer las variables de entorno COR_PROFILER y COR_ENABLE_PROFILING antes de ejecutar la aplicación. También debe asegurarse de que se haya registrado la DLL del generador de perfiles.  
  
> [!NOTE]
> A partir de .NET Framework 4, no es necesario registrar los generadores de perfiles.  
  
> [!NOTE]
> Para usar los generadores de perfiles de .NET Framework 2.0, 3.0 y 3.5 en .NET Framework 4 y versiones posteriores, debe establecer la variable de entorno COMPLUS_ProfAPI_ProfilerCompatibilitySetting.  
  
## <a name="environment-variable-scope"></a>Ámbito de la variable de entorno  
 La forma de establecer las variables de entorno COR_PROFILER y COR_ENABLE_PROFILING determina su ámbito de influencia. Puede establecer estas variables una de las siguientes maneras:  
  
- Si establece las variables en un [ICorDebug::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) llamada, se aplicarán solo a la aplicación que se está ejecutando en el momento. (También se aplicarán a otras aplicaciones iniciadas por esa aplicación que hereden el entorno.)  
  
- Si establece las variables en una ventana del símbolo del sistema, se aplicarán a todas las aplicaciones iniciadas desde esa ventana.  
  
- Si establece las variables en el nivel de usuario, se aplicarán a todas las aplicaciones que inicie con el Explorador de archivos. Una ventana del símbolo del sistema que abra después de establecer las variables tendrá esta configuración de entorno, y también la tendrán todas las aplicaciones que inicie desde esa ventana. Para establecer variables de entorno en el nivel de usuario, haga clic con el botón derecho en **Mi PC**, haga clic en **Propiedades**, haga clic en la ficha **Opciones avanzadas,** haga clic en **Variables**de entorno y agregue las variables a la lista **Variables** de usuario.  
  
- Si establece las variables en el nivel de equipo, se aplicarán a todas las aplicaciones que se inicien en ese equipo. Una ventana del símbolo del sistema que abra en ese equipo tendrá esta configuración de entorno, y también la tendrán todas las aplicaciones que inicie desde esa ventana. Esto significa que todos los procesos administrados de ese equipo se iniciarán con el generador de perfiles. Para establecer variables de entorno en el nivel de equipo, haga clic con el botón derecho en **Mi PC**, haga clic en **Propiedades**, haga clic en la ficha **Opciones avanzadas,** haga clic en **Variables**de entorno , agregue las variables a la lista **Variables** del sistema y, a continuación, reinicie el equipo. Después de reiniciar, las variables estarán disponibles para todo el sistema.  
  
 Si está generando perfiles para un servicio de Windows, debe reiniciar el equipo después de establecer las variables de entorno y registrar la DLL del generador de perfiles. Para obtener más información acerca de estas consideraciones, vea la sección Generación de [perfiles](#windows_service)de un servicio de Windows .  
  
## <a name="additional-considerations"></a>Consideraciones adicionales  
  
- La clase profiler implementa las interfaces [ICorProfilerCallback](icorprofilercallback-interface.md) y [ICorProfilerCallback2.](icorprofilercallback2-interface.md) En la versión 2.0 de .NET Framework, un generador de perfiles debe implementar `ICorProfilerCallback2`. Si no lo hace, no se cargará `ICorProfilerCallback2`.  
  
- Solamente un generador de perfiles puede generar un perfil en cada momento en un entorno determinado. Puede registrar dos generadores de perfiles diferentes en entornos diferentes, pero cada uno debe actuar en procesos independientes. El generador de perfiles se debe implementar como una DLL del servidor COM en proceso, que está asignada al mismo espacio de direcciones que el proceso que se está perfilando. Esto significa que el generador de perfiles se ejecuta en proceso. .NET Framework no es compatible con ningún otro tipo de servidor COM. Por ejemplo, si un generador de perfiles desea supervisar aplicaciones desde un equipo remoto, debe implementar agentes recolectores en cada PC. Estos agentes generarán resultados por lotes y los comunicarán al equipo central de recolección de datos.  
  
- Dado que el generador de perfiles es un objeto COM del que se crean instancias en proceso, cada aplicación para la que se generen perfiles tendrá su propia copia del generador de perfiles. Por consiguiente, una instancia única del generador de perfiles no tiene que administrar datos de varias aplicaciones. Sin embargo, tendrá que agregar lógica al código de registro del generador de perfiles para evitar que el archivo de registro sobrescriba otras aplicaciones para las que se haya generado perfiles.  
  
## <a name="initializing-the-profiler"></a>Inicializar el generador de perfiles  
 Cuando ambas comprobaciones de variables de entorno se realizan correctamente, CLR crea una instancia del generador de perfiles de una manera similar a la función COM `CoCreateInstance`. El generador de perfiles no se carga mediante una llamada directa a `CoCreateInstance`. Por consiguiente, se evita una llamada a `CoInitialize`, que requiere la configuración del modelo de subprocesos. A continuación, CLR llama al método [ICorProfilerCallback::Initialize](icorprofilercallback-initialize-method.md) en el generador de perfiles. La firma de este método es como sigue.  
  
```cpp  
HRESULT Initialize(IUnknown *pICorProfilerInfoUnk)  
```  
  
 El generador de `pICorProfilerInfoUnk` perfiles debe consultar un puntero de interfaz [ICorProfilerInfo](icorprofilerinfo-interface.md) o [ICorProfilerInfo2](icorprofilerinfo2-interface.md) y guardarlo para que pueda solicitar más información más adelante durante la generación de perfiles.  
  
## <a name="setting-event-notifications"></a>Establecer notificaciones de eventos  
 A continuación, el generador de perfiles llama al método [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) para especificar qué categorías de notificaciones le interesan. Por ejemplo, si el generador de perfiles solamente está interesado en notificaciones de entrada y salida de funciones y notificaciones de recolección de elementos no utilizados, especifica lo siguiente.  
  
```cpp  
ICorProfilerInfo* pInfo;  
pICorProfilerInfoUnk->QueryInterface(IID_ICorProfilerInfo, (void**)&pInfo);  
pInfo->SetEventMask(COR_PRF_MONITOR_ENTERLEAVE | COR_PRF_MONITOR_GC)  
```  
  
 Estableciendo la máscara de notificaciones de esta manera, el generador de perfiles puede limitar qué notificaciones recibe. Este enfoque ayuda al usuario a compilar un generador de perfiles simple o de propósito especial. También reduce tiempo de CPU que se gastaría enviando notificaciones que el generador de perfiles simplemente omitiría.  
  
 Ciertos eventos del generador de perfiles son inmutables. Esto significa que, tan pronto como se establezcan estos eventos en la devolución de llamada `ICorProfilerCallback::Initialize`, no se pueden desactivar y no es posible activar nuevos eventos. Los intentos de modificar un evento inmutable provocarán que `ICorProfilerInfo::SetEventMask` devuelva un HRESULT fallido.  
  
<a name="windows_service"></a>
## <a name="profiling-a-windows-service"></a>Generar perfiles en un servicio de Windows  
 La generación de perfiles de Servicio de Windows es similar a la generación de perfiles para una aplicación de Common Language Runtime. Ambas operaciones de generación de perfiles se habilitan mediante variables de entorno. Dado que un Servicio de Windows se inicia cuando se inicia el sistema operativo, las variables de entorno que se explican anteriormente en este tema deben estar ya presentes y establecidas en los valores necesarios antes de que se inicie el sistema. Además, la DLL de generación de perfiles debe estar ya registrada en el sistema.  
  
 Después de establecer las variables de entorno COR_PROFILER y COR_ENABLE_PROFILING, y de registrar la DLL del generador de perfiles, debe reiniciarse el equipo de destino para que el Servicio de Windows pueda detectar esos cambios.  
  
 Observe que estos cambios habilitarán la generación de perfiles para todo el sistema. Para evitar que se generen perfiles para cada aplicación administrada que se ejecute a continuación, debe eliminar las variables de entorno del sistema después de reiniciar el equipo de destino.  
  
 Esta técnica también provoca que se generen perfiles para todos los procesos de CLR. El generador de perfiles debe agregar lógica a su [ICorProfilerCallback::Initialize](icorprofilercallback-initialize-method.md) devolución de llamada para detectar si el proceso actual es de interés. Si no es así, el generador de perfiles puede producir un error en la devolución de llamada sin realizar la inicialización.  
  
## <a name="see-also"></a>Consulte también

- [Descripción general de la elaboración de perfiles](profiling-overview.md)
