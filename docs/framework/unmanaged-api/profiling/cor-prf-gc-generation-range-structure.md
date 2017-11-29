---
title: COR_PRF_GC_GENERATION_RANGE (Estructura)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_GC_GENERATION_RANGE
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_GC_GENERATION_RANGE
helpviewer_keywords: COR_PRF_GC_GENERATION_RANGE structure [.NET Framework profiling]
ms.assetid: e7e07273-8d10-4a68-807e-59634e3f8c5e
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e2fd546a88f34906ab37e36377f67c26e80b2799
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="corprfgcgenerationrange-structure"></a>COR_PRF_GC_GENERATION_RANGE (Estructura)
Describe un intervalo (es decir, un bloque) de memoria sometida a recopilación de elementos no utilizados.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef struct COR_PRF_GC_GENERATION_RANGE {  
    COR_PRF_GC_GENERATION generation;  
    ObjectID rangeStart;  
    UINT_PTR rangeLength;  
    UINT_PTR rangeLengthReserved;  
} COR_PRF_GC_GENERATION_RANGE;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`generation`|Un valor de la [COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md) pertenece de enumeración que especifica la generación a la que el bloque de memoria.|  
|`rangeStart`|El identificador de un objeto que especifica la ubicación inicial del bloque de memoria.|  
|`rangeLength`|Un puntero a un entero que especifica el tamaño de la parte usada del bloque de memoria (es decir, la cantidad de memoria utilizada dentro del bloque).|  
|`rangeLengthReserved`|Un puntero a un entero que especifica el tamaño del bloque de memoria (es decir, la cantidad de memoria reservada para el bloque).|  
  
## <a name="remarks"></a>Comentarios  
 El `rangeLength` valor se garantiza que sea preciso solo si [ICorProfilerInfo2:: GetGenerationBounds](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getgenerationbounds-method.md) o [ICorProfilerInfo2:: GetObjectGeneration](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getobjectgeneration-method.md), ambos que usan el `COR_PRF_GC_GENERATION_RANGE` la estructura, se llama desde el [ICorProfilerCallback2:: GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md) o [ICorProfilerCallback2:: GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) método.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Estructuras de generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
