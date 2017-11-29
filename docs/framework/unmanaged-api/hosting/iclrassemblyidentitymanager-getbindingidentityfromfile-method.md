---
title: "ICLRAssemblyIdentityManager::GetBindingIdentityFromFile (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRAssemblyIdentityManager.GetBindingIdentityFromFile
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRAssemblyIdentityManager::GetBindingIdentityFromFile
helpviewer_keywords:
- GetBindingIdentityFromFile method [.NET Framework hosting]
- ICLRAssemblyIdentityManager::GetBindingIdentifyFromFile method [.NET Framework hosting]
ms.assetid: 7797562d-7b4c-4bd9-8b93-f35e0e2869e4
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 140240f5f108cdd26cd0e813d7fe47f102a3b941
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="iclrassemblyidentitymanagergetbindingidentityfromfile-method"></a><span data-ttu-id="aba43-102">ICLRAssemblyIdentityManager::GetBindingIdentityFromFile (Método)</span><span class="sxs-lookup"><span data-stu-id="aba43-102">ICLRAssemblyIdentityManager::GetBindingIdentityFromFile Method</span></span>
<span data-ttu-id="aba43-103">Obtiene la identidad del ensamblado enlace de datos para el ensamblado en la ruta de acceso de archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="aba43-103">Gets the assembly identity binding data for the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aba43-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aba43-104">Syntax</span></span>  
  
```  
HRESULT GetBindingIdentityFromFile(  
    [in] LPCWSTR     pwzFilePath,  
    [in] DWORD       dwFlags,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="aba43-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="aba43-105">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="aba43-106">[in] La ruta de acceso al archivo que se debe evaluar.</span><span class="sxs-lookup"><span data-stu-id="aba43-106">[in] The path to the file to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="aba43-107">[in] Un valor de la [ECLRAssemblyIdentityFlags](../../../../docs/framework/unmanaged-api/hosting/eclrassemblyidentityflags-enumeration.md) enumeración que indica el tipo de identidad de un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="aba43-107">[in] A value of the [ECLRAssemblyIdentityFlags](../../../../docs/framework/unmanaged-api/hosting/eclrassemblyidentityflags-enumeration.md) enumeration that indicates an assembly's identity type.</span></span> <span data-ttu-id="aba43-108">Se proporciona para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="aba43-108">Provided for future extensibility.</span></span> <span data-ttu-id="aba43-109">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT es el único valor admitido por common language runtime (CLR) versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="aba43-109">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the common language runtime (CLR) version 2.0 supports.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="aba43-110">[out] Un búfer que contiene los datos de identidad de ensamblado opaco.</span><span class="sxs-lookup"><span data-stu-id="aba43-110">[out] A buffer containing the opaque assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="aba43-111">[entrada, salida] Un puntero al tamaño de `pwzBuffer`.</span><span class="sxs-lookup"><span data-stu-id="aba43-111">[in, out] A pointer to the size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="aba43-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="aba43-112">Return Value</span></span>  
  
|<span data-ttu-id="aba43-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="aba43-113">HRESULT</span></span>|<span data-ttu-id="aba43-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="aba43-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="aba43-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="aba43-115">S_OK</span></span>|<span data-ttu-id="aba43-116">El método se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="aba43-116">The method returned successfully.</span></span>|  
|<span data-ttu-id="aba43-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="aba43-117">E_INVALIDARG</span></span>|<span data-ttu-id="aba43-118">Suministrado `pwzFilePath` es null.</span><span class="sxs-lookup"><span data-stu-id="aba43-118">The supplied `pwzFilePath` is null.</span></span>|  
|<span data-ttu-id="aba43-119">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="aba43-119">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="aba43-120">El tamaño de `pwzBuffer` es demasiado pequeño.</span><span class="sxs-lookup"><span data-stu-id="aba43-120">The size of `pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="aba43-121">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="aba43-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="aba43-122">El CLR no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="aba43-122">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="aba43-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="aba43-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="aba43-124">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="aba43-124">The call timed out.</span></span>|  
|<span data-ttu-id="aba43-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="aba43-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="aba43-126">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="aba43-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="aba43-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="aba43-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="aba43-128">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="aba43-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="aba43-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="aba43-129">E_FAIL</span></span>|<span data-ttu-id="aba43-130">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="aba43-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="aba43-131">Si el método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="aba43-131">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="aba43-132">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="aba43-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aba43-133">Comentarios</span><span class="sxs-lookup"><span data-stu-id="aba43-133">Remarks</span></span>  
 <span data-ttu-id="aba43-134">`GetBindingIdentityFromFile`Normalmente se llama dos veces.</span><span class="sxs-lookup"><span data-stu-id="aba43-134">`GetBindingIdentityFromFile` is typically called twice.</span></span> <span data-ttu-id="aba43-135">La primera llamada proporciona un valor null para `pwzBuffer`, y el método devuelve el tamaño adecuado en `pcchBufferSize`.</span><span class="sxs-lookup"><span data-stu-id="aba43-135">The first call supplies a null value for `pwzBuffer`, and the method returns the appropriate size in `pcchBufferSize`.</span></span> <span data-ttu-id="aba43-136">La segunda llamada proporciona un búfer correctamente asignado y el método devuelve con los datos del búfer reales cuando se complete.</span><span class="sxs-lookup"><span data-stu-id="aba43-136">The second call supplies an appropriately allocated buffer, and the method returns with the actual buffer data upon completion.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aba43-137">Requisitos</span><span class="sxs-lookup"><span data-stu-id="aba43-137">Requirements</span></span>  
 <span data-ttu-id="aba43-138">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aba43-138">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aba43-139">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="aba43-139">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="aba43-140">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="aba43-140">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="aba43-141">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aba43-141">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aba43-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="aba43-142">See Also</span></span>  
 [<span data-ttu-id="aba43-143">ICLRAssemblyIdentityManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="aba43-143">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="aba43-144">ICLRAssemblyReferenceList (interfaz)</span><span class="sxs-lookup"><span data-stu-id="aba43-144">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="aba43-145">ICLRHostBindingPolicyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="aba43-145">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
