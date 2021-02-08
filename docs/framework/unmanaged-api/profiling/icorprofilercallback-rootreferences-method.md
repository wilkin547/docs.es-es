---
description: 'Más información acerca de: ICorProfilerCallback:: RootReferences (método)'
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
ms.openlocfilehash: e09434c425784e646c9856693abdfd4ac0d49273
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99788870"
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
 de Número de referencias de la `rootRefIds` matriz.  
  
 `rootRefIds`  
 de Matriz de identificadores de objeto que hacen referencia a un objeto estático o a un objeto de la pila.  
  
## <a name="remarks"></a>Observaciones  

 `RootReferences`Se llama a y [ICorProfilerCallback2:: RootReferences2 (](icorprofilercallback2-rootreferences2-method.md) para notificar al generador de perfiles. Normalmente, los generadores implementarán uno u otro, pero no ambos, ya que la información `RootReferences2` que se pasa es un superconjunto de que se ha pasado `RootReferences` .  
  
 Es posible `rootRefIds` que la matriz contenga un objeto null. Por ejemplo, todas las referencias de objeto declaradas en la pila se tratan como raíces por el recolector de elementos no utilizados y siempre se informará.  
  
 Los identificadores de objeto devueltos por `RootReferences` no son válidos durante la devolución de llamada, ya que la recolección de elementos no utilizados podría estar en medio de mover objetos de direcciones antiguas a direcciones nuevas. Por lo tanto, los perfiles no deben intentar inspeccionar objetos durante una `RootReferences` llamada. Cuando se llama a [ICorProfilerCallback2:: garbagecollectionfinished (](icorprofilercallback2-garbagecollectionfinished-method.md) , todos los objetos se movieron a sus nuevas ubicaciones y se pueden inspeccionar de forma segura.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerCallback (Interfaz)](icorprofilercallback-interface.md)
