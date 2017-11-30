---
title: "COR_PRF_GC_GENERATION (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_GC_GENERATION
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_GC_GENERATION
helpviewer_keywords: COR_GC_GENERATION_FLAGS enumeration [.NET Framework profiling]
ms.assetid: d6ece160-26ad-4d39-abd7-05acd6f78c48
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a296dd333579f9d0e734b7c00a8adb648605295d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="corprfgcgeneration-enumeration"></a>COR_PRF_GC_GENERATION (Enumeración)
Identifica la generación de una colección de elementos no utilizados.  
  
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
 El recolector de elementos no utilizados mejora el rendimiento de la administración de memoria dividiendo los objetos en las generaciones según la edad. El recolector de elementos no utilizados utiliza actualmente tres generaciones numeradas de 0, 1 y 2, además de un segmento de montón especial que se utiliza para los objetos grandes. Los objetos cuyo tamaño es mayor que un valor determinado se almacenan en el montón de objetos grandes. Otros objetos asignados empiezan perteneciendo a la generación 0. Todos los objetos que existen después de recolección de elementos no utilizados se produce en la generación 0 se promueven a la generación 1. Mueven los objetos que existen después de que se realiza una recolección de la generación 1 a la generación 2.  
  
 El uso de generaciones significa que el recolector de elementos no utilizados tiene que trabajar con solo un subconjunto de los objetos asignados en cualquier momento.  
  
 El `COR_PRF_GC_GENERATION` enumeración es utilizada por la [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) estructura.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Enumeraciones de generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
