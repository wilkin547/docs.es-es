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
ms.openlocfilehash: aec3c5f140df7eab10ea2bfa33634a4d853adcb0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134288"
---
# <a name="ememoryavailable-enumeration"></a>EMemoryAvailable (Enumeración)
Contiene valores que indican la cantidad de memoria física disponible en el equipo. Estos valores se asignan lógicamente a los eventos de memoria alta y baja devueltas por la función `CreateMemoryResourceNotification` de la API de Windows.  
  
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
  
## <a name="remarks"></a>Comentarios  
 El host pasa este valor al Common Language Runtime (CLR) mediante una llamada al método [ICLRMemoryNotificationCallback:: OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md) .  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones para hosts](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
