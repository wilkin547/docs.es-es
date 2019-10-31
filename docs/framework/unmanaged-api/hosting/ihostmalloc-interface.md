---
title: IHostMalloc (Interfaz)
ms.date: 03/30/2017
api_name:
- IHostMAlloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMAlloc
helpviewer_keywords:
- IHostMAlloc interface [.NET Framework hosting]
ms.assetid: e3c6643b-6fc7-4a99-959d-4b7b4e63fdee
topic_type:
- apiref
ms.openlocfilehash: abc6cca185b318be016f92ac8c97d21f7af5940a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136777"
---
# <a name="ihostmalloc-interface"></a>IHostMalloc (Interfaz)
Proporciona métodos que permiten que el Common Language Runtime (CLR) solicite asignaciones concretas del montón a través del host.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Alloc (método)](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-alloc-method.md)|Solicita que el host asigne la cantidad de memoria solicitada del montón.|  
|[DebugAlloc (método)](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-debugalloc-method.md)|Solicita que el host asigne la cantidad de memoria solicitada del montón y, además, realiza un seguimiento del lugar en el que se asignó la memoria.|  
|[Free (método)](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-free-method.md)|Libera la memoria asignada mediante el método `Alloc`.|  
  
## <a name="remarks"></a>Comentarios  
 CLR obtiene un puntero de interfaz a una instancia de `IHostMalloc` llamando al método [IHostMemoryManager:: CreateMAlloc (](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) .  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IHostMemoryManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
