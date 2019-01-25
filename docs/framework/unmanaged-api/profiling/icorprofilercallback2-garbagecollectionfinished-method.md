---
title: ICorProfilerCallback2::GarbageCollectionFinished (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.GarbageCollectionFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::GarbageCollectionFinished
helpviewer_keywords:
- ICorProfilerCallback2::GarbageCollectionFinished method [.NET Framework profiling]
- GarbageCollectionFinished method [.NET Framework profiling]
ms.assetid: 1a5758ea-2354-43c0-92a3-32c9909d64e1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 040c51723a2505a1320d2ecde38c9ed1cd19d254
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54734927"
---
# <a name="icorprofilercallback2garbagecollectionfinished-method"></a>ICorProfilerCallback2::GarbageCollectionFinished (Método)
Notifica al generador de perfiles que ha completado la recolección de elementos y todas las devoluciones de llamada de colección de elementos no utilizados se han emitido para ella.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GarbageCollectionFinished();  
```  
  
## <a name="remarks"></a>Comentarios  
 Es seguro para el generador de perfiles inspeccionar los objetos en sus ubicaciones finales cuando el `GarbageCollectionFinished` se llama al método.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [ICorProfilerCallback (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [ICorProfilerCallback2 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
