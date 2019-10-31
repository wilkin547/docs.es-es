---
title: ICorRuntimeHost::CreateDomainEx (Método)
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CreateDomainEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CreateDomainEx
helpviewer_keywords:
- ICorRuntimeHost::CreateDomainEx method [.NET Framework hosting]
- CreateDomainEx method [.NET Framework hosting]
ms.assetid: 1bdde382-f8ba-4cc8-94b2-d1ac919c585e
topic_type:
- apiref
ms.openlocfilehash: a3a2d1827774ddedc00eb849f64256e3f425b3fa
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127711"
---
# <a name="icorruntimehostcreatedomainex-method"></a>ICorRuntimeHost::CreateDomainEx (Método)
Crea un dominio de aplicación. El autor de la llamada recibe un puntero de interfaz, de tipo <xref:System._AppDomain>, a una instancia de tipo <xref:System.AppDomain?displayProperty=nameWithType>. Este método permite al llamador pasar una instancia de IAppDomainSetup para configurar características adicionales de la instancia de <xref:System._AppDomain> devuelta.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT CreateDomainEx (  
    [in] LPCWSTR     pwzFriendlyName,  
    [in] IUnknown*   pSetup,  
    [in] IUnknown*   pIdentityArray,  
    [out] IUnknown** pAppDomain  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pwzFriendlyName`  
 de Parámetro opcional que se usa para proporcionar un nombre descriptivo al dominio. Este nombre descriptivo puede mostrarse en las interfaces de usuario como depuradores para identificar el dominio.  
  
 `pSetup`  
 de Un puntero de interfaz opcional de tipo `IAppDomainSetup`, obtenido mediante una llamada al método [ICorRuntimeHost:: CreateDomainSetup (](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainsetup-method.md) .  
  
 `pIdentityArray`  
 de Matriz opcional de punteros a `IIdentity` instancias que representan la evidencia asignada a través de la Directiva de seguridad para establecer un conjunto de permisos. Un objeto `IIdentity` se puede obtener llamando al método [createevidence (](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md) .  
  
 `pAppDomain`  
 enuncia Puntero de interfaz de tipo <xref:System._AppDomain> a una instancia de <xref:System.AppDomain?displayProperty=nameWithType> que se puede utilizar para controlar aún más el dominio.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|La operación se realizó correctamente.|  
|S_FALSE|No se pudo completar la operación.|  
|E_FAIL|Se produjo un error grave desconocido. Si un método devuelve E_FAIL, el Common Language Runtime (CLR) ya no se puede usar en el proceso. Las llamadas subsiguientes a cualquier API de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
|HOST_E_CLRNOTAVAILABLE|CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
  
## <a name="remarks"></a>Comentarios  
 `CreateDomainEx` extiende las capacidades de [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) permitiendo que el llamador pase una instancia de `IAppDomainSetup` con valores de propiedad para configurar el dominio de aplicación.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versión de .NET Framework:** 1,0, 1,1  
  
## <a name="see-also"></a>Vea también

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- <xref:System.IAppDomainSetup?displayProperty=nameWithType>
- [CreateDomain (método)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md)
- [ICorRuntimeHost (interfaz)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
