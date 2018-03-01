---
title: "ICLRAssemblyIdentityManager::GetReferencedAssembliesFromFile (Método)"
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
- ICLRAssemblyIdentityManager.GetReferencedAssembliesFromFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetReferencedAssembliesFromFile
helpviewer_keywords:
- ICLRAssemblyIdentityManager::GetReferenceAssembliesFromFile method [.NET Framework hosting]
- GetReferenceAssembliesFromFile method [.NET Framework hosting]
ms.assetid: eed63d31-d977-4c7d-9443-f9d37a2a7d81
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 856843cf1c4c5f1dffe23b04cf2655dfe37e476e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="iclrassemblyidentitymanagergetreferencedassembliesfromfile-method"></a><span data-ttu-id="de340-102">ICLRAssemblyIdentityManager::GetReferencedAssembliesFromFile (Método)</span><span class="sxs-lookup"><span data-stu-id="de340-102">ICLRAssemblyIdentityManager::GetReferencedAssembliesFromFile Method</span></span>
<span data-ttu-id="de340-103">Obtiene un [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) instancia que contiene una lista de ensamblados al que hace referencia el ensamblado en la ruta de acceso de archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="de340-103">Gets an [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) instance that contains a list of assemblies referenced by the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de340-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="de340-104">Syntax</span></span>  
  
```  
HRESULT GetReferencedAssembliesFromFile (  
    [in]  LPCWSTR pwzFilePath,  
    [in]  DWORD   dwFlags,  
    [in]  ICLRAssemblyReferenceList   *pExcludeAssembliesList,  
    [out] ICLRReferenceAssemblyEnum  **ppReferenceEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="de340-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="de340-105">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="de340-106">[in] La ruta de acceso al ensamblado que se debe evaluar.</span><span class="sxs-lookup"><span data-stu-id="de340-106">[in] The path to the assembly to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="de340-107">[in] Se proporciona para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="de340-107">[in] Provided for future extensibility.</span></span> <span data-ttu-id="de340-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT es el único valor admitido por la versión actual de common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="de340-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pExcludeAssembliesList`  
 <span data-ttu-id="de340-109">[in] Un puntero a un [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) objeto que representa los ensamblados que se deben excluir de `ppReferenceEnum`.</span><span class="sxs-lookup"><span data-stu-id="de340-109">[in] A pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) object that represents assemblies that should be excluded from `ppReferenceEnum`.</span></span>  
  
 `ppReferenceEnum`  
 <span data-ttu-id="de340-110">[out] Un puntero a la dirección de un `ICLRReferenceAssemblyEnum` objeto que contiene datos de identidad de ensamblado para los ensamblados al que hace referencia el ensamblado en `pwzFilePath`, excluyendo los ensamblados representados por `pExcludeAssembliesList`.</span><span class="sxs-lookup"><span data-stu-id="de340-110">[out] A pointer to the address of an `ICLRReferenceAssemblyEnum` object that contains assembly identity data for the assemblies referenced by the assembly at `pwzFilePath`, excluding the assemblies represented by `pExcludeAssembliesList`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="de340-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="de340-111">Return Value</span></span>  
  
|<span data-ttu-id="de340-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="de340-112">HRESULT</span></span>|<span data-ttu-id="de340-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="de340-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="de340-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="de340-114">S_OK</span></span>|<span data-ttu-id="de340-115">El método se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="de340-115">The method returned successfully.</span></span>|  
|<span data-ttu-id="de340-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="de340-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="de340-117">El CLR no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="de340-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="de340-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="de340-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="de340-119">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="de340-119">The call timed out.</span></span>|  
|<span data-ttu-id="de340-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="de340-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="de340-121">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="de340-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="de340-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="de340-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="de340-123">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="de340-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="de340-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="de340-124">E_FAIL</span></span>|<span data-ttu-id="de340-125">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="de340-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="de340-126">Si el método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="de340-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="de340-127">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="de340-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="de340-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="de340-128">Remarks</span></span>  
 <span data-ttu-id="de340-129">El llamador puede excluir un conjunto de referencias de ensamblado conocidas de la lista devuelta.</span><span class="sxs-lookup"><span data-stu-id="de340-129">The caller can choose to exclude a set of known assembly references from the returned list.</span></span> <span data-ttu-id="de340-130">Este conjunto se define por la `pExcludeAssembliesList` parámetro.</span><span class="sxs-lookup"><span data-stu-id="de340-130">This set is defined by the `pExcludeAssembliesList` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de340-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="de340-131">Requirements</span></span>  
 <span data-ttu-id="de340-132">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="de340-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de340-133">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="de340-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="de340-134">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="de340-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="de340-135">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de340-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de340-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="de340-136">See Also</span></span>  
 [<span data-ttu-id="de340-137">ICLRAssemblyIdentityManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="de340-137">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="de340-138">ICLRAssemblyReferenceList (interfaz)</span><span class="sxs-lookup"><span data-stu-id="de340-138">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="de340-139">ICLRReferenceAssemblyEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="de340-139">ICLRReferenceAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)
