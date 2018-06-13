---
title: ICorRuntimeHost::CreateEvidence (Método)
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CreateEvidence
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CreateEvidence
helpviewer_keywords:
- CreateEvidence method [.NET Framework hosting]
- ICorRuntimeHost::CreateEvidence method [.NET Framework hosting]
ms.assetid: e235ea80-b84c-4442-a4c3-fc96c25a8eb9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a06d57348cfbdfb8bb57580a48e54e298e27e166
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33438199"
---
# <a name="icorruntimehostcreateevidence-method"></a>ICorRuntimeHost::CreateEvidence (Método)
Obtiene un puntero de interfaz de tipo <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>, que permite al host crear la evidencia de seguridad que se pasarán a la [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) o [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) método.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT CreateEvidence (  
    [out] IUnknown** pEvidence  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pEvidence`  
 [out] Un puntero de interfaz a un <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType> instancia utilizada para crear la evidencia de seguridad. Este puntero es de tipo `IUnknown`, por lo que los llamadores normalmente deben llamar a `QueryInterface` en esta interfaz para obtener un puntero a un <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|La operación fue correcta.|  
|S_FALSE|No se pudo completar la operación.|  
|E_FAIL|Se ha producido un error catastrófico desconocido. Si el método devuelve E_FAIL, common language runtime (CLR) ya no es utilizable en el proceso. Las llamadas subsiguientes a cualquier API de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
|HOST_E_CLRNOTAVAILABLE|El CLR no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.|  
  
## <a name="remarks"></a>Comentarios  
 Este método devuelve una colección vacía que no se pueden rellenar desde código nativo. Debe utilizar el <xref:System.Security.Policy.Evidence> método en su lugar.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE.h  
  
 **Biblioteca:** incluye como recurso en MSCorEE.dll  
  
 **Versión de .NET framework:** 1.0, 1.1  
  
## <a name="see-also"></a>Vea también  
 <xref:System._AppDomain>  
 <xref:System.AppDomain>  
 [ICorRuntimeHost (interfaz)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
