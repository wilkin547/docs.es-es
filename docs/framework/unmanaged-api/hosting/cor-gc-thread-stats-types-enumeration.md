---
title: COR_GC_THREAD_STATS_TYPES (enumeración)
ms.date: 03/30/2017
api_name:
- COR_GC_THREAD_STATS_TYPES
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_GC_THREAD_STATS_TYPES
helpviewer_keywords:
- COR_GC_THREAD_STATS_TYPES enumeration [.NET Framework hosting]
ms.assetid: aa227704-0ab1-4b08-aee2-1f439762162e
topic_type:
- apiref
ms.openlocfilehash: 122536877b2fd5f0e5c64118bd978b54c4a8b3df
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95696822"
---
# <a name="cor_gc_thread_stats_types-enumeration"></a>COR_GC_THREAD_STATS_TYPES (enumeración)

Indica las estadísticas de recolección de elementos no utilizados de un subproceso.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum {  
    COR_GC_THREAD_HAS_PROMOTED_BYTES  = 0x00000001  
} COR_GC_THREAD_STATS_TYPES;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`COR_GC_THREAD_HAS_PROMOTED_BYTES`|El subproceso tiene bytes que se promovieron en la recolección de elementos no utilizados más reciente.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** GCHost. idl, GCHost. h  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Enumeraciones para hosts](hosting-enumerations.md)
