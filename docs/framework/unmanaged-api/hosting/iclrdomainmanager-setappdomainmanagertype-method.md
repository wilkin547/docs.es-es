---
title: ICLRDomainManager::SetAppDomainManagerType (Método)
ms.date: 03/30/2017
api_name:
- ICLRDomainManager.SetAppDomainManagerType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDomainManager::SetAppDomainManagerType
helpviewer_keywords:
- SetAppDomainManagerType method, ICLRDomainManager interface [.NET Framework hosting]
- ICLRDomainManager::SetAppDomainManagerType method [.NET Framework hosting]
ms.assetid: ee91abb0-cb74-41dd-927b-e117fb8ffdf4
ms.openlocfilehash: 5c61e2e1208cec0bda1492964a8d02bd71f5a1c6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129331"
---
# <a name="iclrdomainmanagersetappdomainmanagertype-method"></a>ICLRDomainManager::SetAppDomainManagerType (Método)
Especifica el tipo, derivado de la clase <xref:System.AppDomainManager?displayProperty=nameWithType>, del administrador del dominio de aplicación que se utilizará para inicializar el dominio de aplicación predeterminado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetAppDomainManagerType(  
    [in] LPCWSTR wszAppDomainManagerAssembly,  
    [in] LPCWSTR wszAppDomainManagerType,  
    [in] EInitializeNewDomainFlags dwInitializeDomainFlags  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `wszAppDomainManagerAssembly`  
 de El nombre para mostrar del ensamblado que contiene el tipo de administrador de dominio de aplicación; por ejemplo: "AdMgrExample, version = 1.0.0.0, Culture = neutral, PublicKeyToken = 6856bccf150f00b3".  
  
 `wszAppDomainManagerType`  
 de El nombre de tipo del administrador del dominio de aplicación, incluido el espacio de nombres.  
  
 `dwInitializeDomainFlags`  
 de Combinación de valores de enumeración de [einitializenewdomainflags (](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md) que proporcionan información sobre el administrador del dominio de aplicación.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|El método se completó correctamente.|  
|HOST_E_CLRNOTAVAILABLE|El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
  
## <a name="remarks"></a>Comentarios  
 Actualmente, el único valor definido para `dwInitializeDomainFlags` es `eInitializeNewDomainFlags_NoSecurityChanges`, que indica al Common Language Runtime (CLR) que el administrador del dominio de aplicación no modificará la configuración de seguridad durante la ejecución del método de <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType>. Esto permite que CLR optimice la carga de ensamblados que tienen el atributo de <xref:System.Security.AllowPartiallyTrustedCallersAttribute> condicional (APTCA). Esto puede dar lugar a una mejora significativa en el tiempo de inicio si el cierre transitivo de este conjunto de ensamblados es grande.  
  
> [!IMPORTANT]
> Si el host especifica `eInitializeNewDomainFlags_NoSecurityChanges` para el administrador del dominio de aplicación, se produce una <xref:System.InvalidOperationException> si se intenta modificar la seguridad del dominio de aplicación.  
  
 Llamar al método [ICLRControl:: setappdomainmanagertype (](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)es equivalente a llamar a `ICLRDomainManager::SetAppDomainManagerType` con `eInitializeNewDomainFlags_None`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Metahost. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Hospedar aplicaciones de WPF](../../../../docs/framework/unmanaged-api/hosting/index.md)
- [ICLRDomainManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-interface.md)
- [EInitializeNewDomainFlags (enumeración)](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md)
