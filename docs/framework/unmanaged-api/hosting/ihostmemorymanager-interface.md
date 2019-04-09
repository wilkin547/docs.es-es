---
title: IHostMemoryManager (Interfaz)
ms.date: 03/30/2017
api_name:
- IHostMemoryManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager
helpviewer_keywords:
- IHostMemoryManager interface [.NET Framework hosting]
ms.assetid: a945d439-3b34-4aa4-b575-8413dd7806ce
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 57f34ed1796f6fa411d31fca83baeff693f85d70
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59137363"
---
# <a name="ihostmemorymanager-interface"></a>IHostMemoryManager (Interfaz)
Proporciona métodos que permiten a common language runtime (CLR) para realizar solicitudes de memoria virtual a través del host, en lugar de usar las funciones de memoria virtual estándar de Win32.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método AcquiredVirtualAddressSpace](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-acquiredvirtualaddressspace-method.md)|Notifica al host que common language runtime (CLR) ha adquirido la memoria especificada desde el sistema operativo.|  
|[Método CreateMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md)|Obtiene un puntero de interfaz a un [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) instancia que se usa para solicitar las asignaciones de memoria de un montón creado por el host.|  
|[Método GetMemoryLoad](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-getmemoryload-method.md)|Obtiene la cantidad de memoria física que se está usando actualmente, devuelto por el host.|  
|[Método NeedsVirtualAddressSpace](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-needsvirtualaddressspace-method.md)|Notifica al host que el CLR se va a intentar usar la memoria especificada.|  
|[Método RegisterMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md)|Registra un puntero a una función de devolución de llamada que el host invoca para notificar al CLR de la carga de memoria actual en el equipo.|  
|[Método ReleasedVirtualAddressSpace](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-releasedvirtualaddressspace-method.md)|Notifica al host que CLR ha terminado de utilizar la memoria especificada.|  
|[Método VirtualAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualalloc-method.md)|Actúa como un contenedor lógico para la función de Win32 correspondiente, que se reserva o confirma una región de páginas en el espacio de direcciones virtuales del proceso que realiza la llamada.|  
|[Método VirtualFree](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualfree-method.md)|Actúa como un contenedor lógico para la función de Win32 correspondiente, que libera, anula el registro, o si libera y anula una región de páginas dentro del espacio de direcciones virtuales del proceso que realiza la llamada.|  
|[Método VirtualProtect](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualprotect-method.md)|Actúa como un contenedor lógico para la función de Win32 correspondiente, que cambia la protección en una región de páginas confirmadas en el espacio de direcciones virtuales del proceso que realiza la llamada.|  
|[Método VirtualQuery](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualquery-method.md)|Actúa como un contenedor lógico para la función de Win32 correspondiente, que recupera información sobre un intervalo de páginas en el espacio de direcciones virtuales del proceso que realiza la llamada.|  
  
## <a name="remarks"></a>Comentarios  
 `IHostMemoryManager` También proporciona métodos de CLR para obtener un puntero a través de la que se deben realizar solicitudes de memoria en el montón y obtener el nivel de presión de memoria en el proceso, notificado por el host.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.h  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IHostMalloc (Interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
- [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
