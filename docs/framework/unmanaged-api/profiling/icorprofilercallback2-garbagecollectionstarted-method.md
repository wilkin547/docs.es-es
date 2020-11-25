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
ms.openlocfilehash: 63a8d212a61bd73f44995f0e057eeff96f9a5554
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731961"
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
 de Número total de entradas de la `generationCollected` matriz.  
  
 `generationCollected`  
 de Matriz de valores booleanos, que es `true` si la generación que corresponde al índice de la matriz se está recopilando por esta recolección de elementos no utilizados; en caso contrario, es `false` .  
  
 La matriz se indiza mediante un valor de la enumeración [COR_PRF_GC_GENERATION](cor-prf-gc-generation-enumeration.md) , que indica la generación.  
  
 `reason`  
 de Un valor de la enumeración [COR_PRF_GC_REASON](cor-prf-gc-reason-enumeration.md) que indica la razón por la que se indujo la recolección de elementos no utilizados.  
  
## <a name="remarks"></a>Comentarios  

 Todas las devoluciones de llamada que pertenecen a esta recolección de elementos no utilizados se producirán entre la `GarbageCollectionStarted` devolución de llamada y la devolución de llamada [ICorProfilerCallback2:: garbagecollectionfinished (](icorprofilercallback2-garbagecollectionfinished-method.md) correspondiente. No es necesario que estas devoluciones de llamada se realicen en el mismo subproceso.  
  
 Es seguro que el generador de perfiles Inspeccione los objetos en sus ubicaciones originales durante la `GarbageCollectionStarted` devolución de llamada. El recolector de elementos no utilizados comenzará a mover objetos después del retorno de `GarbageCollectionStarted` . Una vez que el generador de perfiles ha devuelto desde esta devolución de llamada, el generador de perfiles debe considerar que todos los identificadores de objeto no son válidos hasta recibir una `ICorProfilerCallback2::GarbageCollectionFinished` devolución de llamada.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICorProfilerCallback (Interfaz)](icorprofilercallback-interface.md)
- [ICorProfilerCallback2 (Interfaz)](icorprofilercallback2-interface.md)
