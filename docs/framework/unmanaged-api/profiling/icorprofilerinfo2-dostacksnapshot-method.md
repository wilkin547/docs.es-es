---
title: "ICorProfilerInfo2::DoStackSnapshot (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.DoStackSnapshot
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::DoStackSnapshot
helpviewer_keywords:
- ICorProfilerInfo2::DoStackSnapshot method [.NET Framework profiling]
- DoStackSnapshot method [.NET Framework profiling]
ms.assetid: 287b11e9-7c52-4a13-ba97-751203fa97f4
topic_type: apiref
caps.latest.revision: "25"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5548254eb160547643a874fd2e31a085ec6f3ecb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo2dostacksnapshot-method"></a>ICorProfilerInfo2::DoStackSnapshot (Método)
Recorre los marcos administrados en la pila para el subproceso especificado y envía información al generador de perfiles mediante una devolución de llamada.  
  
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
  
 Si se pasa null en `thread` , se genera una instantánea del subproceso actual. Si un `ThreadID` de se pasa un subproceso diferente, common language runtime (CLR) suspende ese subproceso, realiza la instantánea y se reanuda.  
  
 `callback`  
 [in] Un puntero a la implementación de la [StackSnapshotCallback](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md) método, que es llamado por el CLR para proporcionar el generador de perfiles con información sobre cada marco administrado y cada ejecución de marcos no administrados.  
  
 El `StackSnapshotCallback` método lo implementa el escritor del generador de perfiles.  
  
 `infoFlags`  
 [in] Un valor de la [COR_PRF_SNAPSHOT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-snapshot-info-enumeration.md) enumeración, que especifica la cantidad de datos que se pasarán nuevo para cada fotograma por `StackSnapshotCallback`.  
  
 `clientData`  
 [in] Un puntero a los datos de cliente, que se pasan directamente a la `StackSnapshotCallback` función de devolución de llamada.  
  
 `context`  
 [in] Un puntero a Win32 `CONTEXT` estructura, que se utiliza para inicializar el recorrido de pila. Win32 `CONTEXT` estructura contiene valores de los registros de la CPU y representa el estado de la CPU en un momento determinado.  
  
 El valor de inicialización ayuda a CLR a determinar dónde comenzar el recorrido de pila, si la parte superior de la pila es código auxiliar no administrado; en caso contrario, se omite el valor de inicialización. Debe suministrar un valor de inicialización para los recorridos asincrónicos. Si va a realizar un recorrido sincrónico, no es necesario ningún valor de inicialización.  
  
 El `context` parámetro sólo es válido si el marcador COR_PRF_SNAPSHOT_CONTEXT se pasó en el `infoFlags` parámetro.  
  
 `contextSize`  
 [in] El tamaño de la `CONTEXT` estructura, que hace referencia el `context` parámetro.  
  
