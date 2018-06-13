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
ms.openlocfilehash: c83f6dfe069b75f1ab3256f4e5a083f85b50adad
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435921"
---
# <a name="iclrmetahostgetruntime-method"></a><span data-ttu-id="74f9d-102">ICLRMetaHost::GetRuntime (Método)</span><span class="sxs-lookup"><span data-stu-id="74f9d-102">ICLRMetaHost::GetRuntime Method</span></span>
<span data-ttu-id="74f9d-103">Obtiene el [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaz que corresponde a una versión determinada de common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="74f9d-103">Gets the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface that corresponds to a particular version of the common language runtime (CLR).</span></span> <span data-ttu-id="74f9d-104">Este método reemplaza a la [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) función que se usa con la [STARTUP_LOADER_SAFEMODE](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) marca.</span><span class="sxs-lookup"><span data-stu-id="74f9d-104">This method supersedes the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) function used with the [STARTUP_LOADER_SAFEMODE](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) flag.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74f9d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="74f9d-105">Syntax</span></span>  
  
```  
HRESULT GetRuntime (  
    [in] LPCWSTR pwzVersion,  
    [in, REFIID riid,  
    [out,iid_is(riid), retval] LPVOID *ppRuntime  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="74f9d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="74f9d-106">Parameters</span></span>  
 `pwzVersion`  
 <span data-ttu-id="74f9d-107">[in] La versión de compilación de .NET Framework almacenada en los metadatos, en el formato "v*A*. *B*[. *X*] ".</span><span class="sxs-lookup"><span data-stu-id="74f9d-107">[in] The .NET Framework compilation version stored in the metadata, in the format "v*A*.*B*[.*X*]".</span></span> <span data-ttu-id="74f9d-108">*A*, *B*, y *X* son números decimales que corresponden a la versión principal, la versión secundaria y el número de compilación.</span><span class="sxs-lookup"><span data-stu-id="74f9d-108">*A*, *B*, and *X* are decimal numbers that correspond to the major version, the minor version, and the build number.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="74f9d-109">Este parámetro debe coincidir con el nombre del directorio para la versión de .NET Framework, tal y como aparece bajo C:\Windows\Microsoft.NET\Framework o C:\Windows\Microsoft.NET\Framework64.</span><span class="sxs-lookup"><span data-stu-id="74f9d-109">This parameter must match the directory name for the .NET Framework version, as it appears under C:\Windows\Microsoft.NET\Framework or C:\Windows\Microsoft.NET\Framework64.</span></span>  
  
 <span data-ttu-id="74f9d-110">Valores de ejemplo son "v1.0.3705", "v1.1.4322", "v2.0.50727" y "v4.0. *X*", donde *X* depende del número de compilación instalado.</span><span class="sxs-lookup"><span data-stu-id="74f9d-110">Example values are "v1.0.3705", "v1.1.4322", "v2.0.50727", and "v4.0.*X*", where *X* depends on the build number installed.</span></span> <span data-ttu-id="74f9d-111">El prefijo "v" es necesario.</span><span class="sxs-lookup"><span data-stu-id="74f9d-111">The "v" prefix is required.</span></span>  
  
 `riid`  
 <span data-ttu-id="74f9d-112">[in] El identificador de la interfaz deseada.</span><span class="sxs-lookup"><span data-stu-id="74f9d-112">[in] The identifier for the desired interface.</span></span> <span data-ttu-id="74f9d-113">Actualmente, el único valor válido para este parámetro es IID_ICLRRuntimeInfo.</span><span class="sxs-lookup"><span data-stu-id="74f9d-113">Currently, the only valid value for this parameter is IID_ICLRRuntimeInfo.</span></span>  
  
 `ppRuntime`  
 <span data-ttu-id="74f9d-114">[out] Un puntero a la [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaz que se corresponde con el runtime solicitado.</span><span class="sxs-lookup"><span data-stu-id="74f9d-114">[out] A pointer to the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface that corresponds to the requested runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="74f9d-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="74f9d-115">Return Value</span></span>  
 <span data-ttu-id="74f9d-116">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="74f9d-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="74f9d-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="74f9d-117">HRESULT</span></span>|<span data-ttu-id="74f9d-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="74f9d-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="74f9d-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="74f9d-119">S_OK</span></span>|<span data-ttu-id="74f9d-120">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="74f9d-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="74f9d-121">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="74f9d-121">E_POINTER</span></span>|<span data-ttu-id="74f9d-122">`pwzVersion` o `ppRuntime` es null.</span><span class="sxs-lookup"><span data-stu-id="74f9d-122">`pwzVersion` or `ppRuntime` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="74f9d-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="74f9d-123">Remarks</span></span>  
 <span data-ttu-id="74f9d-124">Este método interactúa de forma coherente con las interfaces heredadas, como el [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) funciones de interfaz y heredado como las regiones `CorBindTo*` funciones (consulte [en desuso de CLR Hosting Functions](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) en la API de hospedaje de .NET Framework 2.0).</span><span class="sxs-lookup"><span data-stu-id="74f9d-124">This method interacts consistently with legacy interfaces such as the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) interface and legacy functions such as the deprecated `CorBindTo*` functions (see [Deprecated CLR Hosting Functions](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) in the .NET Framework 2.0 hosting API).</span></span> <span data-ttu-id="74f9d-125">Es decir, es visible para la nueva API de tiempo de ejecución que se carga con la API heredada y tiempo de ejecución que se carga con la nueva API está visible para la API heredada.</span><span class="sxs-lookup"><span data-stu-id="74f9d-125">That is, runtimes that are loaded with the legacy API are visible to the new API, and runtimes that are loaded with the new API are visible to the legacy API.</span></span> <span data-ttu-id="74f9d-126">.</span><span class="sxs-lookup"><span data-stu-id="74f9d-126">.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74f9d-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="74f9d-127">Requirements</span></span>  
 <span data-ttu-id="74f9d-128">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74f9d-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74f9d-129">**Encabezado:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="74f9d-129">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="74f9d-130">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="74f9d-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="74f9d-131">**Versiones de .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74f9d-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74f9d-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="74f9d-132">See Also</span></span>  
 [<span data-ttu-id="74f9d-133">ICLRMetaHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="74f9d-133">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 [<span data-ttu-id="74f9d-134">Coclases e interfaces de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="74f9d-134">Deprecated CLR Hosting Interfaces and Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)  
 [<span data-ttu-id="74f9d-135">Interfaces de hospedaje de CLR</span><span class="sxs-lookup"><span data-stu-id="74f9d-135">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 [<span data-ttu-id="74f9d-136">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="74f9d-136">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)  
 [<span data-ttu-id="74f9d-137">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="74f9d-137">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
