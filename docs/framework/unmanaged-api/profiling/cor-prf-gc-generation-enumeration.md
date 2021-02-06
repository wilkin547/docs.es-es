---
description: 'Más información acerca de: enumeración COR_PRF_GC_GENERATION'
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
ms.openlocfilehash: 108bb4b2b4cba57235d354efe3b815a0e0df17ca
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99648940"
---
# <a name="cor_prf_gc_generation-enumeration"></a>COR_PRF_GC_GENERATION (Enumeración)

Identifica una generación de recolección de elementos no utilizados.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum {  
    COR_PRF_GC_GEN_0 = 0,  
    COR_PRF_GC_GEN_1 = 1,  
    COR_PRF_GC_GEN_2 = 2,  
    COR_PRF_GC_LARGE_OBJECT_HEAP = 3,
    COR_PRF_GC_PINNED_OBJECT_HEAP= 4
} COR_PRF_GC_GENERATION;  
```  
  
## <a name="members"></a>Members  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`COR_PRF_GC_GEN_0`|El objeto se almacena como generación 0.|  
|`COR_PRF_GC_GEN_1`|El objeto se almacena como generación 1.|  
|`COR_PRF_GC_GEN_2`|El objeto se almacena como generación 2.|  
|`COR_PRF_GC_LARGE_OBJECT_HEAP`|El objeto se almacena en el montón de objetos grandes.|  
|`COR_PRF_GC_PINNED_OBJECT_HEAP`|El objeto se almacena en el montón de objetos anclados.|  
  
## <a name="remarks"></a>Observaciones  

 El recolector de elementos no utilizados mejora el rendimiento de la administración de memoria dividiendo los objetos en generaciones en función de la edad. El recolector de elementos no utilizados usa actualmente tres generaciones, numeradas como 0, 1 y 2, y dos segmentos de montón especiales, uno para objetos grandes y otro para objetos anclados.
  
 Los objetos cuyo tamaño es mayor que un valor de umbral se almacenan en el montón de objetos grandes. Los objetos anclados se pueden asignar al montón de objetos anclados para evitar el costo de rendimiento de asignarlos en los montones normales. Otros objetos asignados empiezan fuera de la generación 0. Todos los objetos que existen después de la recolección de elementos no utilizados en la generación 0 se promueven a la generación 1. Los objetos que existen después de la recolección de elementos no utilizados se producen en la generación 1 se mueven a la generación 2.  
  
 El uso de generaciones significa que el recolector de elementos no utilizados tiene que trabajar solo con un subconjunto de los objetos asignados en un momento dado.  
  
 `COR_PRF_GC_GENERATION`La estructura de [COR_PRF_GC_GENERATION_RANGE](cor-prf-gc-generation-range-structure.md) usa la enumeración.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones para generación de perfiles](profiling-enumerations.md)
