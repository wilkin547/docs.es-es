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
ms.openlocfilehash: 7ff10f84d8d270d31c5d560fb3c9bd3c81cf3e24
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616234"
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
|`eInitializeNewDomainFlags_NoSecurityChanges`|Informa al Common Language Runtime (CLR) de que el host no realizará cambios en el estado de seguridad del dominio de aplicación en el <xref:System.AppDomainManager.InitializeNewDomain%2A> método.|  
  
## <a name="remarks"></a>Observaciones  
 El método [ICLRDomainManager:: setappdomainmanagertype (](iclrdomainmanager-setappdomainmanagertype-method.md) toma un parámetro de tipo `EInitializeNewDomainFlags` .  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Consulta también

- [Enumeraciones para hosts](hosting-enumerations.md)
- [SetAppDomainManagerType (Método)](iclrdomainmanager-setappdomainmanagertype-method.md)
