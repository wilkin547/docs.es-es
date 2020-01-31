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
ms.openlocfilehash: 4eff8472e353c4e5fd2505b281cc9efc89f013fc
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867222"
---
# <a name="cor_prf_gc_generation-enumeration"></a>COR_PRF_GC_GENERATION (Enumeración)
Identifica una generación de recolección de elementos no utilizados.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
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
  
## <a name="remarks"></a>Notas  
 El recolector de elementos no utilizados mejora el rendimiento de la administración de memoria dividiendo los objetos en generaciones en función de la edad. El recolector de elementos no utilizados usa actualmente tres generaciones, numeradas como 0, 1 y 2, además de un segmento de montón especial que se utiliza para objetos grandes. Los objetos cuyo tamaño es mayor que un valor determinado se almacenan en el montón de objetos grandes. Otros objetos asignados empiezan fuera de la generación 0. Todos los objetos que existen después de la recolección de elementos no utilizados en la generación 0 se promueven a la generación 1. Los objetos que existen después de la recolección de elementos no utilizados se producen en la generación 1 se mueven a la generación 2.  
  
 El uso de generaciones significa que el recolector de elementos no utilizados tiene que trabajar solo con un subconjunto de los objetos asignados en un momento dado.  
  
 La estructura de [COR_PRF_GC_GENERATION_RANGE](cor-prf-gc-generation-range-structure.md) utiliza la enumeración `COR_PRF_GC_GENERATION`.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones para generación de perfiles](profiling-enumerations.md)
