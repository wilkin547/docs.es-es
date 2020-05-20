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
ms.openlocfilehash: 88e81779fc9c20c506f3b0aa11ac2da3958dfe86
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616702"
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
|`PerThreadAllocation`|El número de bytes de memoria asignados en el subproceso que está asociado a la `COR_GC_THREAD_STATS` instancia actual. Este número se borra a cero cada vez que se produce una recolección de elementos no utilizados de generación cero.|  
|`Flags`|Número de bytes promocionados a una generación superior en la recolección de elementos no utilizados más reciente.|  
  
## <a name="remarks"></a>Observaciones  
 [ICLRTask:: getmemstats (](iclrtask-getmemstats-method.md) toma un parámetro de salida de tipo `COR_GC_THREAD_STATS` .  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** GCHost. idl  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulta también

- [Estructuras de hospedaje](hosting-structures.md)
- [IHostTask (Interfaz)](ihosttask-interface.md)
