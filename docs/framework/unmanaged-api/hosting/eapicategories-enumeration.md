---
title: "EApiCategories (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: EApiCategories
api_location: mscoree.dll
api_type: COM
f1_keywords: EApiCategories
helpviewer_keywords: EApiCategories enumeration [.NET Framework hosting]
ms.assetid: 3c4a8a5a-8a46-4ac9-947f-4959bc9d6ac6
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: eaff0133020fe84e58f8a130bffc8ddc2a55a19d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="eapicategories-enumeration"></a>EApiCategories (Enumeración)
Describe las categorías de funciones cuya ejecución en código de confianza parcial puede bloquear el host.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
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
  
|Miembro|Descripción|  
|------------|-----------------|  
|`eAll`|Especifica que todas las clases administran y los miembros que están cubiertos por otro `EApiCategories` campos podrá ejecutarse en código de confianza parcial.|  
|`eExternalProcessMgmt`|Especifica que debe bloquearse la ejecución en el código de confianza parcial de las clases administradas y miembros que permiten la creación, manipulación y destrucción de procesos externos.|  
|`eExternalThreading`|Especifica que debe bloquearse la ejecución en el código de confianza parcial de las clases administradas y los miembros que permiten la creación, manipulación y destrucción de subprocesos externos.|  
|`eMayLeakOnAbort`|Especifica que debe bloquearse la ejecución en el código de confianza parcial de tipos administrados y miembros que pueden provocar pérdidas de memoria en la anulación.|  
|`eNoCategory`|Especifica que no hay categorías de código administrado se bloqueó su ejecución en código de confianza parcial.|  
|`eSecurityInfrastructure`|Especifica que la infraestructura de seguridad de common language runtime (CLR) se bloquee sean usadas por código de confianza parcial.|  
|`eSelfAffectingProcessMgmt`|Especifica que debe bloquearse la ejecución en el código de confianza parcial de las clases administradas y los miembros cuyas funciones pueden afectar al proceso hospedado.|  
|`eSelfAffectingThreading`|Especifica que debe bloquearse la ejecución en el código de confianza parcial de las clases administradas y los miembros cuyas funciones pueden afectar a subprocesos del proceso hospedado.|  
|`eSharedState`|Especifica que debe bloquearse la ejecución en el código de confianza parcial de las clases administradas y los miembros que exponen el estado compartido.|  
|`eSynchronization`|Especifica que las clases en tiempo de ejecución de idioma y miembros que permitir que el código de usuario se mantienen bloqueos comunes podrá ejecutarse en código de confianza parcial.|  
|`eUI`|Especifica que debe bloquearse la ejecución en el código de confianza parcial de las clases administradas y los miembros que permiten o requieren interacción humana.|  
  
## <a name="remarks"></a>Comentarios  
 El [ICLRHostProtectionManager:: SetProtectedCategories](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md) método toma un parámetro de tipo `EApiCategories`.  
  
 El `EApiCategories` enumeración y el `SetProtectedCategories` método están directamente relacionados a los recursos administrados <xref:System.Security.Permissions.HostProtectionAttribute?displayProperty=nameWithType> clase. Se utiliza la clase administrada con el <xref:System.Security.Permissions.HostProtectionResource?displayProperty=nameWithType> enumeración, cuyos valores se corresponden directamente a la `EApiCategories` valores, para marcar tipos administrados y miembros que exponen funciones correspondientes a las categorías descritas por `EApiCategories`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE.h  
  
 **Biblioteca:** MSCorEE.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICLRHostProtectionManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)  
 [Enumeraciones para hosts](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
