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
# <a name="iclrmetahostpolicygetrequestedruntime-method"></a><span data-ttu-id="075e0-103">ICLRMetaHostPolicy::GetRequestedRuntime (Método)</span><span class="sxs-lookup"><span data-stu-id="075e0-103">ICLRMetaHostPolicy::GetRequestedRuntime Method</span></span>

<span data-ttu-id="075e0-104">Proporciona una interfaz a una versión preferida de Common Language Runtime (CLR) basándose en una directiva de hospedaje, un ensamblado administrado, una cadena de versión y una secuencia de configuración.</span><span class="sxs-lookup"><span data-stu-id="075e0-104">Provides an interface to a preferred version of the common language runtime (CLR) based on a hosting policy, managed assembly, version string, and configuration stream.</span></span> <span data-ttu-id="075e0-105">En realidad, este método no carga ni activa CLR, sino que simplemente devuelve la interfaz [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) que representa el resultado de la Directiva.</span><span class="sxs-lookup"><span data-stu-id="075e0-105">This method does not actually load or activate the CLR, but simply returns the [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface that represents the policy result.</span></span> <span data-ttu-id="075e0-106">Este método sustituye a los métodos [GetRequestedRuntimeInfo](getrequestedruntimeinfo-function.md), [GetRequestedRuntimeVersion (](getrequestedruntimeversion-function.md), [CorBindToRuntimeHost](corbindtoruntimehost-function.md), [CorBindToRuntimeByCfg](corbindtoruntimebycfg-function.md)y [getcorrequiredversion (](getcorrequiredversion-function.md) .</span><span class="sxs-lookup"><span data-stu-id="075e0-106">This method supersedes the [GetRequestedRuntimeInfo](getrequestedruntimeinfo-function.md), [GetRequestedRuntimeVersion](getrequestedruntimeversion-function.md), [CorBindToRuntimeHost](corbindtoruntimehost-function.md), [CorBindToRuntimeByCfg](corbindtoruntimebycfg-function.md), and [GetCORRequiredVersion](getcorrequiredversion-function.md) methods.</span></span>

## <a name="syntax"></a><span data-ttu-id="075e0-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="075e0-107">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="075e0-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="075e0-108">Parameters</span></span>

|<span data-ttu-id="075e0-109">Nombre</span><span class="sxs-lookup"><span data-stu-id="075e0-109">Name</span></span>|<span data-ttu-id="075e0-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="075e0-110">Description</span></span>|
|----------|-----------------|
|`dwPolicyFlags`|<span data-ttu-id="075e0-111">[in] Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="075e0-111">[in] Required.</span></span> <span data-ttu-id="075e0-112">Especifica un miembro de la enumeración [METAHOST_POLICY_FLAGS](metahost-policy-flags-enumeration.md) , que representa una directiva de enlace y cualquier número de modificadores.</span><span class="sxs-lookup"><span data-stu-id="075e0-112">Specifies a member of the [METAHOST_POLICY_FLAGS](metahost-policy-flags-enumeration.md) enumeration, representing a binding policy, and any number of modifiers.</span></span> <span data-ttu-id="075e0-113">La única directiva que está disponible actualmente es [METAHOST_POLICY_HIGHCOMPAT](metahost-policy-flags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="075e0-113">The only policy that is currently available is [METAHOST_POLICY_HIGHCOMPAT](metahost-policy-flags-enumeration.md).</span></span><br /><br /> <span data-ttu-id="075e0-114">Los modificadores incluyen [METAHOST_POLICY_EMULATE_EXE_LAUNCH](metahost-policy-flags-enumeration.md), [METAHOST_POLICY_APPLY_UPGRADE_POLICY](metahost-policy-flags-enumeration.md), [METAHOST_POLICY_SHOW_ERROR_DIALOG](metahost-policy-flags-enumeration.md), [METAHOST_POLICY_USE_PROCESS_IMAGE_PATH](metahost-policy-flags-enumeration.md)y [METAHOST_POLICY_ENSURE_SKU_SUPPORTED](metahost-policy-flags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="075e0-114">Modifiers include [METAHOST_POLICY_EMULATE_EXE_LAUNCH](metahost-policy-flags-enumeration.md), [METAHOST_POLICY_APPLY_UPGRADE_POLICY](metahost-policy-flags-enumeration.md), [METAHOST_POLICY_SHOW_ERROR_DIALOG](metahost-policy-flags-enumeration.md), [METAHOST_POLICY_USE_PROCESS_IMAGE_PATH](metahost-policy-flags-enumeration.md), and [METAHOST_POLICY_ENSURE_SKU_SUPPORTED](metahost-policy-flags-enumeration.md).</span></span>|
|`pwzBinary`|<span data-ttu-id="075e0-115">[in] Opcional.</span><span class="sxs-lookup"><span data-stu-id="075e0-115">[in] Optional.</span></span> <span data-ttu-id="075e0-116">Especifica la ruta de acceso del archivo del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="075e0-116">Specifies the assembly file path.</span></span>|
|`pCfgStream`|<span data-ttu-id="075e0-117">[in] Opcional.</span><span class="sxs-lookup"><span data-stu-id="075e0-117">[in] Optional.</span></span> <span data-ttu-id="075e0-118">Especifica el archivo de configuración como un <xref:System.Runtime.InteropServices.ComTypes.IStream?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="075e0-118">Specifies the configuration file as a <xref:System.Runtime.InteropServices.ComTypes.IStream?displayProperty=nameWithType>.</span></span>|
|`pwzVersion`|<span data-ttu-id="075e0-119">[in, out] Opcional.</span><span class="sxs-lookup"><span data-stu-id="075e0-119">[in, out] Optional.</span></span> <span data-ttu-id="075e0-120">Especifica o devuelve la versión de CLR preferida para cargar.</span><span class="sxs-lookup"><span data-stu-id="075e0-120">Specifies or returns the preferred CLR version to be loaded.</span></span>|
|`pcchVersion`|<span data-ttu-id="075e0-121">[in, out] Obligatorio.</span><span class="sxs-lookup"><span data-stu-id="075e0-121">[in, out] Required.</span></span> <span data-ttu-id="075e0-122">Especifica el tamaño esperado de `pwzVersion` como entrada, para evitar saturaciones de búfer.</span><span class="sxs-lookup"><span data-stu-id="075e0-122">Specifies the expected size of `pwzVersion` as input, to avoid buffer overruns.</span></span> <span data-ttu-id="075e0-123">Si `pwzVersion` es nulo, `pcchVersion` contiene el tamaño esperado de `pwzVersion` cuando `GetRequestedRuntime` devuelve, para permitir la asignación previa; en caso contrario, `pcchVersion` contiene el número de caracteres escritos en `pwzVersion`.</span><span class="sxs-lookup"><span data-stu-id="075e0-123">If `pwzVersion` is null, `pcchVersion` contains the expected size of `pwzVersion` when `GetRequestedRuntime` returns, to allow pre-allocation; otherwise, `pcchVersion` contains the number of characters written to `pwzVersion`.</span></span>|
|`pwzImageVersion`|<span data-ttu-id="075e0-124">[out] Opcional.</span><span class="sxs-lookup"><span data-stu-id="075e0-124">[out] Optional.</span></span> <span data-ttu-id="075e0-125">Cuando `GetRequestedRuntime` devuelve, contiene la versión de CLR correspondiente a la interfaz [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) que se devuelve.</span><span class="sxs-lookup"><span data-stu-id="075e0-125">When `GetRequestedRuntime` returns, contains the CLR version corresponding to the [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface that is returned.</span></span>|
|`pcchImageVersion`|<span data-ttu-id="075e0-126">[in, out] Opcional.</span><span class="sxs-lookup"><span data-stu-id="075e0-126">[in, out] Optional.</span></span> <span data-ttu-id="075e0-127">Especifica el tamaño de `pwzImageVersion` como entrada, para evitar saturaciones de búfer.</span><span class="sxs-lookup"><span data-stu-id="075e0-127">Specifies the size of `pwzImageVersion` as input to avoid buffer overruns.</span></span> <span data-ttu-id="075e0-128">Si `pwzImageVersion` es nulo, `pcchImageVersion` contiene el tamaño necesario de `pwzImageVersion` cuando `GetRequestedRuntime` devuelve, para permitir la asignación previa.</span><span class="sxs-lookup"><span data-stu-id="075e0-128">If `pwzImageVersion` is null, `pcchImageVersion` contains the required size of `pwzImageVersion` when `GetRequestedRuntime` returns, to allow pre-allocation.</span></span>|
|`pdwConfigFlags`|<span data-ttu-id="075e0-129">[out] Opcional.</span><span class="sxs-lookup"><span data-stu-id="075e0-129">[out] Optional.</span></span> <span data-ttu-id="075e0-130">Si `GetRequestedRuntime` utiliza un archivo de configuración durante el proceso de enlace, cuando devuelve, `pdwConfigFlags` contiene un valor [METAHOST_CONFIG_FLAGS](metahost-config-flags-enumeration.md) que indica si el [\<startup>](../../configure-apps/file-schema/startup/startup-element.md) elemento tiene el `useLegacyV2RuntimeActivationPolicy` atributo establecido y el valor del atributo.</span><span class="sxs-lookup"><span data-stu-id="075e0-130">If `GetRequestedRuntime` uses a configuration file during the binding process, when it returns, `pdwConfigFlags` contains a [METAHOST_CONFIG_FLAGS](metahost-config-flags-enumeration.md) value that indicates whether the [\<startup>](../../configure-apps/file-schema/startup/startup-element.md) element has the `useLegacyV2RuntimeActivationPolicy` attribute set, and the value of the attribute.</span></span> <span data-ttu-id="075e0-131">Aplique la máscara de [METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK](metahost-config-flags-enumeration.md) a `pdwConfigFlags` para obtener los valores relevantes para `useLegacyV2RuntimeActivationPolicy` .</span><span class="sxs-lookup"><span data-stu-id="075e0-131">Apply the [METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK](metahost-config-flags-enumeration.md) mask to `pdwConfigFlags` to get the values relevant to `useLegacyV2RuntimeActivationPolicy`.</span></span>|
|`riid`|<span data-ttu-id="075e0-132">de Especifica el identificador de interfaz IID_ICLRRuntimeInfo para la interfaz [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) solicitada.</span><span class="sxs-lookup"><span data-stu-id="075e0-132">[in] Specifies the interface identifier IID_ICLRRuntimeInfo for the requested [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface.</span></span>|
|`ppRuntime`|<span data-ttu-id="075e0-133">enuncia Cuando `GetRequestedRuntime` devuelve, contiene un puntero a la interfaz [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) correspondiente.</span><span class="sxs-lookup"><span data-stu-id="075e0-133">[out] When `GetRequestedRuntime` returns, contains a pointer to the corresponding [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface.</span></span>|

## <a name="remarks"></a><span data-ttu-id="075e0-134">Observaciones</span><span class="sxs-lookup"><span data-stu-id="075e0-134">Remarks</span></span>

<span data-ttu-id="075e0-135">Cuando este método se ejecuta correctamente, tiene el efecto secundario de combinar marcas adicionales con las marcas de inicio predeterminadas actuales de la interfaz en tiempo de ejecución devuelta, solo si existen uno o varios de los siguientes elementos en la secuencia de configuración dentro de la sección `<configuration><runtime>`:</span><span class="sxs-lookup"><span data-stu-id="075e0-135">When this method succeeds, it has the side effect of combining additional flags with the current default startup flags of the returned runtime interface, if and only if one or more of the following elements exist in the configuration stream within the `<configuration><runtime>` section:</span></span>

- <span data-ttu-id="075e0-136">`<gcServer enabled="true"/>` hace que `STARTUP_SERVER_GC` se establezca.</span><span class="sxs-lookup"><span data-stu-id="075e0-136">`<gcServer enabled="true"/>` causes `STARTUP_SERVER_GC` to be set.</span></span>

- <span data-ttu-id="075e0-137">`<etwEnable enabled="true"/>` hace que `STARTUP_ETW` se establezca.</span><span class="sxs-lookup"><span data-stu-id="075e0-137">`<etwEnable enabled="true"/>` causes `STARTUP_ETW` to be set.</span></span>

- <span data-ttu-id="075e0-138">`<appDomainResourceMonitoring enabled="true"/>` hace que `STARTUP_ARM` se establezca.</span><span class="sxs-lookup"><span data-stu-id="075e0-138">`<appDomainResourceMonitoring enabled="true"/>` causes `STARTUP_ARM` to be set.</span></span>

<span data-ttu-id="075e0-139">El valor `STARTUP_FLAGS` predeterminado resultante es la combinación OR bit a bit de los valores establecidos de la lista anterior con las marcas de inicio predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="075e0-139">The resulting default `STARTUP_FLAGS` value is the bitwise OR combination of the values that are set from the preceding list with the default startup flags.</span></span>

## <a name="return-value"></a><span data-ttu-id="075e0-140">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="075e0-140">Return Value</span></span>

<span data-ttu-id="075e0-141">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="075e0-141">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>

|<span data-ttu-id="075e0-142">HRESULT</span><span class="sxs-lookup"><span data-stu-id="075e0-142">HRESULT</span></span>|<span data-ttu-id="075e0-143">Descripción</span><span class="sxs-lookup"><span data-stu-id="075e0-143">Description</span></span>|
|-------------|-----------------|
|<span data-ttu-id="075e0-144">S_OK</span><span class="sxs-lookup"><span data-stu-id="075e0-144">S_OK</span></span>|<span data-ttu-id="075e0-145">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="075e0-145">The method completed successfully.</span></span>|
|<span data-ttu-id="075e0-146">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="075e0-146">E_POINTER</span></span>|<span data-ttu-id="075e0-147">`pwzVersion` no es nulo y `pcchVersion` es nulo.</span><span class="sxs-lookup"><span data-stu-id="075e0-147">`pwzVersion` is not null and `pcchVersion` is null.</span></span><br /><br /> <span data-ttu-id="075e0-148">o bien</span><span class="sxs-lookup"><span data-stu-id="075e0-148">-or-</span></span><br /><br /> <span data-ttu-id="075e0-149">`pwzImageVersion` no es nulo y `pcchImageVersion` es nulo.</span><span class="sxs-lookup"><span data-stu-id="075e0-149">`pwzImageVersion` is not null and `pcchImageVersion` is null.</span></span>|
|<span data-ttu-id="075e0-150">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="075e0-150">E_INVALIDARG</span></span>|<span data-ttu-id="075e0-151">`dwPolicyFlags` no especifica `METAHOST_POLICY_HIGHCOMPAT`.</span><span class="sxs-lookup"><span data-stu-id="075e0-151">`dwPolicyFlags` does not specify `METAHOST_POLICY_HIGHCOMPAT`.</span></span>|
|<span data-ttu-id="075e0-152">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="075e0-152">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="075e0-153">La memoria asignada a `pwzVersion` no es adecuada.</span><span class="sxs-lookup"><span data-stu-id="075e0-153">The memory allocated to `pwzVersion` is inadequate.</span></span><br /><br /> <span data-ttu-id="075e0-154">o bien</span><span class="sxs-lookup"><span data-stu-id="075e0-154">-or-</span></span><br /><br /> <span data-ttu-id="075e0-155">La memoria asignada a `pwzImageVersion` no es adecuada.</span><span class="sxs-lookup"><span data-stu-id="075e0-155">The memory allocated to `pwzImageVersion` is inadequate.</span></span>|
|<span data-ttu-id="075e0-156">CLR_E_SHIM_RUNTIMELOAD</span><span class="sxs-lookup"><span data-stu-id="075e0-156">CLR_E_SHIM_RUNTIMELOAD</span></span>|<span data-ttu-id="075e0-157">`dwPolicyFlags` incluye METAHOST_POLICY_APPLY_UPGRADE_POLICY y tanto `pwzVersion` como `pcchVersion` son nulos.</span><span class="sxs-lookup"><span data-stu-id="075e0-157">`dwPolicyFlags` includes METAHOST_POLICY_APPLY_UPGRADE_POLICY, and both `pwzVersion` and `pcchVersion` are null.</span></span>|

## <a name="requirements"></a><span data-ttu-id="075e0-158">Requisitos</span><span class="sxs-lookup"><span data-stu-id="075e0-158">Requirements</span></span>

<span data-ttu-id="075e0-159">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="075e0-159">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="075e0-160">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="075e0-160">**Header:** MetaHost.h</span></span>

<span data-ttu-id="075e0-161">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="075e0-161">**Library:** Included as a resource in MSCorEE.dll</span></span>

<span data-ttu-id="075e0-162">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="075e0-162">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="075e0-163">Vea también</span><span class="sxs-lookup"><span data-stu-id="075e0-163">See also</span></span>

- [<span data-ttu-id="075e0-164">ICLRMetaHostPolicy (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="075e0-164">ICLRMetaHostPolicy Interface</span></span>](iclrmetahostpolicy-interface.md)
- [<span data-ttu-id="075e0-165">Interfaces de hospedaje de CLR agregadas en .NET Framework 4 y 4.5</span><span class="sxs-lookup"><span data-stu-id="075e0-165">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [<span data-ttu-id="075e0-166">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="075e0-166">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="075e0-167">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="075e0-167">Hosting</span></span>](index.md)
