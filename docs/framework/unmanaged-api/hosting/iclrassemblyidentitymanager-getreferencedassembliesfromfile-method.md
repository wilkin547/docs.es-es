---
title: ICLRAssemblyIdentityManager::GetReferencedAssembliesFromFile (Método)
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6ba3ea7fe7b0182971899066f2cee63804fddbd1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59127834"
---
# <a name="iclrassemblyidentitymanagergetreferencedassembliesfromfile-method"></a><span data-ttu-id="25879-102">ICLRAssemblyIdentityManager::GetReferencedAssembliesFromFile (Método)</span><span class="sxs-lookup"><span data-stu-id="25879-102">ICLRAssemblyIdentityManager::GetReferencedAssembliesFromFile Method</span></span>
<span data-ttu-id="25879-103">Obtiene un [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) instancia que contiene una lista de ensamblados al que hace referencia el ensamblado en la ruta de acceso de archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="25879-103">Gets an [ICLRReferenceAssemblyEnum](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md) instance that contains a list of assemblies referenced by the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25879-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="25879-104">Syntax</span></span>  
  
```  
HRESULT GetReferencedAssembliesFromFile (  
    [in]  LPCWSTR pwzFilePath,  
    [in]  DWORD   dwFlags,  
    [in]  ICLRAssemblyReferenceList   *pExcludeAssembliesList,  
    [out] ICLRReferenceAssemblyEnum  **ppReferenceEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="25879-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="25879-105">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="25879-106">[in] La ruta de acceso al ensamblado que se va a evaluar.</span><span class="sxs-lookup"><span data-stu-id="25879-106">[in] The path to the assembly to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="25879-107">[in] Se proporciona para extensibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="25879-107">[in] Provided for future extensibility.</span></span> <span data-ttu-id="25879-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT es el único valor compatible con la versión actual de common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="25879-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pExcludeAssembliesList`  
 <span data-ttu-id="25879-109">[in] Un puntero a un [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) objeto que representa los ensamblados que se deben excluir de `ppReferenceEnum`.</span><span class="sxs-lookup"><span data-stu-id="25879-109">[in] A pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) object that represents assemblies that should be excluded from `ppReferenceEnum`.</span></span>  
  
 `ppReferenceEnum`  
 <span data-ttu-id="25879-110">[out] Un puntero a la dirección de un `ICLRReferenceAssemblyEnum` objeto que contiene datos de identidad de ensamblado para los ensamblados que se hace referencia el ensamblado en `pwzFilePath`, excluyendo los ensamblados representados por `pExcludeAssembliesList`.</span><span class="sxs-lookup"><span data-stu-id="25879-110">[out] A pointer to the address of an `ICLRReferenceAssemblyEnum` object that contains assembly identity data for the assemblies referenced by the assembly at `pwzFilePath`, excluding the assemblies represented by `pExcludeAssembliesList`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="25879-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="25879-111">Return Value</span></span>  
  
|<span data-ttu-id="25879-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="25879-112">HRESULT</span></span>|<span data-ttu-id="25879-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="25879-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="25879-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="25879-114">S_OK</span></span>|<span data-ttu-id="25879-115">El método se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="25879-115">The method returned successfully.</span></span>|  
|<span data-ttu-id="25879-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="25879-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="25879-117">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="25879-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="25879-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="25879-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="25879-119">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="25879-119">The call timed out.</span></span>|  
|<span data-ttu-id="25879-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="25879-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="25879-121">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="25879-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="25879-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="25879-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="25879-123">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="25879-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="25879-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="25879-124">E_FAIL</span></span>|<span data-ttu-id="25879-125">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="25879-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="25879-126">Si el método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="25879-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="25879-127">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="25879-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="25879-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="25879-128">Remarks</span></span>  
 <span data-ttu-id="25879-129">El llamador puede excluir un conjunto de referencias de ensamblados conocidos de la lista devuelta.</span><span class="sxs-lookup"><span data-stu-id="25879-129">The caller can choose to exclude a set of known assembly references from the returned list.</span></span> <span data-ttu-id="25879-130">Este conjunto se define mediante el `pExcludeAssembliesList` parámetro.</span><span class="sxs-lookup"><span data-stu-id="25879-130">This set is defined by the `pExcludeAssembliesList` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25879-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="25879-131">Requirements</span></span>  
 <span data-ttu-id="25879-132">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="25879-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25879-133">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="25879-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="25879-134">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="25879-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="25879-135">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="25879-135">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="25879-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="25879-136">See also</span></span>

- [<span data-ttu-id="25879-137">ICLRAssemblyIdentityManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="25879-137">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="25879-138">ICLRAssemblyReferenceList (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="25879-138">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="25879-139">ICLRReferenceAssemblyEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="25879-139">ICLRReferenceAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)
