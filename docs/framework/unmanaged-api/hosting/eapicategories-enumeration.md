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
ms.openlocfilehash: 0fd9409a5157e1013365c94f01631f130a76f54b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131213"
---
# <a name="eapicategories-enumeration"></a>EApiCategories (Enumeración)
Describe las categorías de funciones de las que el host puede bloquear la ejecución en código de confianza parcial.  
  
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
  
|Miembro|Descripción|  
|------------|-----------------|  
|`eAll`|Especifica que se bloquee la ejecución de todas las clases y miembros administrados que están incluidos en otros campos de `EApiCategories` en código de confianza parcial.|  
|`eExternalProcessMgmt`|Especifica que se bloquee la ejecución de las clases y los miembros administrados que permiten la creación, manipulación y destrucción de procesos externos en código de confianza parcial.|  
|`eExternalThreading`|Especifica que las clases administradas y los miembros que permiten la creación, manipulación y destrucción de subprocesos externos no se pueden ejecutar en código de confianza parcial.|  
|`eMayLeakOnAbort`|Especifica que los tipos y miembros administrados que podrían perder memoria al anularse no se ejecuten en código de confianza parcial.|  
|`eNoCategory`|Especifica que no se bloquee ninguna categoría de código administrado en código de confianza parcial.|  
|`eSecurityInfrastructure`|Especifica que no se puede usar la infraestructura de seguridad de Common Language Runtime (CLR) en el código de confianza parcial.|  
|`eSelfAffectingProcessMgmt`|Especifica que las clases administradas y los miembros cuyas funciones pueden afectar al proceso hospedado no pueden ejecutarse en código de confianza parcial.|  
|`eSelfAffectingThreading`|Especifica que las clases administradas y los miembros cuyas funciones pueden afectar a los subprocesos del proceso hospedado no pueden ejecutarse en código de confianza parcial.|  
|`eSharedState`|Especifica que se bloquee la ejecución de las clases administradas y los miembros que exponen el estado compartido en código de confianza parcial.|  
|`eSynchronization`|Especifica que Common Language Runtime clases y miembros que permiten que el código de usuario mantenga bloqueos no se ejecuten en código de confianza parcial.|  
|`eUI`|Especifica que las clases administradas y los miembros que permiten o requieren la interacción humana no se pueden ejecutar en código de confianza parcial.|  
  
## <a name="remarks"></a>Comentarios  
 El método [ICLRHostProtectionManager:: setprotectedcategories (](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md) toma un parámetro de tipo `EApiCategories`.  
  
 La enumeración `EApiCategories` y el método `SetProtectedCategories` se relacionan directamente con la clase <xref:System.Security.Permissions.HostProtectionAttribute?displayProperty=nameWithType> administrada. La clase administrada se usa con la enumeración <xref:System.Security.Permissions.HostProtectionResource?displayProperty=nameWithType>, cuyos valores se corresponden directamente con los valores `EApiCategories`, para marcar los tipos administrados y los miembros que exponen las funciones correspondientes a las categorías descritas por `EApiCategories`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRHostProtectionManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
- [Enumeraciones para hosts](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
