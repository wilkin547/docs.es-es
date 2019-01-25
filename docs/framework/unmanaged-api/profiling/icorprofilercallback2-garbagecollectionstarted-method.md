---
title: ICorProfilerCallback2::GarbageCollectionStarted (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.GarbageCollectionStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::GarbageCollectionStarted
helpviewer_keywords:
- GarbageCollectionStarted method [.NET Framework profiling]
- ICorProfilerCallback2::GarbageCollectionStarted method [.NET Framework profiling]
ms.assetid: 44eef087-f21f-4fe2-b481-f8a0ee022e7d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6c610445d5467a49b8a50b279d8f7fe706e21f73
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54555666"
---
# <a name="icorprofilercallback2garbagecollectionstarted-method"></a>ICorProfilerCallback2::GarbageCollectionStarted (Método)
Notifica al generador de perfiles de código que ha iniciado la recopilación de elementos no utilizados.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GarbageCollectionStarted(  
    [in] int cGenerations,  
    [in, size_is(cGenerations), length_is(cGenerations)] BOOL generationCollected[],  
    [in] COR_PRF_GC_REASON reason);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `cGenerations`  
 [in] El número total de entradas en el `generationCollected` matriz.  
  
 `generationCollected`  
 [in] Una matriz de valores booleanos, que son `true` si la generación que se corresponde con el índice de matriz está siendo recopilados por esta colección de elementos no utilizados; en caso contrario, `false`.  
  
 La matriz se indiza por un valor de la [COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md) enumeración, que indica la generación.  
  
 `reason`  
 [in] Un valor de la [COR_PRF_GC_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-reason-enumeration.md) indujo la enumeración que indica la razón por la recolección de elementos.  
  
## <a name="remarks"></a>Comentarios  
 Todas las devoluciones de llamada que pertenecen a esta colección de elementos no utilizados se producirán entre el `GarbageCollectionStarted` devolución de llamada y el correspondiente [ICorProfilerCallback2:: GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) devolución de llamada. No es necesitan que estas devoluciones de llamada se produzca en el mismo subproceso.  
  
 Es seguro para el generador de perfiles inspeccionar los objetos en sus ubicaciones originales durante la `GarbageCollectionStarted` devolución de llamada. El recolector de elementos no utilizados se iniciará el movimiento de objetos después de la devolución de `GarbageCollectionStarted`. Después de que el generador de perfiles ha devuelto desde esta devolución de llamada, el generador de perfiles debe tener en cuenta todos los identificadores de objeto son válidos hasta que reciba un `ICorProfilerCallback2::GarbageCollectionFinished` devolución de llamada.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [ICorProfilerCallback (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [ICorProfilerCallback2 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
