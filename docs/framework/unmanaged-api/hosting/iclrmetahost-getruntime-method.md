---
description: 'Más información acerca de: ICLRMetaHost:: GetRuntime (método)'
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
ms.openlocfilehash: 8a2ada652dbb139337150cb8ed20986ebf8ae7f4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99637526"
---
# <a name="iclrmetahostgetruntime-method"></a><span data-ttu-id="3deda-103">ICLRMetaHost::GetRuntime (Método)</span><span class="sxs-lookup"><span data-stu-id="3deda-103">ICLRMetaHost::GetRuntime Method</span></span>

<span data-ttu-id="3deda-104">Obtiene la interfaz [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) que corresponde a una versión determinada del Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="3deda-104">Gets the [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface that corresponds to a particular version of the common language runtime (CLR).</span></span> <span data-ttu-id="3deda-105">Este método reemplaza a la función [CorBindToRuntimeEx](corbindtoruntimeex-function.md) utilizada con la marca [STARTUP_LOADER_SAFEMODE](startup-flags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="3deda-105">This method supersedes the [CorBindToRuntimeEx](corbindtoruntimeex-function.md) function used with the [STARTUP_LOADER_SAFEMODE](startup-flags-enumeration.md) flag.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3deda-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3deda-106">Syntax</span></span>  
  
```cpp  
HRESULT GetRuntime (  
    [in] LPCWSTR pwzVersion,  
    [in] REFIID riid,  
    [out,iid_is(riid), retval] LPVOID *ppRuntime  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3deda-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3deda-107">Parameters</span></span>  

 `pwzVersion`  
 <span data-ttu-id="3deda-108">de La versión de compilación de .NET Framework almacenada en los metadatos, en el formato "v *A*. *B*[.*X*] ".</span><span class="sxs-lookup"><span data-stu-id="3deda-108">[in] The .NET Framework compilation version stored in the metadata, in the format "v *A*.*B*[.*X*]".</span></span> <span data-ttu-id="3deda-109">*A*, *B* y *X* son números decimales que corresponden a la versión principal, la versión secundaria y el número de compilación.</span><span class="sxs-lookup"><span data-stu-id="3deda-109">*A*, *B*, and *X* are decimal numbers that correspond to the major version, the minor version, and the build number.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3deda-110">Este parámetro debe coincidir con el nombre de directorio de la versión .NET Framework, tal y como aparece en C:\Windows\Microsoft.NET\Framework o C:\Windows\Microsoft.NET\Framework64.</span><span class="sxs-lookup"><span data-stu-id="3deda-110">This parameter must match the directory name for the .NET Framework version, as it appears under C:\Windows\Microsoft.NET\Framework or C:\Windows\Microsoft.NET\Framework64.</span></span>  
  
 <span data-ttu-id="3deda-111">Los valores de ejemplo son "v 1.0.3705", "v 1.1.4322", "v 2.0.50727" y "v 4.0. *X*", donde *X* depende del número de compilación instalado.</span><span class="sxs-lookup"><span data-stu-id="3deda-111">Example values are "v1.0.3705", "v1.1.4322", "v2.0.50727", and "v4.0.*X*", where *X* depends on the build number installed.</span></span> <span data-ttu-id="3deda-112">El prefijo "v" es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="3deda-112">The "v" prefix is required.</span></span>  
  
 `riid`  
 <span data-ttu-id="3deda-113">de Identificador de la interfaz deseada.</span><span class="sxs-lookup"><span data-stu-id="3deda-113">[in] The identifier for the desired interface.</span></span> <span data-ttu-id="3deda-114">Actualmente, el único valor válido para este parámetro es IID_ICLRRuntimeInfo.</span><span class="sxs-lookup"><span data-stu-id="3deda-114">Currently, the only valid value for this parameter is IID_ICLRRuntimeInfo.</span></span>  
  
 `ppRuntime`  
 <span data-ttu-id="3deda-115">enuncia Puntero a la interfaz [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) que corresponde al Runtime solicitado.</span><span class="sxs-lookup"><span data-stu-id="3deda-115">[out] A pointer to the [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface that corresponds to the requested runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3deda-116">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3deda-116">Return Value</span></span>  

 <span data-ttu-id="3deda-117">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="3deda-117">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="3deda-118">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3deda-118">HRESULT</span></span>|<span data-ttu-id="3deda-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="3deda-119">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3deda-120">S_OK</span><span class="sxs-lookup"><span data-stu-id="3deda-120">S_OK</span></span>|<span data-ttu-id="3deda-121">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="3deda-121">The method completed successfully.</span></span>|  
|<span data-ttu-id="3deda-122">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="3deda-122">E_POINTER</span></span>|<span data-ttu-id="3deda-123">`pwzVersion` o `ppRuntime` es null.</span><span class="sxs-lookup"><span data-stu-id="3deda-123">`pwzVersion` or `ppRuntime` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3deda-124">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3deda-124">Remarks</span></span>  

 <span data-ttu-id="3deda-125">Este método interactúa de forma coherente con las interfaces heredadas como la interfaz [ICorRuntimeHost](icorruntimehost-interface.md) y las funciones heredadas como las funciones desusadas `CorBindTo*` (vea [funciones de hospedaje de CLR en desuso](deprecated-clr-hosting-functions.md) en la API de hospedaje de .NET Framework 2,0).</span><span class="sxs-lookup"><span data-stu-id="3deda-125">This method interacts consistently with legacy interfaces such as the [ICorRuntimeHost](icorruntimehost-interface.md) interface and legacy functions such as the deprecated `CorBindTo*` functions (see [Deprecated CLR Hosting Functions](deprecated-clr-hosting-functions.md) in the .NET Framework 2.0 hosting API).</span></span> <span data-ttu-id="3deda-126">Es decir, los tiempos de ejecución que se cargan con la API heredada están visibles para la nueva API y los tiempos de ejecución que se cargan con la nueva API son visibles para la API heredada.</span><span class="sxs-lookup"><span data-stu-id="3deda-126">That is, runtimes that are loaded with the legacy API are visible to the new API, and runtimes that are loaded with the new API are visible to the legacy API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3deda-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3deda-127">Requirements</span></span>  

 <span data-ttu-id="3deda-128">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3deda-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3deda-129">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="3deda-129">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="3deda-130">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3deda-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3deda-131">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3deda-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3deda-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="3deda-132">See also</span></span>

- [<span data-ttu-id="3deda-133">ICLRMetaHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3deda-133">ICLRMetaHost Interface</span></span>](iclrmetahost-interface.md)
- [<span data-ttu-id="3deda-134">Coclases e interfaces de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="3deda-134">Deprecated CLR Hosting Interfaces and Coclasses</span></span>](deprecated-clr-hosting-interfaces-and-coclasses.md)
- [<span data-ttu-id="3deda-135">Interfaces de hospedaje de CLR</span><span class="sxs-lookup"><span data-stu-id="3deda-135">CLR Hosting Interfaces</span></span>](clr-hosting-interfaces.md)
- [<span data-ttu-id="3deda-136">Funciones de hospedaje de CLR en desuso</span><span class="sxs-lookup"><span data-stu-id="3deda-136">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
- [<span data-ttu-id="3deda-137">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="3deda-137">Hosting</span></span>](index.md)
