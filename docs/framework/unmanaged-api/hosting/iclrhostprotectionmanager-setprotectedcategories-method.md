---
description: 'Más información sobre: ICLRHostProtectionManager:: Setprotectedcategories ((método)'
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
ms.openlocfilehash: 9138c31ea1a2d9b7ebeaeac8ef5ef9305eabef8d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99637539"
---
# <a name="iclrhostprotectionmanagersetprotectedcategories-method"></a>ICLRHostProtectionManager::SetProtectedCategories (Método)

Especifica qué categorías de tipos administrados y miembros deben bloquearse para que no se ejecuten en código de confianza parcial.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetProtectedCategories (  
    [in] EApiCategories  categories  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `categories`  
 de Una combinación de valores de [EApiCategories](eapicategories-enumeration.md) , que indica en qué categorías de tipos y miembros administrados se debe bloquear la ejecución en código de confianza parcial.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`SetProtectedCategories` se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Después de que un método devuelve E_FAIL, CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Observaciones  

 Cada `EApiCategories` valor hace referencia a una lista de miembros y tipos administrados. La `EApiCategories` enumeración y el `SetProtectedCategories` método están directamente relacionados con la <xref:System.Security.Permissions.HostProtectionAttribute> clase administrada, que se usa para marcar los tipos administrados y los miembros que exponen las funciones correspondientes a las categorías descritas por `EApiCategories` . Para obtener más información, vea <xref:System.Security.Permissions.HostProtectionAttribute> y la <xref:System.Security.Permissions.HostProtectionResource> enumeración, que se corresponde directamente con `EApiCategories` .  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Security.Permissions.HostProtectionAttribute>
- <xref:System.Security.Permissions.HostProtectionResource>
- [EApiCategories (Enumeración)](eapicategories-enumeration.md)
- [ICLRControl (Interfaz)](iclrcontrol-interface.md)
- [ICLRHostProtectionManager (Interfaz)](iclrhostprotectionmanager-interface.md)
