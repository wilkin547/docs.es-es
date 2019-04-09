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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7a538f14e7dbf24a94343f364201e968bffa757f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59158930"
---
# <a name="icorruntimehostcreatedomainex-method"></a>ICorRuntimeHost::CreateDomainEx (Método)
Crea un dominio de aplicación. El llamador recibe un puntero de interfaz de tipo <xref:System._AppDomain>, a una instancia de tipo <xref:System.AppDomain?displayProperty=nameWithType>. Este método permite al llamador pasar una instancia de IAppDomainSetup para configurar características adicionales de devuelto <xref:System._AppDomain> instancia.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT CreateDomainEx (  
    [in] LPCWSTR     pwzFriendlyName,  
    [in] IUnknown*   pSetup,  
    [in] IUnknown*   pIdentityArray,  
    [out] IUnknown** pAppDomain  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pwzFriendlyName`  
 [in] Un parámetro opcional que se utiliza para asignar un nombre descriptivo para el dominio. Este nombre descriptivo puede mostrarse en las interfaces de usuario, como los depuradores para identificar el dominio.  
  
 `pSetup`  
 [in] Un puntero de interfaz opcional de tipo `IAppDomainSetup`, obtenida por una llamada a la [CreateDomainSetup](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainsetup-method.md) método.  
  
 `pIdentityArray`  
 [in] Una matriz opcional de punteros a `IIdentity` instancias que representan la evidencia asignada mediante la directiva de seguridad para establecer un conjunto de permisos. Un `IIdentity` puede obtenerse un objeto mediante una llamada a la [CreateEvidence](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md) método.  
  
 `pAppDomain`  
 [out] Un puntero de interfaz de tipo <xref:System._AppDomain> a una instancia de <xref:System.AppDomain?displayProperty=nameWithType> que puede utilizarse para controlar aún más el dominio.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|La operación fue correcta.|  
|S_FALSE|No se pudo completar la operación.|  
|E_FAIL|Se ha producido un error catastrófico desconocido. Si el método devuelve E_FAIL, common language runtime (CLR) ya no es utilizable en el proceso. Las llamadas subsiguientes a cualquier API de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
|HOST_E_CLRNOTAVAILABLE|El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.|  
  
## <a name="remarks"></a>Comentarios  
 `CreateDomainEx` amplía las capacidades de [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) permitiendo que el llamador pase un `IAppDomainSetup` instancia con valores de propiedad para configurar el dominio de aplicación.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.h  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versión de .NET framework:** 1.0, 1.1  
  
## <a name="see-also"></a>Vea también

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- <xref:System.IAppDomainSetup?displayProperty=nameWithType>
- [Método CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md)
- [ICorRuntimeHost (Interfaz)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
