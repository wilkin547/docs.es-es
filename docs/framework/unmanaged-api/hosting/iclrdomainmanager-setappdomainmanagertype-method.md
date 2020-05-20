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
ms.openlocfilehash: 89b3f9f248a445cc0568236d6a1df14269de4187
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615701"
---
# <a name="iclrdomainmanagersetappdomainmanagertype-method"></a>ICLRDomainManager::SetAppDomainManagerType (Método)
Especifica el tipo, derivado de la <xref:System.AppDomainManager?displayProperty=nameWithType> clase, del administrador del dominio de aplicación que se utilizará para inicializar el dominio de aplicación predeterminado.  
  
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
 de Combinación de valores de enumeración de [einitializenewdomainflags (](einitializenewdomainflags-enumeration.md) que proporcionan información sobre el administrador del dominio de aplicación.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|El método se completó correctamente.|  
|HOST_E_CLRNOTAVAILABLE|El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
  
## <a name="remarks"></a>Observaciones  
 Actualmente, el único valor definido para `dwInitializeDomainFlags` es `eInitializeNewDomainFlags_NoSecurityChanges` , que indica al Common Language Runtime (CLR) que el administrador del dominio de aplicación no modificará la configuración de seguridad durante la ejecución del <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> método. Esto permite que CLR optimice la carga de ensamblados que tienen el <xref:System.Security.AllowPartiallyTrustedCallersAttribute> atributo condicional (APTCA). Esto puede dar lugar a una mejora significativa en el tiempo de inicio si el cierre transitivo de este conjunto de ensamblados es grande.  
  
> [!IMPORTANT]
> Si el host especifica `eInitializeNewDomainFlags_NoSecurityChanges` para el administrador del dominio de aplicación, <xref:System.InvalidOperationException> se produce una excepción si se intenta modificar la seguridad del dominio de aplicación.  
  
 Llamar al método [ICLRControl:: setappdomainmanagertype (](iclrcontrol-setappdomainmanagertype-method.md)es equivalente a llamar a `ICLRDomainManager::SetAppDomainManagerType` con `eInitializeNewDomainFlags_None` .  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Metahost. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Consulta también

- [Hospedar aplicaciones de WPF](index.md)
- [ICLRDomainManager (Interfaz)](iclrdomainmanager-interface.md)
- [EInitializeNewDomainFlags (Enumeración)](einitializenewdomainflags-enumeration.md)
