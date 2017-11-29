---
title: "ICorProfilerCallback::RootReferences (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.RootReferences
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::RootReferences
helpviewer_keywords:
- RootReferences method [.NET Framework profiling]
- ICorProfilerCallback::RootReferences method [.NET Framework profiling]
ms.assetid: dbdf853b-d1a4-4828-8ef7-53d121d8e6ae
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a12dec1ed0fecad235090592def9689f60e50193
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackrootreferences-method"></a>ICorProfilerCallback::RootReferences (Método)
Notifica al generador de perfiles con información sobre las referencias raíz después de recolección de elementos no utilizados.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT RootReferences(  
    [in] ULONG    cRootRefs,  
    [in, size_is(cRootRefs)] ObjectID rootRefIds[] );  
```  
  
#### <a name="parameters"></a>Parámetros  
 `cRootRefs`  
 [in] El número de referencias en el `rootRefIds` matriz.  
  
 `rootRefIds`  
 [in] Una matriz de identificadores de objeto que hacen referencia a un objeto estático o un objeto en la pila.  
  
## <a name="remarks"></a>Comentarios  
 Ambos `RootReferences` y [ICorProfilerCallback2:: Rootreferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) se llama para notificar al generador de perfiles. Los generadores de perfiles normalmente implementarán uno u otro, pero no ambos, porque la información que se pasa en `RootReferences2` es un supraconjunto de la que se pasan en `RootReferences`.  
  
 Es posible que el `rootRefIds` matriz para que contenga un objeto null. Por ejemplo, todas las referencias a objeto declaradas en la pila se tratan como raíces por el recolector de elementos no utilizados y siempre se notificará.  
  
 Los identificadores de objeto devuelven por `RootReferences` no son válidos durante la devolución de llamada, porque la colección de elementos no utilizados puede estar en el proceso de mover objetos de direcciones antiguas a nuevas direcciones. Por lo tanto, los generadores de perfiles no deben intentar inspeccionar objetos durante una `RootReferences` llamar. Cuando [ICorProfilerCallback2:: GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) es llama, todos los objetos que se han movido a sus nuevas ubicaciones y se puede inspeccionar con seguridad.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICorProfilerCallback (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
