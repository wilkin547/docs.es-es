---
title: COR_GC_THREAD_STATS (Estructura)
ms.date: 03/30/2017
api_name:
- COR_GC_THREAD_STATS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_GC_THREAD_STATS
helpviewer_keywords:
- COR_GC_THREAD_STATS structure [.NET Framework hosting]
ms.assetid: 01f9a59b-7679-4d42-9ced-4a8981625c3d
topic_type:
- apiref
ms.openlocfilehash: 37da471aaa8e9f802a8430d7b3289b375ff1b40a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136982"
---
# <a name="cor_gc_thread_stats-structure"></a>COR_GC_THREAD_STATS (Estructura)
Contiene estadísticas por subproceso relativas a la recolección de elementos no utilizados.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef struct _COR_GC_THREAD_STATS {  
    ULONGLONG  PerThreadAllocation;   
    ULONG      Flags;   
} COR_GC_THREAD_STATS;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`PerThreadAllocation`|Número de bytes de memoria asignados en el subproceso asociado a la instancia de `COR_GC_THREAD_STATS` actual. Este número se borra a cero cada vez que se produce una recolección de elementos no utilizados de generación cero.|  
|`Flags`|Número de bytes promocionados a una generación superior en la recolección de elementos no utilizados más reciente.|  
  
## <a name="remarks"></a>Comentarios  
 [ICLRTask:: getmemstats (](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md) toma un parámetro de salida de tipo `COR_GC_THREAD_STATS`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** GCHost. idl  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Estructuras de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [IHostTask (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
