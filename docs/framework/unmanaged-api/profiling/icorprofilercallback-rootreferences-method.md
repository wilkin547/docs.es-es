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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a68ea07c40c966422be6ebb663e62508032c2610
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67750446"
---
# <a name="icorprofilercallbackrootreferences-method"></a>ICorProfilerCallback::RootReferences (Método)
Notifica al generador de perfiles con información acerca de las referencias de raíz después de la recolección de elementos.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT RootReferences(  
    [in] ULONG    cRootRefs,  
    [in, size_is(cRootRefs)] ObjectID rootRefIds[] );  
```  
  
## <a name="parameters"></a>Parámetros  
 `cRootRefs`  
 [in] El número de referencias en el `rootRefIds` matriz.  
  
 `rootRefIds`  
 [in] Una matriz de identificadores de objeto que hacen referencia a un objeto estático o un objeto en la pila.  
  
## <a name="remarks"></a>Comentarios  
 Ambos `RootReferences` y [ICorProfilerCallback2:: Rootreferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) se llama para notificar al generador de perfiles. Los generadores de perfiles normalmente implementarán una u otra, pero no ambos, porque la información pasada `RootReferences2` es un superconjunto de las que pasa `RootReferences`.  
  
 Es posible que el `rootRefIds` matriz que contendrá un objeto null. Por ejemplo, todas las referencias de objeto declaradas en la pila se tratan como raíces por el recolector de elementos no utilizados y siempre se notificará.  
  
 Los identificadores de objeto devuelven por `RootReferences` no son válidos durante la devolución de llamada, porque podría ser la recolección de elementos en medio de mover objetos de direcciones antiguas a nuevas direcciones. Por lo tanto, los generadores de perfiles no deben intentar inspeccionar objetos durante un `RootReferences` llamar. Cuando [ICorProfilerCallback2:: GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) es llamado, todos los objetos se han movido a sus nuevas ubicaciones y se pueden inspeccionar de manera segura.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerCallback (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
