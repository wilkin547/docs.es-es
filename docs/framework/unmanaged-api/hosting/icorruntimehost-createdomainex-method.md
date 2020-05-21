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
ms.openlocfilehash: 4e5856fbcda83c1dd30559c6f59f63495faea78d
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762349"
---
# <a name="icorruntimehostcreatedomainex-method"></a>ICorRuntimeHost::CreateDomainEx (Método)
Crea un dominio de aplicación. El autor de la llamada recibe un puntero de interfaz, de tipo <xref:System._AppDomain> , a una instancia de tipo <xref:System.AppDomain?displayProperty=nameWithType> . Este método permite al llamador pasar una instancia de IAppDomainSetup para configurar características adicionales de la instancia de devuelta <xref:System._AppDomain> .  
  
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
 de Un puntero de interfaz opcional de tipo `IAppDomainSetup` , obtenido mediante una llamada al método [ICorRuntimeHost:: CreateDomainSetup (](icorruntimehost-createdomainsetup-method.md) .  
  
 `pIdentityArray`  
 de Matriz opcional de punteros a `IIdentity` instancias que representan la evidencia asignada a través de la Directiva de seguridad para establecer un conjunto de permisos. Un `IIdentity` objeto se puede obtener llamando al método [createevidence (](icorruntimehost-createevidence-method.md) .  
  
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
 `CreateDomainEx`extiende las capacidades de [CreateDomain](icorruntimehost-createdomain-method.md) permitiendo que el llamador pase una `IAppDomainSetup` instancia con valores de propiedad para configurar el dominio de aplicación.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versión de .NET Framework:** 1,0, 1,1  
  
## <a name="see-also"></a>Consulte también:

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- <xref:System.IAppDomainSetup?displayProperty=nameWithType>
- [Método CreateDomain](icorruntimehost-createdomain-method.md)
- [ICorRuntimeHost (Interfaz)](icorruntimehost-interface.md)
