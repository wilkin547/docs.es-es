---
title: EContextType (Enumeración)
ms.date: 03/30/2017
api_name:
- EContextType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EContextType
helpviewer_keywords:
- EContextType enumeration [.NET Framework hosting]
ms.assetid: 92b926a9-b87e-408a-9036-df7b752c9492
topic_type:
- apiref
ms.openlocfilehash: ceb68410e808bf7843149e3f05a39c7a98d0c000
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616299"
---
# <a name="econtexttype-enumeration"></a>EContextType (Enumeración)
Describe el contexto de seguridad del subproceso que se está ejecutando actualmente.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum {  
    eCurrentContext    = 0x00,  
    eRestrictedContext = 0x01  
} EContextType;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`eCurrentContext`|Indica el contexto del subproceso actual en el momento en que el Common Language Runtime (CLR) llama al método [IHostSecurityManager:: GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md) o el contexto solicitado por CLR en una llamada al método [IHostSecurityManager:: SetSecurityContext](ihostsecuritymanager-setsecuritycontext-method.md) .|  
|`eRestrictedContext`|Indica un contexto sobre el que el host tiene privilegios más bajos, como el recolector de elementos no utilizados, o los constructores de clase o módulo.|  
  
## <a name="remarks"></a>Observaciones  
 CLR proporciona uno de los `EContextType` valores como un valor de parámetro en las llamadas a `IHostSecurityManager::GetSecurityContext` los `IHostSecurityManager::SetSecurityContext` métodos y.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulta también

- [IHostSecurityContext (Interfaz)](ihostsecuritycontext-interface.md)
- [IHostSecurityManager (Interfaz)](ihostsecuritymanager-interface.md)
- [Enumeraciones para hosts](hosting-enumerations.md)
