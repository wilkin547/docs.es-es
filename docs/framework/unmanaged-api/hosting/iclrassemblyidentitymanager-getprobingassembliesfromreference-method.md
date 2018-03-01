---
title: "ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRAssemblyIdentityManager.GetProbingAssembliesFromReference
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference
helpviewer_keywords:
- ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference method [.NET Framework hosting]
- GetProbingAssembliesFromReference method [.NET Framework hosting]
ms.assetid: aec05744-e8d4-44c6-b4a8-e583229ac34e
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f255db046f4c7d698ad864723167e81952481519
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="iclrassemblyidentitymanagergetprobingassembliesfromreference-method"></a><span data-ttu-id="5a41c-102">ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference (Método)</span><span class="sxs-lookup"><span data-stu-id="5a41c-102">ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference Method</span></span>
<span data-ttu-id="5a41c-103">Obtiene un [ICLRProbingAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md) enumerador para las identidades de ensamblado al que hace referencia el ensamblado con el tipo de identidad especificado.</span><span class="sxs-lookup"><span data-stu-id="5a41c-103">Gets an [ICLRProbingAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md) enumerator for the assembly identities referenced by the assembly with the specified identity type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a41c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5a41c-104">Syntax</span></span>  
  
```  
HRESULT GetProbingAssembliesFromReference (  
    [in] DWORD   dwMachineType,  
    [in] DWORD   dwFlags,  
    [in] LPCWSTR pwzReferenceIdentity,  
    [out] ICLRProbingAssemblyEnum **ppProbingAssemblyEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5a41c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5a41c-105">Parameters</span></span>  
 `dwMachineType`  
 <span data-ttu-id="5a41c-106">[in] Un valor válido que especifica la arquitectura del procesador, tal como se define en WinNT.h.</span><span class="sxs-lookup"><span data-stu-id="5a41c-106">[in] A valid value that specifies the processor architecture, as defined in WinNT.h.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="5a41c-107">[in] Se proporciona para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="5a41c-107">[in] Provided for future extensibility.</span></span> <span data-ttu-id="5a41c-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT es el único valor admitido por la versión actual de common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="5a41c-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pwzReferenceIdentity`  
 <span data-ttu-id="5a41c-109">[in] Una identidad de enlace de ensamblado opaco, normalmente devuelta desde una llamada a la [ICLRAssemblyIdentityManager:: GetBindingIdentityFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromfile-method.md) o [ICLRAssemblyIdentityManager:: GetBindingIdentityFromStream](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromstream-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="5a41c-109">[in] An opaque assembly binding identity, typically returned from a call to the [ICLRAssemblyIdentityManager::GetBindingIdentityFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromfile-method.md) or [ICLRAssemblyIdentityManager::GetBindingIdentityFromStream](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getbindingidentityfromstream-method.md) method.</span></span>  
  
 `ppProbingAssemblyEnum`  
 <span data-ttu-id="5a41c-110">[out] Un puntero de interfaz a una `ICLRProbingAssemblyEnum` enumerador que contiene referencias a los ensamblados al que hace referencia el ensamblado identificado por `pwzReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="5a41c-110">[out] An interface pointer to an `ICLRProbingAssemblyEnum` enumerator that contains references to the assemblies referenced by the assembly identified by `pwzReferenceIdentity`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5a41c-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5a41c-111">Return Value</span></span>  
  
|<span data-ttu-id="5a41c-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5a41c-112">HRESULT</span></span>|<span data-ttu-id="5a41c-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="5a41c-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5a41c-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="5a41c-114">S_OK</span></span>|<span data-ttu-id="5a41c-115">El método se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="5a41c-115">The method returned successfully.</span></span>|  
|<span data-ttu-id="5a41c-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5a41c-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5a41c-117">El CLR no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="5a41c-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5a41c-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5a41c-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5a41c-119">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="5a41c-119">The call timed out.</span></span>|  
|<span data-ttu-id="5a41c-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5a41c-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5a41c-121">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="5a41c-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5a41c-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5a41c-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5a41c-123">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="5a41c-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5a41c-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5a41c-124">E_FAIL</span></span>|<span data-ttu-id="5a41c-125">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="5a41c-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5a41c-126">Si el método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="5a41c-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5a41c-127">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="5a41c-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5a41c-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5a41c-128">Requirements</span></span>  
 <span data-ttu-id="5a41c-129">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a41c-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a41c-130">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5a41c-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5a41c-131">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5a41c-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5a41c-132">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a41c-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a41c-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="5a41c-133">See Also</span></span>  
 [<span data-ttu-id="5a41c-134">ICLRAssemblyIdentityManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5a41c-134">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="5a41c-135">ICLRAssemblyReferenceList (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5a41c-135">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="5a41c-136">ICLRProbingAssemblyEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5a41c-136">ICLRProbingAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)
