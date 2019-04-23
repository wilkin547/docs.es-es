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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f2a7a29ef1dc85c2ad554995286e5137fcb104be
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59136419"
---
# <a name="ihostmalloc-interface"></a>IHostMalloc (Interfaz)
Proporciona métodos que permiten a common language runtime (CLR) para solicitar asignaciones concretas del montón a través del host.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Alloc (método)](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-alloc-method.md)|Solicita que el host de asignar la cantidad de memoria del montón.|  
|[DebugAlloc (método)](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-debugalloc-method.md)|Solicita que el host de asignar la cantidad de memoria del montón y además realizar un seguimiento de dónde se ha asignado la memoria.|  
|[Free (método)](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-free-method.md)|Libera la memoria que se asignó utilizando el `Alloc` método.|  
  
## <a name="remarks"></a>Comentarios  
 CLR Obtiene un puntero de interfaz a un `IHostMalloc` instancia mediante una llamada a la [IHostMemoryManager:: CreateMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md) método.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.h  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IHostMemoryManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
