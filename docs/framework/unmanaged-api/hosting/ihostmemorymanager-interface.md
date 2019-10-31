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
ms.openlocfilehash: bc05d76795f20d28d6d2899d61dc4674ebfdca8c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128649"
---
# <a name="ihostmemorymanager-interface"></a>IHostMemoryManager (Interfaz)
Proporciona métodos que permiten que el Common Language Runtime (CLR) realice solicitudes de memoria virtual a través del host, en lugar de usar las funciones estándar de memoria virtual de Win32.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[AcquiredVirtualAddressSpace (método)](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-acquiredvirtualaddressspace-method.md)|Notifica al host que el Common Language Runtime (CLR) ha adquirido la memoria especificada del sistema operativo.|  
|[CreateMAlloc (método)](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md)|Obtiene un puntero de interfaz a una instancia de [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) que se utiliza para solicitar las asignaciones de memoria de un montón creado por el host.|  
|[GetMemoryLoad (método)](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-getmemoryload-method.md)|Obtiene la cantidad de memoria física que se está usando actualmente, tal y como la ha proporcionado el host.|  
|[NeedsVirtualAddressSpace (método)](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-needsvirtualaddressspace-method.md)|Notifica al host que el CLR va a intentar usar la memoria especificada.|  
|[RegisterMemoryNotificationCallback (método)](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md)|Registra un puntero a una función de devolución de llamada que invoca el host para notificar a CLR la carga de memoria actual en el equipo.|  
|[ReleasedVirtualAddressSpace (método)](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-releasedvirtualaddressspace-method.md)|Notifica al host que el CLR ha terminado de usar la memoria especificada.|  
|[VirtualAlloc (método)](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualalloc-method.md)|Actúa como contenedor lógico de la función de Win32 correspondiente, que reserva o confirma una región de páginas en el espacio de direcciones virtuales del proceso de llamada.|  
|[VirtualFree (método)](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualfree-method.md)|Actúa como un contenedor lógico para la función de Win32 correspondiente, que libera, anula o libera y anula la confirmación de una región de páginas dentro del espacio de direcciones virtuales del proceso de llamada.|  
|[VirtualProtect (método)](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualprotect-method.md)|Actúa como contenedor lógico de la función de Win32 correspondiente, que cambia la protección en una región de páginas confirmadas en el espacio de direcciones virtuales del proceso de llamada.|  
|[VirtualQuery (método)](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-virtualquery-method.md)|Actúa como contenedor lógico de la función de Win32 correspondiente, que recupera información sobre un intervalo de páginas en el espacio de direcciones virtuales del proceso de llamada.|  
  
## <a name="remarks"></a>Comentarios  
 `IHostMemoryManager` también proporciona métodos para que CLR obtenga un puntero a través del cual se realizan solicitudes de memoria en el montón y para obtener el nivel de presión de memoria en el proceso, tal y como lo indica el host.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IHostMalloc (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)
- [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
