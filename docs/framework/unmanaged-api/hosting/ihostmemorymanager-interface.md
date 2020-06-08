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
ms.openlocfilehash: 09b4a06892cdc450eed9dead503a990b6f19804e
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501513"
---
# <a name="ihostmemorymanager-interface"></a>IHostMemoryManager (Interfaz)
Proporciona métodos que permiten que el Common Language Runtime (CLR) realice solicitudes de memoria virtual a través del host, en lugar de usar las funciones estándar de memoria virtual de Win32.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método AcquiredVirtualAddressSpace](ihostmemorymanager-acquiredvirtualaddressspace-method.md)|Notifica al host que el Common Language Runtime (CLR) ha adquirido la memoria especificada del sistema operativo.|  
|[Método CreateMAlloc](ihostmemorymanager-createmalloc-method.md)|Obtiene un puntero de interfaz a una instancia de [IHostMAlloc](ihostmalloc-interface.md) que se utiliza para solicitar las asignaciones de memoria de un montón creado por el host.|  
|[Método GetMemoryLoad](ihostmemorymanager-getmemoryload-method.md)|Obtiene la cantidad de memoria física que se está usando actualmente, tal y como la ha proporcionado el host.|  
|[Método NeedsVirtualAddressSpace](ihostmemorymanager-needsvirtualaddressspace-method.md)|Notifica al host que el CLR va a intentar usar la memoria especificada.|  
|[Método RegisterMemoryNotificationCallback](ihostmemorymanager-registermemorynotificationcallback-method.md)|Registra un puntero a una función de devolución de llamada que invoca el host para notificar a CLR la carga de memoria actual en el equipo.|  
|[Método ReleasedVirtualAddressSpace](ihostmemorymanager-releasedvirtualaddressspace-method.md)|Notifica al host que el CLR ha terminado de usar la memoria especificada.|  
|[Método VirtualAlloc](ihostmemorymanager-virtualalloc-method.md)|Actúa como contenedor lógico de la función de Win32 correspondiente, que reserva o confirma una región de páginas en el espacio de direcciones virtuales del proceso de llamada.|  
|[Método VirtualFree](ihostmemorymanager-virtualfree-method.md)|Actúa como un contenedor lógico para la función de Win32 correspondiente, que libera, anula o libera y anula la confirmación de una región de páginas dentro del espacio de direcciones virtuales del proceso de llamada.|  
|[Método VirtualProtect](ihostmemorymanager-virtualprotect-method.md)|Actúa como contenedor lógico de la función de Win32 correspondiente, que cambia la protección en una región de páginas confirmadas en el espacio de direcciones virtuales del proceso de llamada.|  
|[Método VirtualQuery](ihostmemorymanager-virtualquery-method.md)|Actúa como contenedor lógico de la función de Win32 correspondiente, que recupera información sobre un intervalo de páginas en el espacio de direcciones virtuales del proceso de llamada.|  
  
## <a name="remarks"></a>Comentarios  
 `IHostMemoryManager`también proporciona métodos para que CLR obtenga un puntero a través del cual se van a realizar solicitudes de memoria en el montón y para obtener el nivel de presión de memoria en el proceso, tal y como lo indica el host.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [IHostMalloc (Interfaz)](ihostmalloc-interface.md)
- [Interfaces de hospedaje](hosting-interfaces.md)
