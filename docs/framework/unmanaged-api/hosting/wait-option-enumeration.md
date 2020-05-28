---
title: WAIT_OPTION (Enumeración)
ms.date: 03/30/2017
api_name:
- WAIT_OPTION
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- WAIT_OPTION
helpviewer_keywords:
- WAIT_OPTION enumeration [.NET Framework hosting]
ms.assetid: 962fc293-8ded-4b3b-90ce-2c21a4f1b244
topic_type:
- apiref
ms.openlocfilehash: 4c57a3fde3565a21800c60794b6c2d1c7616ddd8
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008006"
---
# <a name="wait_option-enumeration"></a>WAIT_OPTION (Enumeración)
Contiene valores que indican la acción que debe realizar un host si una operación solicitada por los bloques de Common Language Runtime (CLR).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum {  
    WAIT_MSGPUMP       = 0x1,  
    WAIT_ALERTABLE     = 0x2,  
    WAIT_NOTINDEADLOCK = 0x4,  
} WAIT_OPTION;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`WAIT_ALERTABLE`|Notifica al host que la tarea se debe reactivar si CLR llama al método [IHostTask:: Alert](ihosttask-alert-method.md) .|  
|`WAIT_MSGPUMP`|Notifica al host que debe bombear los mensajes en el subproceso del sistema operativo actual si el subproceso se bloquea. El tiempo de ejecución especifica este valor solo en un <xref:System.Threading.ApartmentState.STA> subproceso.|  
|`WAIT_NOTINDEADLOCK`|Notifica al host que un host no puede interrumpir la solicitud de sincronización especificada. Es decir, el host no puede devolver `HOST_E_DEADLOCK` .|  
  
## <a name="remarks"></a>Comentarios  
 Los métodos [IHostTaskManager:: Sleep](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md) y [IHostTaskManager:: switchtotask (](ihosttaskmanager-switchtotask-method.md) toman un parámetro de este tipo.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Enumeraciones para hosts](hosting-enumerations.md)
