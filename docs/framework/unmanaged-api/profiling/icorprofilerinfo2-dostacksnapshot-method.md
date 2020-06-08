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
ms.openlocfilehash: b9a7142de01d818390b740a795f70a4606952780
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84497379"
---
# <a name="icorprofilerinfo2dostacksnapshot-method"></a>ICorProfilerInfo2::DoStackSnapshot (Método)
Recorre los marcos administrados de la pila para el subproceso especificado y envía información al generador de perfiles a través de una devolución de llamada.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT DoStackSnapshot(  
    [in] ThreadID thread,  
    [in] StackSnapshotCallback *callback,  
    [in] ULONG32 infoFlags,  
    [in] void *clientData,  
    [in, size_is(contextSize), length_is(contextSize)] BYTE context[],  
    [in] ULONG32 contextSize);  
```  
  
## <a name="parameters"></a>Parámetros  
 `thread`  
 de IDENTIFICADOR del subproceso de destino.  
  
 Si se pasa null en, se `thread` produce una instantánea del subproceso actual. Si `ThreadID` se pasa un de un subproceso diferente, el Common Language Runtime (CLR) suspende ese subproceso, realiza la instantánea y se reanuda.  
  
 `callback`  
 de Un puntero a la implementación del método [StackSnapshotCallback](stacksnapshotcallback-function.md) , al que llama CLR para proporcionar al generador de perfiles información sobre cada marco administrado y cada ejecución de marcos no administrados.  
  
 El `StackSnapshotCallback` escritor del generador de perfiles implementa el método.  
  
 `infoFlags`  
 de Un valor de la enumeración [COR_PRF_SNAPSHOT_INFO](cor-prf-snapshot-info-enumeration.md) , que especifica la cantidad de datos que se van a devolver para cada marco `StackSnapshotCallback` .  
  
 `clientData`  
 de Puntero a los datos del cliente, que se pasa directamente a la `StackSnapshotCallback` función de devolución de llamada.  
  
 `context`  
 de Puntero a una estructura de Win32 `CONTEXT` , que se usa para inicializar el recorrido de la pila. La `CONTEXT` estructura Win32 contiene los valores de los registros de CPU y representa el estado de la CPU en un momento determinado en el tiempo.  
  
 La inicialización ayuda a CLR a determinar dónde debe comenzar el recorrido de la pila, si la parte superior de la pila es código auxiliar no administrado. de lo contrario, se omite el inicialización. Se debe proporcionar un parámetro de inicialización para un recorrido asincrónico. Si está realizando un recorrido sincrónico, no es necesario ningún SEED.  
  
 El `context` parámetro solo es válido si la marca de COR_PRF_SNAPSHOT_CONTEXT se ha pasado en el `infoFlags` parámetro.  
  
 `contextSize`  
 de Tamaño de la `CONTEXT` estructura, al que hace referencia el `context` parámetro.  
  
## <a name="remarks"></a>Comentarios  
 Si se pasa null para, se `thread` produce una instantánea del subproceso actual. Las instantáneas se pueden tomar de otros subprocesos solo si el subproceso de destino se suspende en el momento.  
  
 Cuando el generador de perfiles desea recorrer la pila, llama a `DoStackSnapshot` . Antes de que el CLR vuelva de esa llamada, llama a la `StackSnapshotCallback` varias veces, una vez por cada fotograma administrado (o la ejecución de marcos no administrados) en la pila. Cuando se encuentren fotogramas no administrados, debe recorrerlos usted mismo.  
  
 El orden en el que se recorre la pila es el inverso de cómo se insertaron los fotogramas en la pila: primero el fotograma (última inserción), el marco principal (primero insertado).  
  
 Para obtener más información sobre cómo programar el generador de perfiles para guiar pilas administradas, consulte [recorrido de la pila del generador de perfiles en el .NET Framework 2,0: aspectos básicos y más allá](https://docs.microsoft.com/previous-versions/dotnet/articles/bb264782(v=msdn.10)).  
  
 Un recorrido de pila puede ser sincrónico o asincrónico, como se explica en las secciones siguientes.  
  
## <a name="synchronous-stack-walk"></a>Recorrido de pila sincrónico  
 Un recorrido de pila sincrónico implica recorrer la pila del subproceso actual en respuesta a una devolución de llamada. No requiere propagación ni suspensión.  
  
 Realiza una llamada sincrónica cuando, en respuesta a CLR que llama a uno de los métodos [ICorProfilerCallback](icorprofilercallback-interface.md) (o [ICorProfilerCallback2](icorprofilercallback2-interface.md)) del generador de perfiles, llama `DoStackSnapshot` a para recorrer la pila del subproceso actual. Esto resulta útil cuando desea ver el aspecto de la pila en una notificación como [ICorProfilerCallback:: ObjectAllocated](icorprofilercallback-objectallocated-method.md). Basta con llamar a `DoStackSnapshot` desde dentro del `ICorProfilerCallback` método, pasando null en `context` los `thread` parámetros y.  
  
## <a name="asynchronous-stack-walk"></a>Recorrido de pila asincrónico  
 Un recorrido de pila asincrónico conlleva el recorrido de la pila de un subproceso diferente o el recorrido de la pila del subproceso actual, no en respuesta a una devolución de llamada, pero mediante el secuestro del puntero de instrucción del subproceso actual. Un recorrido asincrónico requiere un inicialización si la parte superior de la pila es código no administrado que no forma parte de una invocación de plataforma (PInvoke) o una llamada COM, sino código auxiliar en el propio CLR. Por ejemplo, el código que realiza la compilación Just-in-Time (JIT) o la recolección de elementos no utilizados es código auxiliar.  
  
 Para obtener un SEED, se suspende directamente el subproceso de destino y se recorre su pila, hasta que encuentre el marco administrado de nivel superior. Una vez suspendido el subproceso de destino, obtenga el contexto de registro actual del subproceso de destino. A continuación, determine si el contexto de registro apunta a código no administrado llamando a [ICorProfilerInfo:: getfunctionfromip (](icorprofilerinfo-getfunctionfromip-method.md) ; si devuelve un `FunctionID` valor igual a cero, el marco es código no administrado. Ahora, recorra la pila hasta llegar al primer marco administrado y, a continuación, calcule el contexto de inicialización basándose en el contexto de registro para ese marco.  
  
 Llame a `DoStackSnapshot` con el contexto de inicialización para iniciar el recorrido de pila asincrónico. Si no proporciona una inicialización, `DoStackSnapshot` puede omitir los marcos administrados en la parte superior de la pila y, por consiguiente, le proporcionará un recorrido de pila incompleto. Si proporciona una inicialización, debe apuntar a código generado por JIT o por el generador de imágenes nativas (Ngen. exe); de lo contrario, `DoStackSnapshot` devuelve el código de error CORPROF_E_STACKSNAPSHOT_UNMANAGED_CTX.  
  
 Los recorridos de pila asincrónicos pueden causar fácilmente interbloqueos o infracciones de acceso, a menos que siga estas directrices:  
  
- Cuando suspenda directamente los subprocesos, recuerde que solo un subproceso que nunca ha ejecutado código administrado puede suspender otro subproceso.  
  
- Bloquee siempre en la devolución de llamada [ICorProfilerCallback:: ThreadDestroyed (](icorprofilercallback-threaddestroyed-method.md) hasta que se complete el recorrido de la pila del subproceso.  
  
- No mantenga un bloqueo mientras el generador de perfiles llama a una función CLR que puede desencadenar una recolección de elementos no utilizados. Es decir, no debe mantener un bloqueo si el subproceso propietario puede realizar una llamada que desencadene una recolección de elementos no utilizados.  
  
 También hay un riesgo de interbloqueo si se llama a `DoStackSnapshot` desde un subproceso creado por el generador de perfiles para que pueda recorrer la pila de un subproceso de destino independiente. La primera vez que el subproceso creado entra `ICorProfilerInfo*` en determinados métodos (incluido `DoStackSnapshot` ), CLR realizará la inicialización específica de CLR por subproceso en ese subproceso. Si el generador de perfiles ha suspendido el subproceso de destino cuya pila está intentando recorrer y el subproceso de destino ha tenido que poseer un bloqueo necesario para realizar esta inicialización por subproceso, se producirá un interbloqueo. Para evitar este interbloqueo, realice una llamada inicial a `DoStackSnapshot` desde el subproceso creado por el generador de perfiles para recorrer un subproceso de destino independiente, pero no suspenda el subproceso de destino en primer lugar. Esta llamada inicial garantiza que la inicialización por subproceso se puede completar sin interbloqueo. Si se `DoStackSnapshot` realiza correctamente y notifica al menos un fotograma, después de ese punto, será seguro que el subproceso creado por el generador de perfiles suspenda cualquier subproceso de destino y llame `DoStackSnapshot` a para recorrer la pila de ese subproceso de destino.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [ICorProfilerInfo (Interfaz)](icorprofilerinfo-interface.md)
- [ICorProfilerInfo2 (Interfaz)](icorprofilerinfo2-interface.md)
