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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 74de8838d7f9ad1995bf7b15699b5589d13a0cab
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33428842"
---
# <a name="corgcthreadstatstypes-enumeration"></a>COR_GC_THREAD_STATS_TYPES (enumeración)
Indica las estadísticas de la colección de elementos no utilizados para un subproceso.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef enum {  
    COR_GC_THREAD_HAS_PROMOTED_BYTES  = 0x00000001  
} COR_GC_THREAD_STATS_TYPES;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`COR_GC_THREAD_HAS_PROMOTED_BYTES`|El subproceso tiene bytes que se han promovido en la recolección de elementos no utilizados más reciente.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** GCHost.idl, GCHost.h  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Enumeraciones para hosts](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
