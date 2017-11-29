---
title: "ICLRMetaHostPolicy::GetRequestedRuntime (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRMetaHostPolicy.GetRequestedRuntime
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRMetaHostPolicy::GetRequestedRuntime
helpviewer_keywords:
- GetRequestedRuntime method [.NET Framework hosting]
- ICLRMetaHostPolicy::GetRequestedRuntime method [.NET Framework hosting]
ms.assetid: 59ec1832-9cc1-4b5c-983d-03407e51de56
topic_type: apiref
caps.latest.revision: "19"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 57e5efc604568aea0a6edef5cc57f83fb99eb561
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="iclrmetahostpolicygetrequestedruntime-method"></a>ICLRMetaHostPolicy::GetRequestedRuntime (Método)
Proporciona una interfaz a una versión preferida de Common Language Runtime (CLR) basándose en una directiva de hospedaje, un ensamblado administrado, una cadena de versión y una secuencia de configuración. Este método realmente no carga ni activa el CLR, pero simplemente devuelve el [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaz que representa el resultado de la directiva. Este método reemplaza a la [GetRequestedRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md), [GetRequestedRuntimeVersion](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md), [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md), [CorBindToRuntimeByCfg](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md), y [GetCORRequiredVersion](../../../../docs/framework/unmanaged-api/hosting/getcorrequiredversion-function.md) métodos.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetRequestedRuntime(  
    [in]  METAHOST_POLICY_FLAGS dwPolicyFlags,  
    [in]  LPCWSTR pwzBinary,  
    [in]  IStream *pCfgStream,  
    [in, out, size_is(*pcchVersion)] LPWSTR pwzVersion,  
    [in, out]  DWORD *pcchVersion,  
    [out, size_is(*pcchImageVersion)] LPWSTR pwzImageVersion,  
    [in, out]  DWORD *pcchImageVersion,  
    [out] DWORD *pdwConfigFlags,  
    [in]  REFIID  riid  
    [out, iid_is(riid), retval] LPVOID *ppRuntime);  
```  
  
#### <a name="parameters"></a>Parámetros  
  
|Name|Descripción|  
|----------|-----------------|  
|`dwPolicyFlags`|[in] Obligatorio. Especifica un miembro de la [METAHOST_POLICY_FLAGS](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md) enumeración, que representa una directiva de enlace y el número indefinido de modificadores. La única directiva que está actualmente disponible es [METAHOST_POLICY_HIGHCOMPAT](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md).<br /><br /> Incluyen modificadores [METAHOST_POLICY_EMULATE_EXE_LAUNCH](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md), [METAHOST_POLICY_APPLY_UPGRADE_POLICY](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md), [METAHOST_POLICY_SHOW_ERROR_DIALOG](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md), [METAHOST_POLICY_USE_PROCESS_IMAGE_PATH](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md), y [METAHOST_POLICY_ENSURE_SKU_SUPPORTED](../../../../docs/framework/unmanaged-api/hosting/metahost-policy-flags-enumeration.md).|  
|`pwzBinary`|[in] Opcional. Especifica la ruta de acceso del archivo del ensamblado.|  
|`pCfgStream`|[in] Opcional. Especifica el archivo de configuración como un <xref:System.Runtime.InteropServices.ComTypes.IStream?displayProperty=nameWithType>.|  
|`pwzVersion`|[in, out] Opcional. Especifica o devuelve la versión de CLR preferida para cargar.|  
|`pcchVersion`|[in, out] Obligatorio. Especifica el tamaño esperado de `pwzVersion` como entrada, para evitar saturaciones de búfer. Si `pwzVersion` es nulo, `pcchVersion` contiene el tamaño esperado de `pwzVersion` cuando `GetRequestedRuntime` devuelve, para permitir la asignación previa; en caso contrario, `pcchVersion` contiene el número de caracteres escritos en `pwzVersion`.|  
|`pwzImageVersion`|[out] Opcional. Cuando `GetRequestedRuntime` devuelve, contiene la versión CLR correspondiente a la [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaz que se devuelve.|  
|`pcchImageVersion`|[in, out] Opcional. Especifica el tamaño de `pwzImageVersion` como entrada, para evitar saturaciones de búfer. Si `pwzImageVersion` es nulo, `pcchImageVersion` contiene el tamaño necesario de `pwzImageVersion` cuando `GetRequestedRuntime` devuelve, para permitir la asignación previa.|  
|`pdwConfigFlags`|[out] Opcional. Si `GetRequestedRuntime` usa un archivo de configuración durante el proceso de enlace, cuando devuelve, `pdwConfigFlags` contiene un [METAHOST_CONFIG_FLAGS](../../../../docs/framework/unmanaged-api/hosting/metahost-config-flags-enumeration.md) valor que indica si la [ \<Inicio >](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) elemento tiene el `useLegacyV2RuntimeActivationPolicy` atributo conjunto y el valor del atributo. Aplicar el [METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK](../../../../docs/framework/unmanaged-api/hosting/metahost-config-flags-enumeration.md) enmascarar a `pdwConfigFlags` para obtener los valores pertinentes para `useLegacyV2RuntimeActivationPolicy`.|  
|`riid`|[in] Especifica el identificador de interfaz IID_ICLRRuntimeInfo para solicitado [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaz.|  
|`ppRuntime`|[out] Cuando `GetRequestedRuntime` devuelve, contiene un puntero a la correspondiente [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaz.|  
  
## <a name="remarks"></a>Comentarios  
 Cuando este método se ejecuta correctamente, tiene el efecto secundario de combinar marcas adicionales con las marcas de inicio predeterminadas actuales de la interfaz en tiempo de ejecución devuelta, solo si existen uno o varios de los siguientes elementos en la secuencia de configuración dentro de la sección `<configuration><runtime>`:  
  
-   `<gcServer enabled="true"/>` hace que `STARTUP_SERVER_GC` se establezca.  
  
-   `<etwEnable enabled="true"/>` hace que `STARTUP_ETW` se establezca.  
  
-   `<appDomainResourceMonitoring enabled="true"/>` hace que `STARTUP_ARM` se establezca.  
  
 El valor `STARTUP_FLAGS` predeterminado resultante es la combinación OR bit a bit de los valores establecidos de la lista anterior con las marcas de inicio predeterminadas.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve los siguientes HRESULT específicos así como los errores HRESULT que indican un error del método.  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|El método se completó correctamente.|  
|E_POINTER|`pwzVersion` no es nulo y `pcchVersion` es nulo.<br /><br /> O bien<br /><br /> `pwzImageVersion` no es nulo y `pcchImageVersion` es nulo.|  
|E_INVALIDARG|`dwPolicyFlags` no especifica `METAHOST_POLICY_HIGHCOMPAT`.|  
|ERROR_INSUFFICIENT_BUFFER|La memoria asignada a `pwzVerison` no es adecuada.<br /><br /> O bien<br /><br /> La memoria asignada a `pwzImageVerison` no es adecuada.|  
|CLR_E_SHIM_RUNTIMELOAD|`dwPolicyFlags` incluye METAHOST_POLICY_APPLY_UPGRADE_POLICY y tanto `pwzVersion` como `pcchVersion` son nulos.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MetaHost.h  
  
 **Biblioteca:** incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICLRMetaHostPolicy (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md)  
 [Interfaces de hospedaje de CLR agregadas en .NET Framework 4 y 4.5](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [Hospedar aplicaciones de WPF](../../../../docs/framework/unmanaged-api/hosting/index.md)
