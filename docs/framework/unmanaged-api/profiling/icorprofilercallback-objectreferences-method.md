---
title: "ICorProfilerCallback::ObjectReferences (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ObjectReferences
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ObjectReferences
helpviewer_keywords:
- ObjectReferences method [.NET Framework profiling]
- ICorProfilerCallback::ObjectReferences method [.NET Framework profiling]
ms.assetid: dd5e9b64-b4a3-4ba6-9be6-ddb540f4ffcf
topic_type: apiref
caps.latest.revision: "18"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 30b8f6b5f424ff81ace36baa8d2ae39e0a2f1d1e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackobjectreferences-method"></a>ICorProfilerCallback::ObjectReferences (Método)
Notifica al generador de perfiles acerca de los objetos en memoria que se hace referencia el objeto especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT ObjectReferences(  
    [in]  ObjectID objectId,  
    [in]  ClassID  classId,  
    [in]  ULONG    cObjectRefs,  
    [in, size_is(cObjectRefs)] ObjectID objectRefIds[] );  
```  
  
#### <a name="parameters"></a>Parámetros  
 `objectId`  
 [in] El identificador del objeto que hace referencia a objetos.  
  
 `classId`  
 [in] El identificador de la clase que el objeto especificado es una instancia de.  
  
 `cObjectRefs`  
 [in] El número de objetos al que hace referencia el objeto especificado (es decir, el número de elementos de la `objectRefIds` matriz).  
  
 `objectRefIds`  
 [in] Una matriz de identificadores de objetos que se hace referencia a por `objectId`.  
  
## <a name="remarks"></a>Comentarios  
 El `ObjectReferences` método se llama para cada objeto permanece en el montón después de que ha completado una recolección de elementos. Si el generador de perfiles devuelve un error de esta devolución de llamada, los servicios de generación de perfiles dejarán de invocar esta devolución de llamada hasta la siguiente recolección.  
  
 El `ObjectReferences` devolución de llamada puede utilizarse junto con la [ICorProfilerCallback:: RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) devolución de llamada para crear un gráfico de referencia de objeto completo para el tiempo de ejecución. Common language runtime (CLR) garantiza que cada referencia de objeto se ha notificado una sola vez por la `ObjectReferences` método.  
  
 Los identificadores de objeto devuelven por `ObjectReferences` no son válidos durante la devolución de llamada, porque la colección de elementos no utilizados puede estar en el proceso de mover objetos. Por lo tanto, los generadores de perfiles no deben intentar inspeccionar objetos durante una `ObjectReferences` llamar. Cuando [ICorProfilerCallback2:: GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) se llama, los elementos no utilizados recopilación está completa y la inspección puede realizarse de forma segura.  
  
 Un valor null `ClassId` indica que `objectId` tiene un tipo que se está descargando.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICorProfilerCallback (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
