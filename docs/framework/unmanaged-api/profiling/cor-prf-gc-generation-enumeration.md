---
title: COR_PRF_GC_GENERATION (Enumeración)
ms.date: 03/30/2017
api_name:
- COR_PRF_GC_GENERATION
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_GENERATION
helpviewer_keywords:
- COR_GC_GENERATION_FLAGS enumeration [.NET Framework profiling]
ms.assetid: d6ece160-26ad-4d39-abd7-05acd6f78c48
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0178e2a7877803644bb25e6700306d7ac2ef2d4f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775081"
---
# <a name="corprfgcgeneration-enumeration"></a>COR_PRF_GC_GENERATION (Enumeración)
Identifica una colección de elementos no utilizados de generación.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef enum {  
    COR_PRF_GC_GEN_0 = 0,  
    COR_PRF_GC_GEN_1 = 1,  
    COR_PRF_GC_GEN_2 = 2,  
    COR_PRF_GC_LARGE_OBJECT_HEAP = 3  
} COR_PRF_GC_GENERATION;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`COR_PRF_GC_GEN_0`|El objeto se almacena como generación 0.|  
|`COR_PRF_GC_GEN_1`|El objeto se almacena como generación 1.|  
|`COR_PRF_GC_GEN_2`|El objeto se almacena como generación 2.|  
|`COR_PRF_GC_LARGE_OBJECT_HEAP`|El objeto se almacena en el montón de objetos grandes.|  
  
## <a name="remarks"></a>Comentarios  
 El recolector de elementos no utilizados mejora el rendimiento de la administración de memoria dividiendo los objetos en las generaciones según la edad. El recolector de elementos no utilizados utiliza actualmente tres generaciones, numeradas de 0, 1 y 2, además de un segmento de montón especial que se usa para los objetos grandes. Los objetos cuyo tamaño es mayor que un valor determinado se almacenan en el montón de objetos grandes. Para empezar otros objetos asignados que pertenecen a la generación 0. Todos los objetos que existen después de que se produce una recolección en la generación 0 se promueven a la generación 1. Mueven los objetos que existen después de que se produce una recolección de generación 1 a la generación 2.  
  
 El uso de las generaciones significa que el recolector de elementos no utilizados tiene que trabajar con solo un subconjunto de los objetos asignados en cualquier momento.  
  
 El `COR_PRF_GC_GENERATION` enumeración la utiliza el [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) estructura.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
