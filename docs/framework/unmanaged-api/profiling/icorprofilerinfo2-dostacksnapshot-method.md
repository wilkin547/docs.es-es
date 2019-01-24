---
title: ICorProfilerInfo2::DoStackSnapshot (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.DoStackSnapshot
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::DoStackSnapshot
helpviewer_keywords:
- ICorProfilerInfo2::DoStackSnapshot method [.NET Framework profiling]
- DoStackSnapshot method [.NET Framework profiling]
ms.assetid: 287b11e9-7c52-4a13-ba97-751203fa97f4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d107653d34689814ae97ca4012d0fd2e2c4190dc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54727279"
---
# <a name="icorprofilerinfo2dostacksnapshot-method"></a>ICorProfilerInfo2::DoStackSnapshot (Método)
Recorre los marcos administrados en la pila para el subproceso especificado y envía información al generador de perfiles a través de una devolución de llamada.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT DoStackSnapshot(  
    [in] ThreadID thread,  
    [in] StackSnapshotCallback *callback,  
    [in] ULONG32 infoFlags,  
    [in] void *clientData,  
    [in, size_is(contextSize), length_is(contextSize)] BYTE context[],  
    [in] ULONG32 contextSize);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `thread`  
 [in] El identificador del subproceso de destino.  
  
 Si se pasa null en `thread` genera una instantánea del subproceso actual. Si un `ThreadID` de se pasa un subproceso diferente, common language runtime (CLR) suspende ese subproceso, realiza la instantánea y se reanuda.  
  
 `callback`  
 [in] Un puntero a la implementación de la [StackSnapshotCallback](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md) método, que es invocado por el CLR para proporcionar el generador de perfiles con información sobre cada marco administrado y cada ejecución de los marcos no administrados.  
  
 El `StackSnapshotCallback` método se implementa el sistema de escritura del generador de perfiles.  
  
 `infoFlags`  
 [in] Un valor de la [COR_PRF_SNAPSHOT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-snapshot-info-enumeration.md) enumeración, que especifica la cantidad de datos que se pasarán por cada marco por `StackSnapshotCallback`.  
  
 `clientData`  
 [in] Un puntero a los datos de cliente, que se pasan directamente a la `StackSnapshotCallback` función de devolución de llamada.  
  
 `context`  
 [in] Un puntero a Win32 `CONTEXT` estructura, que se usa para inicializar el recorrido de pila. Win32 `CONTEXT` estructura contiene valores de los registros de la CPU y representa el estado de la CPU en un momento determinado.  
  
 El valor de inicialización ayuda a CLR a determinar dónde debe comenzar el recorrido de pila, si la parte superior de la pila de código auxiliar no administrado; en caso contrario, se omite el valor de inicialización. Debe proporcionar un valor de inicialización para un recorrido asincrónico. Si va a realizar un recorrido sincrónico, no es necesario ningún valor de inicialización.  
  
 El `context` parámetro sólo es válido si el marcador COR_PRF_SNAPSHOT_CONTEXT se pasó el `infoFlags` parámetro.  
  
 `contextSize`  
 [in] El tamaño de la `CONTEXT` estructura, que hace referencia el `context` parámetro.  
  
## <a name="remarks"></a>Comentarios  
 Si se pasa null para `thread` genera una instantánea del subproceso actual. Pueden tomar instantáneas de otros subprocesos sólo si se suspende el subproceso de destino en el momento.  
  
 Cuando el generador de perfiles desea recorrer la pila, llama a `DoStackSnapshot`. Antes de que el CLR vuelva de esa llamada, llama a su `StackSnapshotCallback` varias veces, una vez para cada uno administrado fotograma (o ejecución de marcos no administrados) en la pila. Cuando se producen los marcos no administrados, debe recorrer ellos usted mismo.  
  
 El orden en el que se recorre la pila es el inverso de cómo se insertan los marcos en la pila: hoja (último-Insertar) en primer lugar, principal (insertar primero) fotograma por última vez.  
  
 Para obtener más información acerca de cómo programar el generador de perfiles para rastrear pilas administradas, vea [recorrido de pila de Profiler en .NET Framework 2.0: DoStackSnapshot](https://go.microsoft.com/fwlink/?LinkId=73638).  
  
 Un recorrido de pila puede ser sincrónico o asincrónico, como se explica en las secciones siguientes.  
  
## <a name="synchronous-stack-walk"></a>Recorrido de pila sincrónico  
 Un recorrido de pila sincrónico implica recorrer la pila del subproceso actual en respuesta a una devolución de llamada. No se requiere la propagación o la suspensión.  
  
 Realice una sincrónica a llamar cuando, en respuesta a una llamada a uno de su generador de perfiles de CLR [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) (o [ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)) métodos, se llama a `DoStackSnapshot` para recorrer la pila de la subproceso actual. Esto es útil cuando desee ver la pila de aspecto en una notificación como [ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md). Basta con llamar a `DoStackSnapshot` desde su `ICorProfilerCallback` método, se pasa null en el `context` y `thread` parámetros.  
  
## <a name="asynchronous-stack-walk"></a>Recorrido de pila asincrónico  
 Un recorrido de pila asincrónico conlleva recorrer la pila de un subproceso diferente o recorrido de la pila del subproceso actual, no en respuesta a una devolución de llamada, pero por secuestro de puntero de instrucción del subproceso actual. Un recorrido asincrónico requiere la invocación de un valor de inicialización si la parte superior de la pila de código no administrado que no forma parte de una plataforma (PInvoke) o llamada de COM, pero código auxiliar en el propio CLR. Por ejemplo, el código que realiza la colección de elementos no utilizados o compilación de just-in-time (JIT) es código auxiliar.  
  
 Obtener un valor de inicialización suspendiendo directamente el subproceso de destino y recorriendo la pila administrada por sí mismo, hasta que encuentre el primer fotograma. Después de que se suspende el subproceso de destino, obtenga el contexto del registro actual del subproceso de destino. A continuación, determine si el contexto del Registro apunta a código no administrado mediante una llamada a [GetFunctionFromIP](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctionfromip-method.md) , si devuelve un `FunctionID` igual a cero, el marco utiliza código no administrado. Ahora, recorra la pila hasta que llegue el primer marco administrado y, a continuación, calcule el contexto de inicialización basado en el contexto del registro para ese marco.  
  
 Llamar a `DoStackSnapshot` con el contexto de inicialización para comenzar el recorrido de pila asincrónico. Si no se proporciona un valor de inicialización, `DoStackSnapshot` podría omitir los marcos administrados en la parte superior de la pila y, por lo tanto, le proporcionará un recorrido de pila incompleta. Si proporciona un valor de inicialización, debe apuntar a JIT o Native Image Generator (Ngen.exe)-genera código; en caso contrario, `DoStackSnapshot` devuelve el código de error, CORPROF_E_STACKSNAPSHOT_UNMANAGED_CTX.  
  
 Recorridos de pila asincrónicos fácilmente pueden provocar interbloqueos o infracciones de acceso, a menos que siga estas directrices:  
  
-   Cuando suspende directamente los subprocesos, recuerde que sólo un subproceso que nunca se ha ejecutado el código administrado puede suspender otro subproceso.  
  
-   Bloquear siempre su [ThreadDestroyed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threaddestroyed-method.md) hasta que finalice el recorrido de pila del subproceso que la devolución de llamada.  
  
-   No mantenga un bloqueo mientras el generador de perfiles llama a una función CLR que puede desencadenar una recolección de elementos. Es decir, no mantenga un bloqueo si el subproceso propietario puede realizar una llamada que se desencadena una recolección de elementos.  
  
 Hay también un riesgo de interbloqueo si llama a `DoStackSnapshot` desde un subproceso que ha creado el generador de perfiles para que pueda recorrer la pila de un subproceso de destino diferente. La primera vez que el subproceso que creó entra en ciertos `ICorProfilerInfo*` métodos (incluidos `DoStackSnapshot`), el CLR llevará a cabo por el subproceso, la inicialización específica de CLR en ese subproceso. Si el generador de perfiles ha suspendido el subproceso de destino cuya pila se está intentando recorrer y si ese subproceso de destino que ha ocurrido con su propio bloqueo es necesario para realizar esta inicialización por subproceso, se producirá un interbloqueo. Para evitar este interbloqueo, realice una llamada inicial a `DoStackSnapshot` desde tu subproceso creado por el generador de perfiles para recorrer otro subproceso de destino, pero no suspender el subproceso de destino en primer lugar. Esta llamada inicial garantiza que se puede completar la inicialización por subproceso sin interbloqueo. Si `DoStackSnapshot` se realiza correctamente y notifica al menos un fotograma, después de ese punto, estará seguro de ese subproceso creado por el generador de perfiles para suspender cualquier subproceso de destino y la llamada `DoStackSnapshot` para recorrer la pila del subproceso de destino.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [ICorProfilerInfo (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [ICorProfilerInfo2 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
