---
title: EMemoryAvailable (Enumeración)
ms.date: 03/30/2017
api_name:
- EMemoryAvailable
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EMemoryAvailable
helpviewer_keywords:
- EMemoryAvailable enumeration [.NET Framework hosting]
ms.assetid: 38e72a06-dbed-473b-a59b-7e0b3ea4f2af
topic_type:
- apiref
ms.openlocfilehash: 822396e28d000a5309738680fec502e1aeacd67c
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616221"
---
# <a name="ememoryavailable-enumeration"></a>EMemoryAvailable (Enumeración)
Contiene valores que indican la cantidad de memoria física disponible en el equipo. Estos valores se asignan lógicamente a los eventos de memoria alta y baja devueltas por la `CreateMemoryResourceNotification` función en la API de Windows.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum {  
    eMemoryAvailableLow     = 1,  
    eMemoryAvailableNeutral = 2,  
    eMemoryAvailableHigh    = 3
} EMemoryAvailable;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`eMemoryAvailableHigh`|Hay mucha memoria física disponible.|  
|`eMemoryAvailableLow`|Hay muy poca memoria física disponible.|  
|`eMemoryAvailableNeutral`|La memoria física disponible es neutra.|  
  
## <a name="remarks"></a>Observaciones  
 El host pasa este valor al Common Language Runtime (CLR) mediante una llamada al método [ICLRMemoryNotificationCallback:: OnMemoryNotification](iclrmemorynotificationcallback-onmemorynotification-method.md) .  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulta también

- [Enumeraciones para hosts](hosting-enumerations.md)
