---
title: IHostMalloc (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e1690f5fe8f1417e6547ed94db8c71f079ebf5e6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ihostmalloc-interface"></a>IHostMalloc (Interfaz)
Proporciona métodos que permiten a common language runtime (CLR) para solicitar asignaciones concretas del montón a través del host.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Alloc (método)](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-alloc-method.md)|Solicita que el host asigne la cantidad de memoria solicitada del montón.|  
|[DebugAlloc (método)](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-debugalloc-method.md)|Solicita que el host de asignar la cantidad de memoria solicitada del montón y además realizar un seguimiento de dónde se ha asignado la memoria.|  
|[Free (método)](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-free-method.md)|Libera la memoria que se asignó utilizando el `Alloc` método.|  
  
## <a name="remarks"></a>Comentarios  
 CLR Obtiene un puntero de interfaz a una `IHostMalloc` instancia mediante una llamada a la [IHostMemoryManager:: CreateMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) método.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE.h  
  
 **Biblioteca:** incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [IHostMemoryManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
