---
title: IHostAssemblyManager (Interfaz)
ms.date: 03/30/2017
api_name:
- IHostAssemblyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyManager
helpviewer_keywords:
- IHostAssemblyManager interface [.NET Framework hosting]
ms.assetid: dfec05bb-3cd7-4bd5-b396-a4f097c3a636
topic_type:
- apiref
ms.openlocfilehash: d9feeaf5f85d6f84a13e74a893b82c97fdaf023c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124509"
---
# <a name="ihostassemblymanager-interface"></a>IHostAssemblyManager (Interfaz)
Proporciona métodos que permiten a un host especificar conjuntos de ensamblados que deben ser cargados por el Common Language Runtime (CLR) o por el host.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetAssemblyStore (método)](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getassemblystore-method.md)|Obtiene un puntero de interfaz a un [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) que representa la lista de ensamblados cargados por el host.|  
|[GetNonHostStoreAssemblies (método)](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md)|Obtiene un puntero de interfaz a un [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) que representa la lista de ensamblados que el host espera que el CLR cargue.|  
  
## <a name="remarks"></a>Comentarios  
 No es necesario que el host implemente `IHostAssemblyManager` o `IHostAssemblyStore`. Si el host implementa `IHostAssemblyManager`, también debe implementar `IHostAssemblyStore`.  
  
 El tiempo de ejecución consulta una `IHostAssemblyManager` llamando a [IHostControl:: GetHostManager (](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) al inicializar con una `IID` de IID_IHostAssemblyManager.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRAssemblyReferenceList (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [IHostAssemblyStore (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
- [IHostControl (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
- [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
