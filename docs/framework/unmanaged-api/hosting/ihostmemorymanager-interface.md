---
title: IHostMemoryManager (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostMemoryManager
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostMemoryManager
helpviewer_keywords: IHostMemoryManager interface [.NET Framework hosting]
ms.assetid: a945d439-3b34-4aa4-b575-8413dd7806ce
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b39a43874bc1808928f21e0a35638aae9a99ca8e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ihostmemorymanager-interface"></a>IHostMemoryManager (Interfaz)
Proporciona métodos que permiten a common language runtime (CLR) para realizar solicitudes de memoria virtual a través del host, en lugar de utilizar las funciones estándar de memoria virtual de Win32.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[AcquiredVirtualAddressSpace (método)](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-acquiredvirtualaddressspace-method.md)|Notifica al host que common language runtime (CLR) ha adquirido la memoria especificada del sistema operativo.|  
|[CreateMAlloc (método)](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md)|Obtiene un puntero de interfaz a una [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) instancia que se usa para solicitar las asignaciones de memoria de un montón creado por el host.|  
|[GetMemoryLoad (método)](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-getmemoryload-method.md)|Obtiene la cantidad de memoria física que se está usando actualmente, devuelto por el host.|  
|[NeedsVirtualAddressSpace (método)](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-needsvirtualaddressspace-method.md)|Notifica al host que el CLR se va a intentar utilizar la memoria especificada.|  
|[RegisterMemoryNotificationCallback (método)](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md)|Registra un puntero a una función de devolución de llamada que el host invoca para notificar a CLR de la carga de memoria actual en el equipo.|  
|[ReleasedVirtualAddressSpace (método)](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-releasedvirtualaddressspace-method.md)|Notifica al host que CLR ha terminado de utilizar la memoria especificada.|  
|[VirtualAlloc (método)](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualalloc-method.md)|Actúa como un contenedor lógico para la función de Win32 correspondiente, que se reserva o confirma una región de páginas en el espacio de direcciones virtuales del proceso que realiza la llamada.|  
|[VirtualFree (método)](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualfree-method.md)|Actúa como un contenedor lógico para la función de Win32 correspondiente, que libera, anula el registro, o si libera y anula el registro de una región de páginas en el espacio de direcciones virtuales del proceso que realiza la llamada.|  
|[VirtualProtect (método)](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualprotect-method.md)|Actúa como un contenedor lógico para la función de Win32 correspondiente, que cambia la protección en una región de páginas confirmadas en el espacio de direcciones virtuales del proceso que realiza la llamada.|  
|[VirtualQuery (método)](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualquery-method.md)|Actúa como un contenedor lógico para la función de Win32 correspondiente, que recupera información sobre un intervalo de páginas en el espacio de direcciones virtuales del proceso que realiza la llamada.|  
  
## <a name="remarks"></a>Comentarios  
 `IHostMemoryManager`También proporciona métodos para el CLR obtener un puntero a través del cual para realizar solicitudes de memoria en el montón y obtener el nivel de presión de memoria en el proceso, tal y como informa el host.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE.h  
  
 **Biblioteca:** incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [IHostMalloc (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)  
 [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
