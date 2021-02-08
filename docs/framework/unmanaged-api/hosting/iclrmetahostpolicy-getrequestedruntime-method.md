---
description: 'Más información sobre: ICLRMetaHostPolicy:: GetRequestedRuntime (método)'
title: ICLRMetaHostPolicy::GetRequestedRuntime (Método)
ms.date: 03/30/2017
api_name:
- ICLRMetaHostPolicy.GetRequestedRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHostPolicy::GetRequestedRuntime
helpviewer_keywords:
- GetRequestedRuntime method [.NET Framework hosting]
- ICLRMetaHostPolicy::GetRequestedRuntime method [.NET Framework hosting]
ms.assetid: 59ec1832-9cc1-4b5c-983d-03407e51de56
topic_type:
- apiref
ms.openlocfilehash: 0e11694b0cb66ad7fc28abf7bb9f7fc8c6931a19
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789845"
---
# <a name="iclrmetahostpolicygetrequestedruntime-method"></a>ICLRMetaHostPolicy::GetRequestedRuntime (Método)

Proporciona una interfaz a una versión preferida de Common Language Runtime (CLR) basándose en una directiva de hospedaje, un ensamblado administrado, una cadena de versión y una secuencia de configuración. En realidad, este método no carga ni activa CLR, sino que simplemente devuelve la interfaz [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) que representa el resultado de la Directiva. Este método sustituye a los métodos [GetRequestedRuntimeInfo](getrequestedruntimeinfo-function.md), [GetRequestedRuntimeVersion (](getrequestedruntimeversion-function.md), [CorBindToRuntimeHost](corbindtoruntimehost-function.md), [CorBindToRuntimeByCfg](corbindtoruntimebycfg-function.md)y [getcorrequiredversion (](getcorrequiredversion-function.md) .

## <a name="syntax"></a>Sintaxis

```cpp
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

## <a name="parameters"></a>Parámetros

|Nombre|Descripción|
|----------|-----------------|
|`dwPolicyFlags`|[in] Obligatorio. Especifica un miembro de la enumeración [METAHOST_POLICY_FLAGS](metahost-policy-flags-enumeration.md) , que representa una directiva de enlace y cualquier número de modificadores. La única directiva que está disponible actualmente es [METAHOST_POLICY_HIGHCOMPAT](metahost-policy-flags-enumeration.md).<br /><br /> Los modificadores incluyen [METAHOST_POLICY_EMULATE_EXE_LAUNCH](metahost-policy-flags-enumeration.md), [METAHOST_POLICY_APPLY_UPGRADE_POLICY](metahost-policy-flags-enumeration.md), [METAHOST_POLICY_SHOW_ERROR_DIALOG](metahost-policy-flags-enumeration.md), [METAHOST_POLICY_USE_PROCESS_IMAGE_PATH](metahost-policy-flags-enumeration.md)y [METAHOST_POLICY_ENSURE_SKU_SUPPORTED](metahost-policy-flags-enumeration.md).|
|`pwzBinary`|[in] Opcional. Especifica la ruta de acceso del archivo del ensamblado.|
|`pCfgStream`|[in] Opcional. Especifica el archivo de configuración como un <xref:System.Runtime.InteropServices.ComTypes.IStream?displayProperty=nameWithType>.|
|`pwzVersion`|[in, out] Opcional. Especifica o devuelve la versión de CLR preferida para cargar.|
|`pcchVersion`|[in, out] Obligatorio. Especifica el tamaño esperado de `pwzVersion` como entrada, para evitar saturaciones de búfer. Si `pwzVersion` es nulo, `pcchVersion` contiene el tamaño esperado de `pwzVersion` cuando `GetRequestedRuntime` devuelve, para permitir la asignación previa; en caso contrario, `pcchVersion` contiene el número de caracteres escritos en `pwzVersion`.|
|`pwzImageVersion`|[out] Opcional. Cuando `GetRequestedRuntime` devuelve, contiene la versión de CLR correspondiente a la interfaz [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) que se devuelve.|
|`pcchImageVersion`|[in, out] Opcional. Especifica el tamaño de `pwzImageVersion` como entrada, para evitar saturaciones de búfer. Si `pwzImageVersion` es nulo, `pcchImageVersion` contiene el tamaño necesario de `pwzImageVersion` cuando `GetRequestedRuntime` devuelve, para permitir la asignación previa.|
|`pdwConfigFlags`|[out] Opcional. Si `GetRequestedRuntime` utiliza un archivo de configuración durante el proceso de enlace, cuando devuelve, `pdwConfigFlags` contiene un valor [METAHOST_CONFIG_FLAGS](metahost-config-flags-enumeration.md) que indica si el [\<startup>](../../configure-apps/file-schema/startup/startup-element.md) elemento tiene el `useLegacyV2RuntimeActivationPolicy` atributo establecido y el valor del atributo. Aplique la máscara de [METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK](metahost-config-flags-enumeration.md) a `pdwConfigFlags` para obtener los valores relevantes para `useLegacyV2RuntimeActivationPolicy` .|
|`riid`|de Especifica el identificador de interfaz IID_ICLRRuntimeInfo para la interfaz [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) solicitada.|
|`ppRuntime`|enuncia Cuando `GetRequestedRuntime` devuelve, contiene un puntero a la interfaz [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) correspondiente.|

## <a name="remarks"></a>Observaciones

Cuando este método se ejecuta correctamente, tiene el efecto secundario de combinar marcas adicionales con las marcas de inicio predeterminadas actuales de la interfaz en tiempo de ejecución devuelta, solo si existen uno o varios de los siguientes elementos en la secuencia de configuración dentro de la sección `<configuration><runtime>`:

- `<gcServer enabled="true"/>` hace que `STARTUP_SERVER_GC` se establezca.

- `<etwEnable enabled="true"/>` hace que `STARTUP_ETW` se establezca.

- `<appDomainResourceMonitoring enabled="true"/>` hace que `STARTUP_ARM` se establezca.

El valor `STARTUP_FLAGS` predeterminado resultante es la combinación OR bit a bit de los valores establecidos de la lista anterior con las marcas de inicio predeterminadas.

## <a name="return-value"></a>Valor devuelto

Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.

|HRESULT|Descripción|
|-------------|-----------------|
|S_OK|El método se completó correctamente.|
|E_POINTER|`pwzVersion` no es nulo y `pcchVersion` es nulo.<br /><br /> o bien<br /><br /> `pwzImageVersion` no es nulo y `pcchImageVersion` es nulo.|
|E_INVALIDARG|`dwPolicyFlags` no especifica `METAHOST_POLICY_HIGHCOMPAT`.|
|ERROR_INSUFFICIENT_BUFFER|La memoria asignada a `pwzVersion` no es adecuada.<br /><br /> o bien<br /><br /> La memoria asignada a `pwzImageVersion` no es adecuada.|
|CLR_E_SHIM_RUNTIMELOAD|`dwPolicyFlags` incluye METAHOST_POLICY_APPLY_UPGRADE_POLICY y tanto `pwzVersion` como `pcchVersion` son nulos.|

## <a name="requirements"></a>Requisitos

**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).

**Encabezado:** Metahost. h

**Biblioteca:** Se incluye como un recurso en MSCorEE.dll

**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]

## <a name="see-also"></a>Vea también

- [ICLRMetaHostPolicy (Interfaz)](iclrmetahostpolicy-interface.md)
- [Interfaces de hospedaje de CLR agregadas en .NET Framework 4 y 4.5](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [Interfaces de hospedaje](hosting-interfaces.md)
- [Hospedar aplicaciones de WPF](index.md)
