---
title: COR_PRF_MONITOR (Enumeración)
ms.date: 03/30/2017
api_name:
- COR_PRF_MONITOR
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_MONITOR
helpviewer_keywords:
- COR_PRF_MONITOR enumeration [.NET Framework profiling]
ms.assetid: 9294d702-b4e5-441c-a930-e63d27b86bfd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b6916c223aee615fad0bb9e5a47691122db41c98
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67752057"
---
# <a name="corprfmonitor-enumeration"></a>COR_PRF_MONITOR (Enumeración)
Contiene valores que se usan para especificar el comportamiento, las funcionalidades o los eventos a los que el generador de perfiles quiere suscribirse.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum {  
    COR_PRF_MONITOR_NONE                = 0x00000000,  
    COR_PRF_MONITOR_FUNCTION_UNLOADS    = 0x00000001,  
    COR_PRF_MONITOR_CLASS_LOADS         = 0x00000002,  
    COR_PRF_MONITOR_MODULE_LOADS        = 0x00000004,  
    COR_PRF_MONITOR_ASSEMBLY_LOADS      = 0x00000008,  
    COR_PRF_MONITOR_APPDOMAIN_LOADS     = 0x00000010,  
    COR_PRF_MONITOR_JIT_COMPILATION     = 0x00000020,  
    COR_PRF_MONITOR_EXCEPTIONS          = 0x00000040,  
    COR_PRF_MONITOR_GC                  = 0x00000080,  
    COR_PRF_MONITOR_OBJECT_ALLOCATED    = 0x00000100,  
    COR_PRF_MONITOR_THREADS             = 0x00000200,  
    COR_PRF_MONITOR_REMOTING            = 0x00000400,  
    COR_PRF_MONITOR_CODE_TRANSITIONS    = 0x00000800,  
    COR_PRF_MONITOR_ENTERLEAVE          = 0x00001000,  
    COR_PRF_MONITOR_CCW                 = 0x00002000,  
    COR_PRF_MONITOR_REMOTING_COOKIE     = 0x00004000 |   
                                          COR_PRF_MONITOR_REMOTING,  
    COR_PRF_MONITOR_REMOTING_ASYNC      = 0x00008000 |   
                                          COR_PRF_MONITOR_REMOTING,  
    COR_PRF_MONITOR_SUSPENDS            = 0x00010000,  
    COR_PRF_MONITOR_CACHE_SEARCHES      = 0x00020000,  
    COR_PRF_ENABLE_REJIT                = 0x00040000,  
    COR_PRF_ENABLE_INPROC_DEBUGGING     = 0x00080000,  
    COR_PRF_ENABLE_JIT_MAPS             = 0x00100000,  
    COR_PRF_DISABLE_INLINING            = 0x00200000,  
    COR_PRF_DISABLE_OPTIMIZATIONS       = 0x00400000,  
    COR_PRF_ENABLE_OBJECT_ALLOCATED     = 0x00800000,  
    COR_PRF_MONITOR_CLR_EXCEPTIONS      = 0x01000000,  
    COR_PRF_MONITOR_ALL                 = 0x0107FFFF,  
    COR_PRF_ENABLE_FUNCTION_ARGS        = 0X02000000,  
    COR_PRF_ENABLE_FUNCTION_RETVAL      = 0X04000000,  
    COR_PRF_ENABLE_FRAME_INFO           = 0X08000000,  
    COR_PRF_ENABLE_STACK_SNAPSHOT       = 0X10000000,  
    COR_PRF_USE_PROFILE_IMAGES          = 0x20000000,  
    COR_PRF_DISABLE_TRANSPARENCY_CHECKS_UNDER_FULL_TRUST  
                                        = 0x40000000,  
    COR_PRF_DISABLE_ALL_NGEN_IMAGES     = 0x80000000,  
    COR_PRF_ALL                         = 0x8FFFFFFF,  
    COR_PRF_REQUIRE_PROFILE_IMAGE       = COR_PRF_USE_PROFILE_IMAGES |   
                                          COR_PRF_MONITOR_CODE_TRANSITIONS |   
                                          COR_PRF_MONITOR_ENTERLEAVE,  
    COR_PRF_ALLOWABLE_AFTER_ATTACH      = COR_PRF_MONITOR_THREADS |  
                                          COR_PRF_MONITOR_MODULE_LOADS |  
                                          COR_PRF_MONITOR_ASSEMBLY_LOADS |  
                                          COR_PRF_MONITOR_APPDOMAIN_LOADS |  
                                          COR_PRF_ENABLE_STACK_SNAPSHOT |  
                                          COR_PRF_MONITOR_GC |  
                                          COR_PRF_MONITOR_SUSPENDS |  
                                          COR_PRF_MONITOR_CLASS_LOADS |  
                                          COR_PRF_MONITOR_JIT_COMPILATION,  
    COR_PRF_MONITOR_IMMUTABLE           = COR_PRF_MONITOR_CODE_TRANSITIONS |  
                                          COR_PRF_MONITOR_REMOTING |  
                                          COR_PRF_MONITOR_REMOTING_COOKIE |  
                                          COR_PRF_MONITOR_REMOTING_ASYNC |  
                                          COR_PRF_ENABLE_REJIT |  
                                          COR_PRF_ENABLE_INPROC_DEBUGGING |  
                                          COR_PRF_ENABLE_JIT_MAPS |  
                                          COR_PRF_DISABLE_OPTIMIZATIONS |  
                                          COR_PRF_DISABLE_INLINING |  
                                          COR_PRF_ENABLE_OBJECT_ALLOCATED |  
                                          COR_PRF_ENABLE_FUNCTION_ARGS |  
                                          COR_PRF_ENABLE_FUNCTION_RETVAL |  
                                          COR_PRF_ENABLE_FRAME_INFO |  
                                          COR_PRF_USE_PROFILE_IMAGES |  
                     COR_PRF_DISABLE_TRANSPARENCY_CHECKS_UNDER_FULL_TRUST |  
                                          COR_PRF_DISABLE_ALL_NGEN_IMAGES  
} COR_PRF_MONITOR;  
```  
  
## <a name="members"></a>Miembros  
 La secciones siguientes se muestran `COR_PRF_MONITOR` miembros de la enumeración por categoría. Las categorías son:  
  
- [No hay ningún conjunto de marcas](#None)  
  
- [Marcas de devolución de llamada](#Callback)  
  
- [Marcas para habilitar características](#Feature)  
  
- [Marcas de configuración](#Config)  
  
- [Marcas compuestas](#Composite)  
  
<a name="None"></a>   
### <a name="no-flags-set"></a>No hay ningún conjunto de marcas  
  
|Member|DESCRIPCIÓN|  
|------------|-----------------|  
|`COR_PRF_MONITOR_NONE`|No se establecen marcas.|  
  
<a name="Callback"></a>   
### <a name="callback-flags"></a>Marcas de devolución de llamada  
  
|Member|DESCRIPCIÓN|  
|------------|-----------------|  
|`COR_PRF_MONITOR_ALL`|Habilita todos los eventos de devolución de llamada.|  
|`COR_PRF_MONITOR_APPDOMAIN_LOADS`|Los controles de la `AppDomainCreation*` y `AppDomainShutdown*` devoluciones de llamada en el [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interfaz.|  
|`COR_PRF_MONITOR_ASSEMBLY_LOADS`|Los controles de la `AssemblyLoad*` y `AssemblyUnload*` devoluciones de llamada en el [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interfaz.|  
|`COR_PRF_MONITOR_CACHE_SEARCHES`|Los controles de la `JITCachedFunctionSearch*` devoluciones de llamada en el [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interfaz.<br /><br /> El comportamiento de esta marca se cambió en .NET Framework versión 2.0.|  
|`COR_PRF_MONITOR_CCW`|Los controles de la `COMClassicVTable*` devoluciones de llamada en el [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interfaz.|  
|`COR_PRF_MONITOR_CLASS_LOADS`|Los controles de la `ClassLoad*` y `ClassUnload*` devoluciones de llamada en el [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interfaz.|  
|`COR_PRF_MONITOR_CLR_EXCEPTIONS`|Los controles de la `ExceptionCLRCatcher*` devoluciones de llamada en el [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interfaz.|  
|`COR_PRF_MONITOR_CODE_TRANSITIONS`|Los controles de la [UnmanagedToManagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md) y [ManagedToUnmanagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md) devoluciones de llamada en el [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interfaz|  
|`COR_PRF_MONITOR_ENTERLEAVE`|Los controles de la `FunctionEnter*`, `FunctionLeave*`, y `FunctionTailCall*` [funciones estáticas globales de generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md).|  
|`COR_PRF_MONITOR_EXCEPTIONS`|Los controles de la [ExceptionThrown](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionthrown-method.md) devolución de llamada y el `ExceptionSearch*`, `ExceptionOSHandler*`, `ExceptionUnwind*`, y `ExceptionCatcher*` devoluciones de llamada en el [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interfaz.|  
|`COR_PRF_MONITOR_FUNCTION_UNLOADS`|Los controles de la [FunctionUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-functionunloadstarted-method.md) devolución de llamada en el [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interfaz.|  
|`COR_PRF_MONITOR_GC`|Los controles de la [GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md), [GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md), [MovedReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md), [MovedReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md), [ SurvivingReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-survivingreferences-method.md), [SurvivingReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-survivingreferences2-method.md), [ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md), [ObjectsAllocatedByClass](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectsallocatedbyclass-method.md), [ RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md), [RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md), [HandleCreated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-handlecreated-method.md), [HandleDestroyed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-handledestroyed-method.md), y [FinalizeableObjectQueued ](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-finalizeableobjectqueued-method.md) devoluciones de llamada en el `ICorProfilerCallback*` interfaces. Cuando `COR_PRF_MONITOR_GC` elementos no utilizados simultánea, asignado colección se ha desactivado.|  
|`COR_PRF_MONITOR_JIT_COMPILATION`|Los controles de la `JITCompilation*`, [JITFunctionPitched](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitfunctionpitched-method.md), y [JITInlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md) devoluciones de llamada en el [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interfaz.|  
|`COR_PRF_MONITOR_MODULE_LOADS`|Los controles de la `ModuleLoad*`, `ModuleUnload*`, y [ModuleAttachedToAssembly](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleattachedtoassembly-method.md) devoluciones de llamada en el [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interfaz.|  
|`COR_PRF_MONITOR_OBJECT_ALLOCATED`|Los controles de la [ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md) devolución de llamada en el [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interfaz.|  
|`COR_PRF_MONITOR_REMOTING`|Los controles de la `Remoting*` devoluciones de llamada en el [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interfaz.|  
|`COR_PRF_MONITOR_REMOTING_ASYNC`|Controla si las devoluciones de llamada `Remoting*` supervisarán eventos asincrónicos.|  
|`COR_PRF_MONITOR_REMOTING_COOKIE`|Controla si se pasa una cookie a las devoluciones de llamada `Remoting*`.|  
|`COR_PRF_MONITOR_SUSPENDS`|Los controles de la `RuntimeSuspend*`, `RuntimeResume*`, [RuntimeThreadSuspended](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadsuspended-method.md), y [RuntimeThreadResumed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadresumed-method.md) devoluciones de llamada en el [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interfaz.|  
|`COR_PRF_MONITOR_THREADS`|Los controles de la [ThreadCreated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadcreated-method.md), [ThreadDestroyed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threaddestroyed-method.md), [ThreadAssignedToOSThread](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadassignedtoosthread-method.md), y [ThreadNameChanged](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-threadnamechanged-method.md) devoluciones de llamada en el [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) y [ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md) interfaces.|  
  
<a name="Feature"></a>   
### <a name="feature-enabling-flags"></a>Marcas para habilitar características  
  
|Member|DESCRIPCIÓN|  
|------------|-----------------|  
|`COR_PRF_ENABLE_FRAME_INFO`|Habilita la recuperación de una ciencia exacta `ClassID` para una función genérica llamando el [GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) método con un `COR_PRF_FRAME_INFO` valor devuelto por la [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) devolución de llamada.|  
|`COR_PRF_ENABLE_FUNCTION_ARGS`|Seguimiento de los argumentos de habilita usando el [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) devolución de llamada o el [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md) devolución de llamada y el [GetFunctionEnter3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md) método.|  
|`COR_PRF_ENABLE_FUNCTION_RETVAL`|Habilita el seguimiento de los valores devueltos mediante el uso de la [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) devolución de llamada o el [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md) devolución de llamada y [GetFunctionLeave3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md) método.|  
|`COR_PRF_ENABLE_INPROC_DEBUGGING`|En desuso.<br /><br /> No se admite la depuración en proceso. Esta marca no tiene efecto.|  
|`COR_PRF_ENABLE_JIT_MAPS`|En desuso.<br /><br /> Permite al generador de perfiles obtener asignaciones de IL a nativo mediante [GetILToNativeMapping](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md). A partir de .NET Framework 2.0, el tiempo de ejecución siempre realiza el seguimiento de las asignaciones de IL a nativo; por lo tanto, se considera que esta marca está siempre establecida.|  
|`COR_PRF_ENABLE_OBJECT_ALLOCATED`|Informa al tiempo de ejecución que puede que el generador de perfiles quiera notificaciones de asignación de objetos. Esta marca se debe establecer durante la inicialización. Permite que el generador de perfiles seguir usando el `COR_PRF_MONITOR_OBJECT_ALLOCATED` marca para recibir [ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md) devoluciones de llamada.|  
|`COR_PRF_ENABLE_REJIT`|Habilita las llamadas a la [RequestReJIT](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrejit-method.md) y [RequestRevert](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrevert-method.md) métodos. El generador de perfiles debe establecer esta marca en el inicio.  Si el generador de perfiles especifica esta marca, también debe especificar `COR_PRF_DISABLE_ALL_NGEN_IMAGES`.|  
|`COR_PRF_ENABLE_STACK_SNAPSHOT`|Habilita las llamadas a la [DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) método.|  
  
<a name="Config"></a>   
### <a name="configuration-flags"></a>Marcas de configuración  
  
|Member|DESCRIPCIÓN|  
|------------|-----------------|  
|`COR_PRF_DISABLE_ALL_NGEN_IMAGES`|Impide que se carguen todas las imágenes nativas (incluidas imágenes mejoradas por el generador de perfiles).  Si se especifican esta marca y la marca `COR_PRF_USE_PROFILE_IMAGES`, se usa `COR_PRF_DISABLE_ALL_NGEN_IMAGES`.|  
|`COR_PRF_DISABLE_INLINING`|Deshabilita todas las inserciones.|  
|`COR_PRF_DISABLE_OPTIMIZATIONS`|Deshabilita todas las optimizaciones de código.|  
|`COR_PRF_DISABLE_TRANSPARENCY_CHECKS_UNDER_FULL_TRUST`|Deshabilita las comprobaciones de transparencia de seguridad que normalmente se realizan durante la compilación Just-In-Time (JIT) y la carga de las clases para ensamblados de confianza total. Esto puede hacer que la instrumentación sea más fácil de realizar.|  
|`COR_PRF_USE_PROFILE_IMAGES`|Hace que la búsqueda de imágenes nativas busque imágenes mejoradas por el generador de perfiles. Si no se encuentra ninguna imagen mejorada por el generador de perfiles para un ensamblado determinado, Common Language Runtime vuelve a JIT para ese ensamblado. Si se especifican esta marca y la marca `COR_PRF_DISABLE_ALL_NGEN_IMAGES`, se usa `COR_PRF_DISABLE_ALL_NGEN_IMAGES`.|  
  
<a name="Composite"></a>   
### <a name="composite-flags"></a>Marcas compuestas  
  
|Member|DESCRIPCIÓN|  
|------------|-----------------|  
|`COR_PRF_ALL`|Representa todos los valores de la marca `COR_PRF_MONITOR`.|  
|`COR_PRF_ALLOWABLE_AFTER_ATTACH`|Representa todas las marcas `COR_PRF_MONITOR` que se pueden establecer después de que el generador de perfiles se asocie a una aplicación en ejecución. En la sección sobre la sintaxis se indica cada una de las marcas presentes en esta máscara de bits.|  
|`COR_PRF_MONITOR_ALL`|Habilita todos los eventos de devolución de llamada.|  
|`COR_PRF_MONITOR_IMMUTABLE`|Representa todas las marcas `COR_PRF_MONITOR` que se pueden establecer solo durante la inicialización. Al intentar cambiar cualquiera de estas marcas después de la inicialización se genera un valor `HRESULT` que indica error.|  
|`COR_PRF_REQUIRE_PROFILE_IMAGE`|Representa todas las marcas `COR_PRF_MONITOR` que requieren imágenes mejoradas para el perfil.|  
  
## <a name="remarks"></a>Comentarios  
 Un `COR_PRF_MONITOR` valor se usa con el [ICorProfilerInfo:: GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md) y [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) métodos para definir las notificaciones de eventos que common language runtime realiza para el generador de perfiles.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
- [GetEventMask (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md)
- [SetEventMask (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)