## <a name="remarks"></a>Comentarios  
 Si se pasa null para `thread` , se genera una instantánea del subproceso actual. Pueden tomar instantáneas de otros subprocesos sólo si se suspende el subproceso de destino en el momento.  
  
 Cuando el generador de perfiles desea recorrer la pila, llama al método `DoStackSnapshot`. Antes de que el CLR vuelva de esa llamada, llama a su `StackSnapshotCallback` varias veces, una vez para cada administran marco (o ejecución de marcos no administrados) en la pila. Cuando se encuentran marcos no administrados, debe recorrer a usted mismo.  
  
 El orden en el que se recorre la pila es el inverso de cómo los fotogramas se insertan en la pila: hoja (Insertar última) en primer lugar, principal (insertar primero) fotogramas última.  
  
 Para obtener más información acerca de cómo programar el generador de perfiles para rastrear pilas administradas, vea [recorrido de pila de generador de perfiles en .NET Framework 2.0: Basics y versiones posteriores](http://go.microsoft.com/fwlink/?LinkId=73638).  
  
 Un recorrido de pila puede ser sincrónicas o asincrónicas, como se explica en las secciones siguientes.  
  
## <a name="synchronous-stack-walk"></a>Recorrido de pila sincrónico  
 Un recorrido de pila sincrónico implica recorrer la pila del subproceso actual en respuesta a una devolución de llamada. No se requiere inicialización ni suspensión.  
  
 Realice una sincrónica a llamar cuando, en respuesta a una llamada entre el generador de perfiles de CLR [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) (o [ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)) métodos, se llama a `DoStackSnapshot` para recorrer la pila de la subproceso actual. Esto es útil cuando desea ver la pila de aspecto en una notificación como [ICorProfilerCallback:: ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md). Se llama a `DoStackSnapshot` desde su `ICorProfilerCallback` método, se pasa null en el `context` y `thread` parámetros.  
  
## <a name="asynchronous-stack-walk"></a>Recorrido de pila asincrónico  
 Un recorrido de pila asincrónico implica el recorrido de la pila de un subproceso diferente o recorrer la pila del subproceso actual, no en respuesta a una devolución de llamada, pero por cambiando la configuración de puntero de instrucción del subproceso actual. Un recorrido asincrónico requiere un valor de inicialización si la parte superior de la pila es código no administrado que no forma parte de una plataforma de invocación (PInvoke) o llamada de COM, pero código auxiliar en el CLR. Por ejemplo, el código que realiza la recopilación de compilación o de elementos no utilizados de just-in-time (JIT) es código auxiliar.  
  
 Obtener un valor de inicialización suspendiendo directamente el subproceso de destino y recorriendo la pila usted mismo, hasta que encuentre el primer marco administrado. Después de que se suspende el subproceso de destino, obtenga el contexto del registro actual del subproceso de destino. A continuación, determine si el contexto del Registro apunta a código no administrado mediante una llamada a [ICorProfilerInfo:: GetFunctionFromIP](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctionfromip-method.md) : si devuelve un `FunctionID` igual a cero, el marco es código no administrado. Ahora, recorra la pila hasta que llegue al primer marco administrado y, a continuación, calcule el contexto de inicialización basado en el contexto del registro para ese marco.  
  
 Llamar a `DoStackSnapshot` con su contexto de inicialización para comenzar el recorrido de pila asincrónico. Si no se proporciona un valor de inicialización, `DoStackSnapshot` podría omitir los marcos administrados en la parte superior de la pila y, por lo tanto, le proporcionará un recorrido de pila incompleto. Si se proporciona un valor de inicialización, debe señalar a compilado JIT o Native Image Generator (Ngen.exe)-genera código; en caso contrario, `DoStackSnapshot` devuelve el código de error, CORPROF_E_STACKSNAPSHOT_UNMANAGED_CTX.  
  
 Recorridos de pila asincrónicos fácilmente pueden causar interbloqueos o infracciones de acceso, a menos que siga estas instrucciones:  
  
-   Cuando suspende directamente los subprocesos, recuerde que sólo un subproceso que nunca se ha ejecutado el código administrado puede suspender otro subproceso.  
  
-   Bloquear siempre su [ICorProfilerCallback:: ThreadDestroyed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threaddestroyed-method.md) hasta que finalice el recorrido de pila del subproceso que la devolución de llamada.  
  
-   No mantenga un bloqueo mientras el generador de perfiles llama a una función CLR que puede desencadenar una recolección de elementos. Es decir, no mantenga un bloqueo si el subproceso que posee podría realizar una llamada que desencadena una recolección.  
  
 Hay también un riesgo de interbloqueo si se llama a `DoStackSnapshot` desde un subproceso que ha creado el generador de perfiles para que pueda recorrer la pila de un subproceso de destino diferente. La primera vez que el subproceso que creó entra en ciertos `ICorProfilerInfo*` métodos (incluidos los `DoStackSnapshot`), el CLR realizará por subproceso, inicialización específica del CLR en ese subproceso. Si el generador de perfiles ha suspendido el subproceso de destino cuyo pila intenta recorrer y si ese subproceso de destino ha ocurrido con su propio bloqueo necesario para realizar esta inicialización por subproceso, se producirá un interbloqueo. Para evitar este interbloqueo, realizar una llamada inicial a `DoStackSnapshot` desde el subproceso creado por el generador de perfiles para recorrer otro subproceso de destino, pero no suspende el subproceso de destino primero. Esta llamada inicial asegura que la inicialización por subproceso puede completarse sin interbloqueos. Si `DoStackSnapshot` se realiza correctamente y notifica al menos un fotograma, después de ese punto, que son seguros para ese subproceso creado por el generador de perfiles para suspender cualquier subproceso de destino y la llamada `DoStackSnapshot` para recorrer la pila de ese subproceso de destino.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICorProfilerInfo (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [ICorProfilerInfo2 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
