---
title: IHostControl::SetAppDomainManager (Método)
ms.date: 03/30/2017
api_name:
- IHostControl.SetAppDomainManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostControl::SetAppDomainManager
helpviewer_keywords:
- IHostControl::SetAppDomainManager method [.NET Framework hosting]
- SetAppDomainManager method [.NET Framework hosting]
ms.assetid: 6562bbe7-0d67-4c50-a958-3a18cf680375
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 94deb4eaeeec2400aebf397d391ce4b67c16989e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67763888"
---
# <a name="ihostcontrolsetappdomainmanager-method"></a>IHostControl::SetAppDomainManager (Método)
Notifica al host que se ha creado un dominio de aplicación.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetAppDomainManager (  
    [in] DWORD     dwAppDomainID,  
    [in] IUnknown* pUnkAppDomainManager  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `dwAppDomainID`  
 [in] El identificador numérico del seleccionado <xref:System.AppDomain>.  
  
 `pUnkAppDomainManager`  
 [in] Un puntero a la <xref:System.AppDomainManager> objeto que implementa el host como `IUnknown`.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|DESCRIPCIÓN|  
|-------------|-----------------|  
|S_OK|`SetAppDomainManager` se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|La llamada ha agotado el tiempo de espera.|  
|HOST_E_NOT_OWNER|El llamador no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.|  
|E_FAIL|Se ha producido un error irrecuperable desconocido. Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso. Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Comentarios  
 El <xref:System.AppDomainManager> proporciona el host con un mecanismo para arrancar en código administrado y controlar la creación y configuración de cada <xref:System.AppDomain>. El <xref:System.AppDomainManager> se carga en cada uno de ellos <xref:System.AppDomain> cuando que <xref:System.AppDomain> se crea. Si lo elige, CLR notifica al host que se ha creado el dominio de aplicación estableciendo el valor de la `pUnkAppDomainManager` parámetro.  
  
 En su implementación de la `SetAppDomainManager` método, el host puede establecer el nombre de ensamblado y tipo para el Administrador de dominio de aplicación.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.h  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.AppDomain>
- <xref:System.AppDomainManager>
- [IHostControl (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
