---
title: EInitializeNewDomainFlags (Enumeración)
ms.date: 03/30/2017
api_name:
- EInitializeNewDomainFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EInitializeNewDomainFlags
helpviewer_keywords:
- EInitializeNewDomainFlags enumeration [.NET Framework hosting]
ms.assetid: 3a120ab2-f5ef-4c9b-8595-d3ed7247c342
ms.openlocfilehash: 3693285e13d0650f7662e2187471027cc4c40704
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129413"
---
# <a name="einitializenewdomainflags-enumeration"></a>EInitializeNewDomainFlags (Enumeración)
Permite al host proporcionar información sobre la inicialización de un dominio de aplicación en el tiempo de ejecución.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum {  
    eInitializeNewDomainFlags_None              = 0x0000,  
    eInitializeNewDomainFlags_NoSecurityChanges = 0x0002  
} EInitializeNewDomainFlags;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`eInitializeNewDomainFlags_None`|Sin marcas.|  
|`eInitializeNewDomainFlags_NoSecurityChanges`|Informa al Common Language Runtime (CLR) de que el host no realizará cambios en el estado de seguridad del dominio de aplicación en el método <xref:System.AppDomainManager.InitializeNewDomain%2A>.|  
  
## <a name="remarks"></a>Comentarios  
 El método [ICLRDomainManager:: setappdomainmanagertype (](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md) toma un parámetro de tipo `EInitializeNewDomainFlags`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones para hosts](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
- [SetAppDomainManagerType (método)](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md)
