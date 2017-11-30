---
title: "ICLRAssemblyIdentityManager::GetBindingIdentityFromStream (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRAssemblyIdentityManager.GetBindingIdentityFromStream
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRAssemblyIdentityManager::GetBindingIdentityFromStream
helpviewer_keywords:
- GetBindingIdentityFromStream method [.NET Framework hosting]
- ICLRAssemblyIdentityManager::GetBindingIdentityFromStream method [.NET Framework hosting]
ms.assetid: 40123b30-a589-46b3-95d3-af7b2b0baa05
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: cd16f13bd77127953bdd17b258c7be518088f899
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="iclrassemblyidentitymanagergetbindingidentityfromstream-method"></a><span data-ttu-id="da09e-102">ICLRAssemblyIdentityManager::GetBindingIdentityFromStream (Método)</span><span class="sxs-lookup"><span data-stu-id="da09e-102">ICLRAssemblyIdentityManager::GetBindingIdentityFromStream Method</span></span>
<span data-ttu-id="da09e-103">Obtiene los datos de identidad de ensamblado canónico para el ensamblado en la secuencia especificada.</span><span class="sxs-lookup"><span data-stu-id="da09e-103">Gets the canonical assembly identity data for the assembly in the specified stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da09e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="da09e-104">Syntax</span></span>  
  
```  
HRESULT GetBindingIdentityFromStream (  
    [in] IStream    *pStream,  
    [in] DWORD       dwFlags,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="da09e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="da09e-105">Parameters</span></span>  
 `pStream`  
 <span data-ttu-id="da09e-106">[in] La secuencia de ensamblado que se debe evaluar.</span><span class="sxs-lookup"><span data-stu-id="da09e-106">[in] The assembly stream to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="da09e-107">[in] Se proporciona para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="da09e-107">[in] Provided for future extensibility.</span></span> <span data-ttu-id="da09e-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT es el único valor admitido por la versión actual de common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="da09e-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="da09e-109">[out] Un búfer que contiene los datos de identidad de ensamblado opaco.</span><span class="sxs-lookup"><span data-stu-id="da09e-109">[out] A buffer containing the opaque assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="da09e-110">[entrada, salida] El tamaño de `pwzBuffer`.</span><span class="sxs-lookup"><span data-stu-id="da09e-110">[in, out] The size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="da09e-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="da09e-111">Return Value</span></span>  
  
|<span data-ttu-id="da09e-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="da09e-112">HRESULT</span></span>|<span data-ttu-id="da09e-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="da09e-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="da09e-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="da09e-114">S_OK</span></span>|<span data-ttu-id="da09e-115">El método se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="da09e-115">The method returned successfully.</span></span>|  
|<span data-ttu-id="da09e-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="da09e-116">E_INVALIDARG</span></span>|<span data-ttu-id="da09e-117">Suministrado `pStream` es null.</span><span class="sxs-lookup"><span data-stu-id="da09e-117">The supplied `pStream` is null.</span></span>|  
|<span data-ttu-id="da09e-118">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="da09e-118">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="da09e-119">El tamaño de `pwzBuffer` es demasiado pequeño.</span><span class="sxs-lookup"><span data-stu-id="da09e-119">The size of `pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="da09e-120">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="da09e-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="da09e-121">El CLR no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="da09e-121">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="da09e-122">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="da09e-122">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="da09e-123">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="da09e-123">The call timed out.</span></span>|  
|<span data-ttu-id="da09e-124">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="da09e-124">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="da09e-125">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="da09e-125">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="da09e-126">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="da09e-126">HOST_E_ABANDONED</span></span>|<span data-ttu-id="da09e-127">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="da09e-127">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="da09e-128">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="da09e-128">E_FAIL</span></span>|<span data-ttu-id="da09e-129">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="da09e-129">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="da09e-130">Si el método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="da09e-130">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="da09e-131">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="da09e-131">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="da09e-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="da09e-132">Requirements</span></span>  
 <span data-ttu-id="da09e-133">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da09e-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da09e-134">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="da09e-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="da09e-135">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="da09e-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="da09e-136">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da09e-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da09e-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="da09e-137">See Also</span></span>  
 [<span data-ttu-id="da09e-138">ICLRAssemblyIdentityManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="da09e-138">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="da09e-139">ICLRAssemblyReferenceList (interfaz)</span><span class="sxs-lookup"><span data-stu-id="da09e-139">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
