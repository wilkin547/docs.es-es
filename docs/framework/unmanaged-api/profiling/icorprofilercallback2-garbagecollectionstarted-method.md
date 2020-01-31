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
ms.openlocfilehash: c90c790c519cc0c422657e6e2d8040a365fbf48c
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865784"
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
  
## <a name="parameters"></a>Parameters  
 `cGenerations`  
 de Número total de entradas de la matriz de `generationCollected`.  
  
 `generationCollected`  
 de Matriz de valores booleanos, que se `true` si la generación que corresponde al índice de la matriz se va a recopilar mediante esta recolección de elementos no utilizados; de lo contrario, `false`.  
  
 La matriz se indiza mediante un valor de la enumeración [COR_PRF_GC_GENERATION](cor-prf-gc-generation-enumeration.md) , que indica la generación.  
  
 `reason`  
 de Un valor de la enumeración [COR_PRF_GC_REASON](cor-prf-gc-reason-enumeration.md) que indica la razón por la que se indujo la recolección de elementos no utilizados.  
  
## <a name="remarks"></a>Notas  
 Todas las devoluciones de llamada que pertenecen a esta recolección de elementos no utilizados se producirán entre la `GarbageCollectionStarted` devolución de llamada y la devolución de llamada [ICorProfilerCallback2:: garbagecollectionfinished (](icorprofilercallback2-garbagecollectionfinished-method.md) correspondiente. No es necesario que estas devoluciones de llamada se realicen en el mismo subproceso.  
  
 Es seguro que el generador de perfiles Inspeccione los objetos en sus ubicaciones originales durante la devolución de llamada de `GarbageCollectionStarted`. El recolector de elementos no utilizados comenzará a mover objetos después del retorno de `GarbageCollectionStarted`. Una vez que el generador de perfiles ha devuelto desde esta devolución de llamada, el generador de perfiles debe considerar que todos los identificadores de objeto no son válidos hasta recibir una devolución de llamada de `ICorProfilerCallback2::GarbageCollectionFinished`.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerCallback (interfaz)](icorprofilercallback-interface.md)
- [ICorProfilerCallback2 (interfaz)](icorprofilercallback2-interface.md)
