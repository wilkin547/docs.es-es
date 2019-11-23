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
ms.openlocfilehash: 86720cb1739e3f193cd1d5081577d69bca1cf0f9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427055"
---
# <a name="setting-up-a-profiling-environment"></a>Configurar un entorno de generación de perfiles
> [!NOTE]
> There have been substantial changes to profiling in the .NET Framework 4.  
  
 Cuando se inicia un proceso administrado (aplicación o servicio), se carga el Common Language Runtime (CLR). Cuando se inicializa el CLR, evalúa las siguientes dos variables de entorno para decidir si el proceso debería conectar con un generador de perfiles:  
  
- COR_ENABLE_PROFILING: CLR solamente se conecta a un generador de perfiles si esta variable de entorno existe y está establecida en 1.  
  
- COR_PROFILER: si la comprobación de COR_ENABLE_PROFILING es correcta, CLR conecta con el generador de perfiles que tiene este CLSID o ProgID, que se debe haber almacenado previamente en el Registro. La variable de entorno COR_PROFILER se define como una cadena, como se muestra en los dos ejemplos siguientes.  
  
    ```cpp  
    set COR_PROFILER={32E2F4DA-1BEA-47ea-88F9-C5DAF691C94A}  
    set COR_PROFILER="MyProfiler"  
    ```  
  
 Para generar el perfil de una aplicación CLR, debe establecer las variables de entorno COR_PROFILER y COR_ENABLE_PROFILING antes de ejecutar la aplicación. También debe asegurarse de que se haya registrado la DLL del generador de perfiles.  
  
> [!NOTE]
> Starting with the .NET Framework 4, profilers do not have to be registered.  
  
> [!NOTE]
> To use .NET Framework versions 2.0, 3.0, and 3.5 profilers in the .NET Framework 4 and later versions, you must set the COMPLUS_ProfAPI_ProfilerCompatibilitySetting environment variable.  
  
## <a name="environment-variable-scope"></a>Ámbito de la variable de entorno  
 La forma de establecer las variables de entorno COR_PROFILER y COR_ENABLE_PROFILING determina su ámbito de influencia. Puede establecer estas variables una de las siguientes maneras:  
  
- If you set the variables in an [ICorDebug::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) call, they will apply only to the application that you are running at the time. (También se aplicarán a otras aplicaciones iniciadas por esa aplicación que hereden el entorno.)  
  
- Si establece las variables en una ventana del símbolo del sistema, se aplicarán a todas las aplicaciones iniciadas desde esa ventana.  
  
- Si establece las variables en el nivel de usuario, se aplicarán a todas las aplicaciones que inicie con el Explorador de archivos. Una ventana del símbolo del sistema que abra después de establecer las variables tendrá esta configuración de entorno, y también la tendrán todas las aplicaciones que inicie desde esa ventana. To set environment variables at the user level, right-click **My Computer**, click **Properties**, click the **Advanced** tab, click **Environment Variables**, and add the variables to the **User variables** list.  
  
- Si establece las variables en el nivel de equipo, se aplicarán a todas las aplicaciones que se inicien en ese equipo. Una ventana del símbolo del sistema que abra en ese equipo tendrá esta configuración de entorno, y también la tendrán todas las aplicaciones que inicie desde esa ventana. Esto significa que todos los procesos administrados de ese equipo se iniciarán con el generador de perfiles. To set environment variables at the computer level, right-click **My Computer**, click **Properties**, click the **Advanced** tab, click **Environment Variables**, add the variables to the **System variables** list, and then restart your computer. Después de reiniciar, las variables estarán disponibles para todo el sistema.  
  
 Si está generando perfiles para un servicio de Windows, debe reiniciar el equipo después de establecer las variables de entorno y registrar la DLL del generador de perfiles. For more information about these considerations, see the section [Profiling a Windows Service](#windows_service).  
  
## <a name="additional-considerations"></a>Consideraciones adicionales  
  
- The profiler class implements the [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) and [ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md) interfaces. En la versión 2.0 de .NET Framework, un generador de perfiles debe implementar `ICorProfilerCallback2`. Si no lo hace, no se cargará `ICorProfilerCallback2`.  
  
- Solamente un generador de perfiles puede generar un perfil en cada momento en un entorno determinado. Puede registrar dos generadores de perfiles diferentes en entornos diferentes, pero cada uno debe actuar en procesos independientes. El generador de perfiles se debe implementar como una DLL del servidor COM en proceso, que está asignada al mismo espacio de direcciones que el proceso que se está perfilando. Esto significa que el generador de perfiles se ejecuta en proceso. .NET Framework no es compatible con ningún otro tipo de servidor COM. Por ejemplo, si un generador de perfiles desea supervisar aplicaciones desde un equipo remoto, debe implementar agentes recolectores en cada PC. Estos agentes generarán resultados por lotes y los comunicarán al equipo central de recolección de datos.  
  
- Dado que el generador de perfiles es un objeto COM del que se crean instancias en proceso, cada aplicación para la que se generen perfiles tendrá su propia copia del generador de perfiles. Por consiguiente, una instancia única del generador de perfiles no tiene que administrar datos de varias aplicaciones. Sin embargo, tendrá que agregar lógica al código de registro del generador de perfiles para evitar que el archivo de registro sobrescriba otras aplicaciones para las que se haya generado perfiles.  
  
## <a name="initializing-the-profiler"></a>Inicializar el generador de perfiles  
 Cuando ambas comprobaciones de variables de entorno se realizan correctamente, CLR crea una instancia del generador de perfiles de una manera similar a la función COM `CoCreateInstance`. El generador de perfiles no se carga mediante una llamada directa a `CoCreateInstance`. Por consiguiente, se evita una llamada a `CoInitialize`, que requiere la configuración del modelo de subprocesos. The CLR then calls the [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) method in the profiler. La firma de este método es como sigue.  
  
```cpp  
HRESULT Initialize(IUnknown *pICorProfilerInfoUnk)  
```  
  
 The profiler must query `pICorProfilerInfoUnk` for an [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) or [ICorProfilerInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md) interface pointer and save it so that it can request more information later during profiling.  
  
## <a name="setting-event-notifications"></a>Establecer notificaciones de eventos  
 The profiler then calls the [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method to specify which categories of notifications it is interested in. Por ejemplo, si el generador de perfiles solamente está interesado en notificaciones de entrada y salida de funciones y notificaciones de recolección de elementos no utilizados, especifica lo siguiente.  
  
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
  
 Esta técnica también provoca que se generen perfiles para todos los procesos de CLR. The profiler should add logic to its [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback to detect whether the current process is of interest. Si no es así, el generador de perfiles puede producir un error en la devolución de llamada sin realizar la inicialización.  
  
## <a name="see-also"></a>Vea también

- [Información general sobre la generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-overview.md)
