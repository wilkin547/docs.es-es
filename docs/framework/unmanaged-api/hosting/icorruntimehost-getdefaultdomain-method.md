---
title: ICorRuntimeHost::GetDefaultDomain (Método)
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.GetDefaultDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::GetDefaultDomain
helpviewer_keywords:
- ICorRuntimeHost::GetDefaultDomain method [.NET Framework hosting]
- GetDefaultDomain method [.NET Framework hosting]
ms.assetid: 5e17a6fc-f335-4aae-9bb0-c3e1271a9426
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f2351fbb26a38f408d330db3f7600120bd57d6e1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33437887"
---
# <a name="icorruntimehostgetdefaultdomain-method"></a>ICorRuntimeHost::GetDefaultDomain (Método)
Obtiene un puntero de interfaz de tipo <xref:System._AppDomain?displayProperty=nameWithType> que representa el dominio predeterminado para el proceso actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetDefaultDomain (  
    [out] IUnknown** pAppDomain  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pAppDomain`  
 [out] Un puntero de interfaz de tipo <xref:System._AppDomain?displayProperty=nameWithType> a la <xref:System.AppDomain> instancia que representa el dominio de aplicación predeterminado para el proceso.  
  
 Este puntero es de tipo `IUnknown`, por lo que los llamadores generalmente deben llamar a `QueryInterface` para obtener un puntero de interfaz de tipo <xref:System._AppDomain?displayProperty=nameWithType>.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|La operación fue correcta.|  
|S_FALSE|No se pudo completar la operación.|  
|E_FAIL|Se ha producido un error catastrófico desconocido. Si el método devuelve E_FAIL, common language runtime (CLR) ya no es utilizable en el proceso. Las llamadas subsiguientes a cualquier API de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
|HOST_E_CLRNOTAVAILABLE|El CLR no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE.h  
  
 **Biblioteca:** incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET framework:** 1.0, 1.1  
  
## <a name="see-also"></a>Vea también  
 <xref:System._AppDomain>  
 <xref:System.AppDomain>  
 [ICorRuntimeHost (interfaz)](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
