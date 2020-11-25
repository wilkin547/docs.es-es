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
ms.openlocfilehash: 2530c7fcd63f81b566d6623a533bd8e2af084047
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702165"
---
# <a name="ihostmalloc-interface"></a>IHostMalloc (Interfaz)

Proporciona métodos que permiten que el Common Language Runtime (CLR) solicite asignaciones concretas del montón a través del host.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Alloc (Método)](ihostmalloc-alloc-method.md)|Solicita que el host asigne la cantidad de memoria solicitada del montón.|  
|[Método DebugAlloc](ihostmalloc-debugalloc-method.md)|Solicita que el host asigne la cantidad de memoria solicitada del montón y, además, realiza un seguimiento del lugar en el que se asignó la memoria.|  
|[Método Free](ihostmalloc-free-method.md)|Libera la memoria asignada mediante el `Alloc` método.|  
  
## <a name="remarks"></a>Comentarios  

 CLR obtiene un puntero de interfaz a una `IHostMalloc` instancia llamando al método [IHostMemoryManager:: CreateMAlloc (](ihostmemorymanager-createmalloc-method.md) .  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IHostMemoryManager (Interfaz)](ihostmemorymanager-interface.md)
- [Interfaces de hospedaje](hosting-interfaces.md)
