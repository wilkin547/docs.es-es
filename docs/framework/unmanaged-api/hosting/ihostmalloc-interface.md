---
description: 'Más información acerca de: IHostMalloc (interfaz)'
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
ms.openlocfilehash: cd04a0f71fd429ea10b9edcce02806f4afa57148
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99708182"
---
# <a name="ihostmalloc-interface"></a>IHostMalloc (Interfaz)

Proporciona métodos que permiten que el Common Language Runtime (CLR) solicite asignaciones concretas del montón a través del host.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Alloc (Método)](ihostmalloc-alloc-method.md)|Solicita que el host asigne la cantidad de memoria solicitada del montón.|  
|[Método DebugAlloc](ihostmalloc-debugalloc-method.md)|Solicita que el host asigne la cantidad de memoria solicitada del montón y, además, realiza un seguimiento del lugar en el que se asignó la memoria.|  
|[Método Free](ihostmalloc-free-method.md)|Libera la memoria asignada mediante el `Alloc` método.|  
  
## <a name="remarks"></a>Observaciones  

 CLR obtiene un puntero de interfaz a una `IHostMalloc` instancia llamando al método [IHostMemoryManager:: CreateMAlloc (](ihostmemorymanager-createmalloc-method.md) .  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IHostMemoryManager (Interfaz)](ihostmemorymanager-interface.md)
- [Interfaces de hospedaje](hosting-interfaces.md)
