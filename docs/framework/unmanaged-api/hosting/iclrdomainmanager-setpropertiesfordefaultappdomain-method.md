---
title: ICLRDomainManager::SetPropertiesForDefaultAppDomain (Método)
ms.date: 03/30/2017
api_name:
- ICLRDomainManager.SetPropertiesForDefaultAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDomainManager::SetPropertiesForDefaultAppDomain
helpviewer_keywords:
- ICLRDomainManager::SetPropertiesForDefaultAppDomain method [.NET Framework hosting]
- SetPropertiesForDefaultAppDomain method [.NET Framework hosting]
ms.assetid: 43e61c4b-c435-45ec-9ef6-c68403aa4200
ms.openlocfilehash: b5577d0444caf14fb47d9d7e2de60a8399378db7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702139"
---
# <a name="iclrdomainmanagersetpropertiesfordefaultappdomain-method"></a>ICLRDomainManager::SetPropertiesForDefaultAppDomain (Método)

Establece las propiedades que se usarán para inicializar el dominio de aplicación predeterminado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetPropertiesForDefaultAppDomain(  
    [in] DWORD nProperties,  
    [in] LPCWSTR *pwszPropertyNames,  
    [in] LPCWSTR *pwszPropertyValues  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `nProperties`  
 de Número de entradas en `pwszPropertyNames` y `pwszPropertyValues` .  
  
 `pwszPropertyNames`  
 de Una matriz de nombres de propiedad, o null si no hay propiedades. Actualmente, el único nombre de propiedad que reconoce este método es "PARTIAL_TRUST_VISIBLE_ASSEMBLIES".  
  
 `pwszPropertyValues`  
 de Una matriz de valores de propiedad o null si no hay propiedades.  
  
## <a name="return-value"></a>Valor devuelto  

 Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|El método se completó correctamente.|  
|HRESULT_FROM_WIN32 (ERROR_UNKNOWN_PROPERTY)|`pwszPropertyNames` incluye un nombre de propiedad que este método no reconoce.|  
  
## <a name="remarks"></a>Comentarios  

 El valor de propiedad para "PARTIAL_TRUST_VISIBLE_ASSEMBLIES" es una lista de ensamblados que tienen el <xref:System.Security.AllowPartiallyTrustedCallersAttribute> atributo condicional (APTCA) con la <xref:System.Security.PartialTrustVisibilityLevel.NotVisibleByDefault?displayProperty=nameWithType> marca, que se van a hacer visibles para los llamadores de confianza parcial en el dominio de aplicación predeterminado.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Metahost. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Hospedar aplicaciones de WPF](index.md)
- [ICLRDomainManager (Interfaz)](iclrdomainmanager-interface.md)
