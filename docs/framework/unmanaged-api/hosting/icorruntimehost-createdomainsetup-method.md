---
title: ICorRuntimeHost::CreateDomainSetup (Método)
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CreateDomainSetup
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CreateDomainSetup
helpviewer_keywords:
- CreateDomainSetup method [.NET Framework hosting]
- ICorRuntimeHost::CreateDomainSetup method [.NET Framework hosting]
ms.assetid: c21dab60-fb65-47d9-8a94-7fd47ca53b48
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 88f5de9882f8a029769d0ccbdac21aec541582a4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59157370"
---
# <a name="icorruntimehostcreatedomainsetup-method"></a>ICorRuntimeHost::CreateDomainSetup (Método)
Obtiene un puntero de interfaz de tipo IAppDomainSetup a un <xref:System.AppDomainSetup?displayProperty=nameWithType> instancia. `IAppDomainSetup` Proporciona métodos para configurar aspectos de un dominio de aplicación antes de crearlo.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT CreateDomainSetup (  
    [out] IUnknown** pAppDomainSetup  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pAppDomainSetup`  
 [out] Un puntero de interfaz a un <xref:System.AppDomainSetup?displayProperty=nameWithType> instancia. Este parámetro es de tipo `IUnknown`, por lo que generalmente deberían llamar los llamadores `QueryInterface` en este puntero para obtener un puntero de interfaz de tipo `IAppDomainSetup`.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|La operación fue correcta.|  
|S_FALSE|No se pudo completar la operación.|  
|E_FAIL|Se ha producido un error catastrófico desconocido. Si el método devuelve E_FAIL, common language runtime (CLR) ya no es utilizable en el proceso. Las llamadas subsiguientes a cualquier API de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
|HOST_E_CLRNOTAVAILABLE|El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.|  
  
## <a name="remarks"></a>Comentarios  
 El puntero devuelto por este método normalmente se pasa como parámetro a la [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) método.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.h  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versión de .NET framework:** 1.0, 1.1  
  
## <a name="see-also"></a>Vea también

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- <xref:System.AppDomainSetup>
- <xref:System.IAppDomainSetup?displayProperty=nameWithType>
- [ICorRuntimeHost (Interfaz)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
