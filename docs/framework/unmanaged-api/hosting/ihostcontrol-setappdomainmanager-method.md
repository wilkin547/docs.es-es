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
ms.openlocfilehash: de264135450190fd028eb8cf12017d94cc65ffac
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134723"
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
 de Identificador numérico de la <xref:System.AppDomain>seleccionada.  
  
 `pUnkAppDomainManager`  
 de Puntero al objeto <xref:System.AppDomainManager> que el host implementa como `IUnknown`.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`SetAppDomainManager` devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Comentarios  
 El <xref:System.AppDomainManager> proporciona al host un mecanismo para arrancar en código administrado y controlar la creación y la configuración de cada <xref:System.AppDomain>. El <xref:System.AppDomainManager> se carga en cada <xref:System.AppDomain> cuando se crea ese <xref:System.AppDomain>. Si elige, CLR notifica al host que el dominio de aplicación se ha creado estableciendo el valor del parámetro `pUnkAppDomainManager`.  
  
 En su implementación del método `SetAppDomainManager`, el host puede establecer el nombre y el tipo del ensamblado para el administrador del dominio de aplicación.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.AppDomain>
- <xref:System.AppDomainManager>
- [IHostControl (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
