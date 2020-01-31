---
title: COR_PRF_GC_GENERATION_RANGE (Estructura)
ms.date: 03/30/2017
api_name:
- COR_PRF_GC_GENERATION_RANGE
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_GENERATION_RANGE
helpviewer_keywords:
- COR_PRF_GC_GENERATION_RANGE structure [.NET Framework profiling]
ms.assetid: e7e07273-8d10-4a68-807e-59634e3f8c5e
topic_type:
- apiref
ms.openlocfilehash: 682aac9729519e0861ae6e6f60df78a30063c278
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867219"
---
# <a name="cor_prf_gc_generation_range-structure"></a>COR_PRF_GC_GENERATION_RANGE (Estructura)
Describe un intervalo (es decir, un bloque) de memoria sometida a recopilación de elementos no utilizados.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
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
|`generation`|Un valor de la enumeración [COR_PRF_GC_GENERATION](cor-prf-gc-generation-enumeration.md) que especifica la generación a la que pertenece el bloque de memoria.|  
|`rangeStart`|IDENTIFICADOR de un objeto que especifica la ubicación inicial del bloque de memoria.|  
|`rangeLength`|Un puntero a un entero que especifica el tamaño de la parte utilizada del bloque de memoria (es decir, la cantidad de memoria que se usa en el bloque).|  
|`rangeLengthReserved`|Un puntero a un entero que especifica el tamaño del bloque de memoria (es decir, la cantidad de memoria reservada para el bloque).|  
  
## <a name="remarks"></a>Notas  
 Se garantiza que el valor `rangeLength` sea preciso solo si [ICorProfilerInfo2:: getgenerationbounds (](icorprofilerinfo2-getgenerationbounds-method.md) o [Icorprofilerinfo2:: getobjectgeneration (](icorprofilerinfo2-getobjectgeneration-method.md), ambos usan la estructura `COR_PRF_GC_GENERATION_RANGE`, se llama desde [ICorProfilerCallback2:: garbagecollectionstarted (](icorprofilercallback2-garbagecollectionstarted-method.md) o el método [ICorProfilerCallback2:: garbagecollectionfinished (](icorprofilercallback2-garbagecollectionfinished-method.md) .  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Corprof. idl  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Estructuras para generación de perfiles](profiling-structures.md)
