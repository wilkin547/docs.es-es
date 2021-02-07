---
description: 'Más información acerca de: IHostAssemblyManager (interfaz)'
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
ms.openlocfilehash: 649771f79e65039adfa8c0ade9f167b1679bb917
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99709001"
---
# <a name="ihostassemblymanager-interface"></a>IHostAssemblyManager (Interfaz)

Proporciona métodos que permiten a un host especificar conjuntos de ensamblados que deben ser cargados por el Common Language Runtime (CLR) o por el host.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método GetAssemblyStore](ihostassemblymanager-getassemblystore-method.md)|Obtiene un puntero de interfaz a un [IHostAssemblyStore](ihostassemblystore-interface.md) que representa la lista de ensamblados cargados por el host.|  
|[Método GetNonHostStoreAssemblies](ihostassemblymanager-getnonhoststoreassemblies-method.md)|Obtiene un puntero de interfaz a un [ICLRAssemblyReferenceList](iclrassemblyreferencelist-interface.md) que representa la lista de ensamblados que el host espera que el CLR cargue.|  
  
## <a name="remarks"></a>Observaciones  

 No es necesario que el host implemente `IHostAssemblyManager` o `IHostAssemblyStore` . Si el host implementa `IHostAssemblyManager` , también debe implementar `IHostAssemblyStore` .  
  
 El tiempo de ejecución consulta para un llamando `IHostAssemblyManager` a [IHostControl:: GetHostManager (](ihostcontrol-gethostmanager-method.md) al inicializar con una `IID` de IID_IHostAssemblyManager.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRAssemblyReferenceList (Interfaz)](iclrassemblyreferencelist-interface.md)
- [IHostAssemblyStore (Interfaz)](ihostassemblystore-interface.md)
- [IHostControl (Interfaz)](ihostcontrol-interface.md)
- [Interfaces de hospedaje](hosting-interfaces.md)
