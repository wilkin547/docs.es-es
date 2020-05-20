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
ms.openlocfilehash: a0d6496e014b767b2bdaf68cdc62017813e1e57f
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703634"
---
# <a name="iclrmetahostgetruntime-method"></a><span data-ttu-id="9c616-102">ICLRMetaHost::GetRuntime (Método)</span><span class="sxs-lookup"><span data-stu-id="9c616-102">ICLRMetaHost::GetRuntime Method</span></span>
<span data-ttu-id="9c616-103">Obtiene la interfaz [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) que corresponde a una versión determinada del Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="9c616-103">Gets the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface that corresponds to a particular version of the common language runtime (CLR).</span></span> <span data-ttu-id="9c616-104">Este método reemplaza a la función [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) utilizada con la marca [STARTUP_LOADER_SAFEMODE](startup-flags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="9c616-104">This method supersedes the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) function used with the [STARTUP_LOADER_SAFEMODE](startup-flags-enumeration.md) flag.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c616-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9c616-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRuntime (  
    [in] LPCWSTR pwzVersion,  
    [in] REFIID riid,  
    [out,iid_is(riid), retval] LPVOID *ppRuntime  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9c616-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9c616-106">Parameters</span></span>  
 `pwzVersion`  
 <span data-ttu-id="9c616-107">de La versión de compilación de .NET Framework almacenada en los metadatos, en el formato "v*A*. *B*[.\* X\*] ".</span><span class="sxs-lookup"><span data-stu-id="9c616-107">[in] The .NET Framework compilation version stored in the metadata, in the format "v*A*.*B*[.*X*]".</span></span> <span data-ttu-id="9c616-108">*A*, *B*y *X* son números decimales que corresponden a la versión principal, la versión secundaria y el número de compilación.</span><span class="sxs-lookup"><span data-stu-id="9c616-108">*A*, *B*, and *X* are decimal numbers that correspond to the major version, the minor version, and the build number.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9c616-109">Este parámetro debe coincidir con el nombre de directorio de la versión .NET Framework, tal y como aparece en C:\Windows\Microsoft.NET\Framework o C:\Windows\Microsoft.NET\Framework64.</span><span class="sxs-lookup"><span data-stu-id="9c616-109">This parameter must match the directory name for the .NET Framework version, as it appears under C:\Windows\Microsoft.NET\Framework or C:\Windows\Microsoft.NET\Framework64.</span></span>  
  
 <span data-ttu-id="9c616-110">Los valores de ejemplo son "v 1.0.3705", "v 1.1.4322", "v 2.0.50727" y "v 4.0. *X*", donde *X* depende del número de compilación instalado.</span><span class="sxs-lookup"><span data-stu-id="9c616-110">Example values are "v1.0.3705", "v1.1.4322", "v2.0.50727", and "v4.0.*X*", where *X* depends on the build number installed.</span></span> <span data-ttu-id="9c616-111">El prefijo "v" es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="9c616-111">The "v" prefix is required.</span></span>  
  
 `riid`  
 <span data-ttu-id="9c616-112">de Identificador de la interfaz deseada.</span><span class="sxs-lookup"><span data-stu-id="9c616-112">[in] The identifier for the desired interface.</span></span> <span data-ttu-id="9c616-113">Actualmente, el único valor válido para este parámetro es IID_ICLRRuntimeInfo.</span><span class="sxs-lookup"><span data-stu-id="9c616-113">Currently, the only valid value for this parameter is IID_ICLRRuntimeInfo.</span></span>  
  
 `ppRuntime`  
 <span data-ttu-id="9c616-114">enuncia Puntero a la interfaz [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) que corresponde al Runtime solicitado.</span><span class="sxs-lookup"><span data-stu-id="9c616-114">[out] A pointer to the [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface that corresponds to the requested runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9c616-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9c616-115">Return Value</span></span>  
 <span data-ttu-id="9c616-116">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="9c616-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="9c616-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9c616-117">HRESULT</span></span>|<span data-ttu-id="9c616-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="9c616-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9c616-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="9c616-119">S_OK</span></span>|<span data-ttu-id="9c616-120">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="9c616-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="9c616-121">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="9c616-121">E_POINTER</span></span>|<span data-ttu-id="9c616-122">`pwzVersion` o `ppRuntime` es null.</span><span class="sxs-lookup"><span data-stu-id="9c616-122">`pwzVersion` or `ppRuntime` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9c616-123">Observaciones</span><span class="sxs-lookup"><span data-stu-id="9c616-123">Remarks</span></span>  
 <span data-ttu-id="9c616-124">Este método interactúa de forma coherente con las interfaces heredadas como la interfaz [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) y las funciones heredadas como las funciones desusadas `CorBindTo*` (vea [funciones de hospedaje de CLR en desuso](deprecated-clr-hosting-functions.md) en la API de hospedaje de .NET Framework 2,0).</span><span class="sxs-lookup"><span data-stu-id="9c616-124">This method interacts consistently with legacy interfaces such as the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) interface and legacy functions such as the deprecated `CorBindTo*` functions (see [Deprecated CLR Hosting Functions](deprecated-clr-hosting-functions.md) in the .NET Framework 2.0 hosting API).</span></span> <span data-ttu-id="9c616-125">Es decir, los tiempos de ejecución que se cargan con la API heredada están visibles para la nueva API y los tiempos de ejecución que se cargan con la nueva API son visibles para la API heredada.</span><span class="sxs-lookup"><span data-stu-id="9c616-125">That is, runtimes that are loaded with the legacy API are visible to the new API, and runtimes that are loaded with the new API are visible to the legacy API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c616-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9c616-126">Requirements</span></span>  
 <span data-ttu-id="9c616-127">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9c616-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c616-128">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="9c616-128">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="9c616-129">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="9c616-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9c616-130">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c616-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c616-131">Consulta también</span><span class="sxs-lookup"><span data-stu-id="9c616-131">See also</span></span>

- [<span data-ttu-id="9c616-132">ICLRMetaHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9c616-132">ICLRMetaHost Interface</span></span>](iclrmetahost-interface.md)
- [<span data-ttu-id="9c616-133">Coclases e interfaces de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="9c616-133">Deprecated CLR Hosting Interfaces and Coclasses</span></span>](deprecated-clr-hosting-interfaces-and-coclasses.md)
- [<span data-ttu-id="9c616-134">Interfaces de hospedaje de CLR</span><span class="sxs-lookup"><span data-stu-id="9c616-134">CLR Hosting Interfaces</span></span>](clr-hosting-interfaces.md)
- [<span data-ttu-id="9c616-135">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="9c616-135">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
- [<span data-ttu-id="9c616-136">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="9c616-136">Hosting</span></span>](index.md)
