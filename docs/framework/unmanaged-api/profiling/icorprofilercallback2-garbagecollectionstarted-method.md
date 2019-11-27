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
ms.openlocfilehash: ed2553f2d971deefd85f731dd39f383cd096c5b0
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439816"
---
# <a name="icorprofilercallback2garbagecollectionstarted-method"></a>ICorProfilerCallback2::GarbageCollectionStarted (Método)
Notifica al generador de perfiles de código que se ha iniciado la recolección de elementos no utilizados.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GarbageCollectionStarted(  
    [in] int cGenerations,  
    [in, size_is(cGenerations), length_is(cGenerations)] BOOL generationCollected[],  
    [in] COR_PRF_GC_REASON reason);  
```  
  
## <a name="parameters"></a>Parámetros  
 `cGenerations`  
 de Número total de entradas de la matriz de `generationCollected`.  
  
 `generationCollected`  
 de Matriz de valores booleanos, que se `true` si la generación que corresponde al índice de la matriz se va a recopilar mediante esta recolección de elementos no utilizados; de lo contrario, `false`.  
  
 La matriz se indiza mediante un valor de la enumeración [COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md) , que indica la generación.  
  
 `reason`  
 de Un valor de la enumeración [COR_PRF_GC_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-reason-enumeration.md) que indica la razón por la que se indujo la recolección de elementos no utilizados.  
  
## <a name="remarks"></a>Comentarios  
 Todas las devoluciones de llamada que pertenecen a esta recolección de elementos no utilizados se producirán entre la `GarbageCollectionStarted` devolución de llamada y la devolución de llamada [ICorProfilerCallback2:: garbagecollectionfinished (](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) correspondiente. No es necesario que estas devoluciones de llamada se realicen en el mismo subproceso.  
  
 Es seguro que el generador de perfiles Inspeccione los objetos en sus ubicaciones originales durante la devolución de llamada de `GarbageCollectionStarted`. El recolector de elementos no utilizados comenzará a mover objetos después del retorno de `GarbageCollectionStarted`. Una vez que el generador de perfiles ha devuelto desde esta devolución de llamada, el generador de perfiles debe considerar que todos los identificadores de objeto no son válidos hasta recibir una devolución de llamada de `ICorProfilerCallback2::GarbageCollectionFinished`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerCallback (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [ICorProfilerCallback2 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
