---
title: ICLRMetaHost::GetRuntime (Método)
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.GetRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::GetRuntime
helpviewer_keywords:
- GetRuntime method [.NET Framework hosting]
- ICLRMetaHost::GetRuntime method [.NET Framework hosting]
ms.assetid: a10749f1-ab91-47cf-982f-d8ccd2e81bd2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 273891b0814d9383d9640c79f5df959f2b9398b0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54707913"
---
# <a name="iclrmetahostgetruntime-method"></a><span data-ttu-id="ab022-102">ICLRMetaHost::GetRuntime (Método)</span><span class="sxs-lookup"><span data-stu-id="ab022-102">ICLRMetaHost::GetRuntime Method</span></span>
<span data-ttu-id="ab022-103">Obtiene el [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaz que corresponde a una versión determinada de common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="ab022-103">Gets the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface that corresponds to a particular version of the common language runtime (CLR).</span></span> <span data-ttu-id="ab022-104">Este método reemplaza el [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) función que se usa con el [STARTUP_LOADER_SAFEMODE](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) marca.</span><span class="sxs-lookup"><span data-stu-id="ab022-104">This method supersedes the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) function used with the [STARTUP_LOADER_SAFEMODE](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) flag.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab022-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ab022-105">Syntax</span></span>  
  
```  
HRESULT GetRuntime (  
    [in] LPCWSTR pwzVersion,  
    [in, REFIID riid,  
    [out,iid_is(riid), retval] LPVOID *ppRuntime  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ab022-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ab022-106">Parameters</span></span>  
 `pwzVersion`  
 <span data-ttu-id="ab022-107">[in] La versión de compilación de .NET Framework almacenada en los metadatos, en el formato "v*A*. *B*[. *X*] ".</span><span class="sxs-lookup"><span data-stu-id="ab022-107">[in] The .NET Framework compilation version stored in the metadata, in the format "v*A*.*B*[.*X*]".</span></span> <span data-ttu-id="ab022-108">*Un*, *B*, y *X* son números decimales que corresponden a la versión principal, la versión secundaria y el número de compilación.</span><span class="sxs-lookup"><span data-stu-id="ab022-108">*A*, *B*, and *X* are decimal numbers that correspond to the major version, the minor version, and the build number.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ab022-109">Este parámetro debe coincidir con el nombre del directorio para la versión de .NET Framework, tal y como aparece bajo C:\Windows\Microsoft.NET\Framework o C:\Windows\Microsoft.NET\Framework64.</span><span class="sxs-lookup"><span data-stu-id="ab022-109">This parameter must match the directory name for the .NET Framework version, as it appears under C:\Windows\Microsoft.NET\Framework or C:\Windows\Microsoft.NET\Framework64.</span></span>  
  
 <span data-ttu-id="ab022-110">Los valores de ejemplo son "v1.0.3705", "v1.1.4322", "v2.0.50727" y "v4.0. *X*", donde *X* depende del número de compilación instalado.</span><span class="sxs-lookup"><span data-stu-id="ab022-110">Example values are "v1.0.3705", "v1.1.4322", "v2.0.50727", and "v4.0.*X*", where *X* depends on the build number installed.</span></span> <span data-ttu-id="ab022-111">El prefijo "v" es necesario.</span><span class="sxs-lookup"><span data-stu-id="ab022-111">The "v" prefix is required.</span></span>  
  
 `riid`  
 <span data-ttu-id="ab022-112">[in] El identificador de la interfaz deseada.</span><span class="sxs-lookup"><span data-stu-id="ab022-112">[in] The identifier for the desired interface.</span></span> <span data-ttu-id="ab022-113">Actualmente, el único valor válido para este parámetro es IID_ICLRRuntimeInfo.</span><span class="sxs-lookup"><span data-stu-id="ab022-113">Currently, the only valid value for this parameter is IID_ICLRRuntimeInfo.</span></span>  
  
 `ppRuntime`  
 <span data-ttu-id="ab022-114">[out] Un puntero a la [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaz que se corresponde con el tiempo de ejecución solicitado.</span><span class="sxs-lookup"><span data-stu-id="ab022-114">[out] A pointer to the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface that corresponds to the requested runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ab022-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ab022-115">Return Value</span></span>  
 <span data-ttu-id="ab022-116">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="ab022-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="ab022-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ab022-117">HRESULT</span></span>|<span data-ttu-id="ab022-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="ab022-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ab022-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="ab022-119">S_OK</span></span>|<span data-ttu-id="ab022-120">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="ab022-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="ab022-121">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="ab022-121">E_POINTER</span></span>|<span data-ttu-id="ab022-122">`pwzVersion` o `ppRuntime` es null.</span><span class="sxs-lookup"><span data-stu-id="ab022-122">`pwzVersion` or `ppRuntime` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ab022-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ab022-123">Remarks</span></span>  
 <span data-ttu-id="ab022-124">Este método interactúa de forma coherente con las interfaces heredadas, como el [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) interfaz y funciones heredadas como en desuso `CorBindTo*` funciones (consulte [en desuso hospeda las funciones CLR](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) en la API de hospedaje de .NET Framework 2.0).</span><span class="sxs-lookup"><span data-stu-id="ab022-124">This method interacts consistently with legacy interfaces such as the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) interface and legacy functions such as the deprecated `CorBindTo*` functions (see [Deprecated CLR Hosting Functions](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) in the .NET Framework 2.0 hosting API).</span></span> <span data-ttu-id="ab022-125">Es decir, los tiempos de ejecución que se cargan con la API heredada son visibles para la nueva API y los tiempos de ejecución que se cargan con la nueva API son visibles para la API heredada.</span><span class="sxs-lookup"><span data-stu-id="ab022-125">That is, runtimes that are loaded with the legacy API are visible to the new API, and runtimes that are loaded with the new API are visible to the legacy API.</span></span> <span data-ttu-id="ab022-126">.</span><span class="sxs-lookup"><span data-stu-id="ab022-126">.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab022-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ab022-127">Requirements</span></span>  
 <span data-ttu-id="ab022-128">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ab022-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab022-129">**Encabezado**: MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="ab022-129">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="ab022-130">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ab022-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ab022-131">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab022-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab022-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="ab022-132">See also</span></span>
- [<span data-ttu-id="ab022-133">ICLRMetaHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ab022-133">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [<span data-ttu-id="ab022-134">Coclases e interfaces de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="ab022-134">Deprecated CLR Hosting Interfaces and Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)
- [<span data-ttu-id="ab022-135">Interfaces de hospedaje de CLR</span><span class="sxs-lookup"><span data-stu-id="ab022-135">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [<span data-ttu-id="ab022-136">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="ab022-136">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
- [<span data-ttu-id="ab022-137">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="ab022-137">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
