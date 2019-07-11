---
title: ICorProfilerCallback::ObjectReferences (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ObjectReferences
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ObjectReferences
helpviewer_keywords:
- ObjectReferences method [.NET Framework profiling]
- ICorProfilerCallback::ObjectReferences method [.NET Framework profiling]
ms.assetid: dd5e9b64-b4a3-4ba6-9be6-ddb540f4ffcf
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4141c79502dae89ec228e4e39da121615f292786
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782970"
---
# <a name="icorprofilercallbackobjectreferences-method"></a>ICorProfilerCallback::ObjectReferences (Método)
Notifica al generador de perfiles de objetos en memoria que se hace referencia el objeto especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT ObjectReferences(  
    [in]  ObjectID objectId,  
    [in]  ClassID  classId,  
    [in]  ULONG    cObjectRefs,  
    [in, size_is(cObjectRefs)] ObjectID objectRefIds[] );  
```  
  
## <a name="parameters"></a>Parámetros  
 `objectId`  
 [in] El identificador del objeto al que hace referencia a objetos.  
  
 `classId`  
 [in] El identificador de la clase que el objeto especificado es una instancia de.  
  
 `cObjectRefs`  
 [in] El número de objetos al que hace referencia el objeto especificado (es decir, el número de elementos de la `objectRefIds` matriz).  
  
 `objectRefIds`  
 [in] Una matriz de identificadores de objetos que se hace referencia por `objectId`.  
  
## <a name="remarks"></a>Comentarios  
 El `ObjectReferences` se llama al método para cada objeto restante en el montón de una vez completada una recolección de elementos. Si el generador de perfiles devuelve un error de esta devolución de llamada, los servicios de generación de perfiles dejarán de invocar esta devolución de llamada hasta la siguiente recolección de elementos no utilizados.  
  
 El `ObjectReferences` devolución de llamada puede usarse junto con el [ICorProfilerCallback:: RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) devolución de llamada para crear un gráfico de referencia de objeto completo para el tiempo de ejecución. Common language runtime (CLR) garantiza que cada referencia de objeto se notifica una sola vez mediante la `ObjectReferences` método.  
  
 Los identificadores de objeto devuelven por `ObjectReferences` no son válidos durante la devolución de llamada, porque la colección de elementos no utilizados podría estar moviendo los objetos. Por lo tanto, los generadores de perfiles no deben intentar inspeccionar objetos durante un `ObjectReferences` llamar. Cuando [ICorProfilerCallback2:: GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) se denomina la basura recopilación está completa y la inspección puede realizarse de forma segura.  
  
 Un valor null `ClassId` indica que `objectId` tiene un tipo que se está descargando.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerCallback (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
