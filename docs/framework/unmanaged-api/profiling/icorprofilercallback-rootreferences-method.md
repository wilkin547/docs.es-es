---
title: ICorProfilerCallback::RootReferences (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RootReferences
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RootReferences
helpviewer_keywords:
- RootReferences method [.NET Framework profiling]
- ICorProfilerCallback::RootReferences method [.NET Framework profiling]
ms.assetid: dbdf853b-d1a4-4828-8ef7-53d121d8e6ae
topic_type:
- apiref
ms.openlocfilehash: 9c96cacf508ef5c056a1ff4469247393fdfb9e9e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444475"
---
# <a name="icorprofilercallbackrootreferences-method"></a>ICorProfilerCallback::RootReferences (Método)
Notifica al generador de perfiles información sobre las referencias raíz después de la recolección de elementos no utilizados.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT RootReferences(  
    [in] ULONG    cRootRefs,  
    [in, size_is(cRootRefs)] ObjectID rootRefIds[] );  
```  
  
## <a name="parameters"></a>Parámetros  
 `cRootRefs`  
 de Número de referencias de la matriz de `rootRefIds`.  
  
 `rootRefIds`  
 de Matriz de identificadores de objeto que hacen referencia a un objeto estático o a un objeto de la pila.  
  
## <a name="remarks"></a>Comentarios  
 Se llama a `RootReferences` y [ICorProfilerCallback2:: RootReferences2 (](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) para notificar al generador de perfiles. Normalmente, los generadores implementarán uno u otro, pero no ambos, porque la información pasada en `RootReferences2` es un superconjunto de que se pasa en `RootReferences`.  
  
 Es posible que la matriz de `rootRefIds` contenga un objeto null. Por ejemplo, todas las referencias de objeto declaradas en la pila se tratan como raíces por el recolector de elementos no utilizados y siempre se informará.  
  
 Los identificadores de objeto devueltos por `RootReferences` no son válidos durante la devolución de llamada, ya que la recolección de elementos no utilizados podría estar en medio de mover objetos de direcciones antiguas a direcciones nuevas. Por lo tanto, los perfiles no deben intentar inspeccionar objetos durante una llamada `RootReferences`. Cuando se llama a [ICorProfilerCallback2:: garbagecollectionfinished (](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) , todos los objetos se movieron a sus nuevas ubicaciones y se pueden inspeccionar de forma segura.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerCallback (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
