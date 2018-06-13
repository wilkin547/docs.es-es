---
title: ICLRHostProtectionManager::SetProtectedCategories (Método)
ms.date: 03/30/2017
api_name:
- ICLRHostProtectionManager.SetProtectedCategories
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostProtectionManager::SetProtectedCategories
helpviewer_keywords:
- SetProtectedCategories method [.NET Framework hosting]
- ICLRHostProtectionManager::SetProtectedCategories method [.NET Framework hosting]
ms.assetid: fa21dc7b-5da7-440b-b59e-9180e5181f9d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c6c93566d0909f1dbef46862760d47ede478d51a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434543"
---
# <a name="iclrhostprotectionmanagersetprotectedcategories-method"></a>ICLRHostProtectionManager::SetProtectedCategories (Método)
Especifica qué categorías de tipos y miembros administrados deben bloquearse de ejecución en el código de confianza parcial.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT SetProtectedCategories (  
    [in] EApiCategories  categories  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `categories`  
 [in] Una combinación de [EApiCategories](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md) valores, que indica qué categorías de tipos y miembros administrados deben bloquearse de ejecución en el código de confianza parcial.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`SetProtectedCategories` se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|La llamada agotó el tiempo de espera.|  
|HOST_E_NOT_OWNER|El llamador no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.|  
|E_FAIL|Se ha producido un error catastrófico desconocido. Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso. Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Comentarios  
 Cada `EApiCategories` valor hace referencia a una lista de tipos y miembros administrados. El `EApiCategories` enumeración y el `SetProtectedCategories` método están directamente relacionados a los recursos administrados <xref:System.Security.Permissions.HostProtectionAttribute> (clase), que se utiliza para marcar tipos administrados y miembros que exponen funciones correspondientes a las categorías descritas por `EApiCategories`. Para obtener más información, consulte <xref:System.Security.Permissions.HostProtectionAttribute> y <xref:System.Security.Permissions.HostProtectionResource> enumeración, que se corresponde directamente con `EApiCategories`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE.h  
  
 **Biblioteca:** incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Security.Permissions.HostProtectionAttribute>  
 <xref:System.Security.Permissions.HostProtectionResource>  
 [EApiCategories (enumeración)](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md)  
 [ICLRControl (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [ICLRHostProtectionManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
