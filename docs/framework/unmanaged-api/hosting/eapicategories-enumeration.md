---
title: EApiCategories (Enumeración)
ms.date: 03/30/2017
api_name:
- EApiCategories
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EApiCategories
helpviewer_keywords:
- EApiCategories enumeration [.NET Framework hosting]
ms.assetid: 3c4a8a5a-8a46-4ac9-947f-4959bc9d6ac6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 41513d9b6f98743bfad95e4d9606cfb4927369e6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67769789"
---
# <a name="eapicategories-enumeration"></a>EApiCategories (Enumeración)
Describe las categorías de funciones que puede bloquear el host que se ejecutan en el código de confianza parcial.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum {  
    eNoCategory               = 0,  
    eSynchronization          = 0x1,  
    eSharedState              = 0x2,  
    eExternalProcessMgmt      = 0x4,  
    eSelfAffectingProcessMgmt = 0x8,  
    eExternalThreading        = 0x10,  
    eSelfAffectingThreading   = 0x20,  
    eSecurityInfrastructure   = 0x40,  
    eUI                       = 0x80,  
    eMayLeakOnAbort           = 0x100,  
    eAll                      = 0x1ff  
} EHostProtectionCategories;  
```  
  
## <a name="members"></a>Miembros  
  
|Member|DESCRIPCIÓN|  
|------------|-----------------|  
|`eAll`|Especifica que todos los administrados de las clases y miembros que están cubiertos por otro `EApiCategories` campos podrá ejecutarse en el código de confianza parcial.|  
|`eExternalProcessMgmt`|Especifica que las clases administradas y los miembros que permiten la creación, manipulación y destrucción de procesos externos podrá ejecutarse en el código de confianza parcial.|  
|`eExternalThreading`|Especifica que las clases administradas y los miembros que permiten la creación, manipulación y destrucción de subprocesos externos podrá ejecutarse en el código de confianza parcial.|  
|`eMayLeakOnAbort`|Especifica que se bloquean los tipos administrados y miembros que pueden provocar pérdidas de memoria en la anulación se ejecuten en el código de confianza parcial.|  
|`eNoCategory`|Especifica que no hay categorías de código administrado se bloqueó su ejecución en código de confianza parcial.|  
|`eSecurityInfrastructure`|Especifica que debe bloquearse la infraestructura de seguridad de common language runtime (CLR) usando código de confianza parcial.|  
|`eSelfAffectingProcessMgmt`|Especifica que las clases administradas y miembros cuyas características pueden afectar al proceso hospedado podrá ejecutarse en el código de confianza parcial.|  
|`eSelfAffectingThreading`|Especifica que las clases administradas y miembros cuyas características pueden afectar a los subprocesos del proceso hospedado podrá ejecutarse en el código de confianza parcial.|  
|`eSharedState`|Especifica que las clases administradas y los miembros que exponen el estado compartido podrá ejecutarse en el código de confianza parcial.|  
|`eSynchronization`|Especifica que los miembros que permitir que el código de usuario mantener los bloqueos y las clases en tiempo de ejecución de lenguaje comunes podrá ejecutarse en el código de confianza parcial.|  
|`eUI`|Especifica que las clases administradas y los miembros que permiten o requieren la interacción humana podrá ejecutarse en el código de confianza parcial.|  
  
## <a name="remarks"></a>Comentarios  
 El [ICLRHostProtectionManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md) método toma un parámetro de tipo `EApiCategories`.  
  
 El `EApiCategories` enumeración y el `SetProtectedCategories` método están relacionados directamente a los recursos administrados <xref:System.Security.Permissions.HostProtectionAttribute?displayProperty=nameWithType> clase. Se usa la clase administrada con el <xref:System.Security.Permissions.HostProtectionResource?displayProperty=nameWithType> enumeración, cuyos valores se corresponden directamente con el `EApiCategories` valores para marcar los tipos administrados y miembros que exponen funciones correspondientes a las categorías descritas por `EApiCategories`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.h  
  
 **Biblioteca:** MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRHostProtectionManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
- [Enumeraciones para hosts](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
