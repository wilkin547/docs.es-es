---
title: "ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRAssemblyIdentityManager.GetCLRAssemblyReferenceList
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList
helpviewer_keywords:
- GetClrAssemblyReferenceList method [.NET Framework hosting]
- ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList method [.NET Framework hosting]
ms.assetid: cb5ffae5-287b-4a87-9ca8-7ce3ae0601b7
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: eefe5ff68c7bd428c18729dcbd792b4c3cb64c2e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="iclrassemblyidentitymanagergetclrassemblyreferencelist-method"></a><span data-ttu-id="b4a33-102">ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList (Método)</span><span class="sxs-lookup"><span data-stu-id="b4a33-102">ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList Method</span></span>
<span data-ttu-id="b4a33-103">Obtiene un puntero de interfaz a una [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) instancia de la lista proporcionada de identidades de ensamblado parciales.</span><span class="sxs-lookup"><span data-stu-id="b4a33-103">Gets an interface pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) instance from the supplied list of partial assembly identities.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4a33-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b4a33-104">Syntax</span></span>  
  
```  
HRESULT  GetCLRAssemblyReferenceList (  
    [in] LPCWSTR *ppwzAssemblyReferences,  
    [in] DWORD    dwNumOfReferences,  
    [out] ICLRAssemblyReferenceList **ppReferenceList  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b4a33-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b4a33-105">Parameters</span></span>  
 `ppwzAssemblyReferences`  
 <span data-ttu-id="b4a33-106">[in] Una matriz de cadenas terminadas en null con el formato "nombre de propiedad = valor..." que especifican una lista de identidades de ensamblado parciales.</span><span class="sxs-lookup"><span data-stu-id="b4a33-106">[in] An array of null-terminated strings in the form "name, property=value..." that specify a list of partial assembly identities.</span></span>  
  
 `dwNumOfReferences`  
 <span data-ttu-id="b4a33-107">[in] El número de elementos de `ppwzAssemblyReferences`.</span><span class="sxs-lookup"><span data-stu-id="b4a33-107">[in] The number of items in `ppwzAssemblyReferences`.</span></span>  
  
 `ppReferenceList`  
 <span data-ttu-id="b4a33-108">[out] Un puntero de interfaz a una `ICLRAssemblyReferenceList` objeto que contiene los datos de identidad de ensamblado para obtener la lista de ensamblados especificados en `ppwzAssemblyReferences`.</span><span class="sxs-lookup"><span data-stu-id="b4a33-108">[out] An interface pointer to an `ICLRAssemblyReferenceList` object that contains the assembly identity data for the list of assemblies specified in `ppwzAssemblyReferences`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b4a33-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b4a33-109">Return Value</span></span>  
  
|<span data-ttu-id="b4a33-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b4a33-110">HRESULT</span></span>|<span data-ttu-id="b4a33-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="b4a33-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b4a33-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="b4a33-112">S_OK</span></span>|<span data-ttu-id="b4a33-113">El método se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="b4a33-113">The method returned successfully.</span></span>|  
|<span data-ttu-id="b4a33-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b4a33-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b4a33-115">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="b4a33-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b4a33-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b4a33-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b4a33-117">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="b4a33-117">The call timed out.</span></span>|  
|<span data-ttu-id="b4a33-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b4a33-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b4a33-119">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="b4a33-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b4a33-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b4a33-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b4a33-121">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="b4a33-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b4a33-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b4a33-122">E_FAIL</span></span>|<span data-ttu-id="b4a33-123">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="b4a33-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b4a33-124">Si el método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="b4a33-124">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b4a33-125">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b4a33-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b4a33-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b4a33-126">Requirements</span></span>  
 <span data-ttu-id="b4a33-127">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4a33-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4a33-128">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b4a33-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b4a33-129">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b4a33-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b4a33-130">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4a33-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4a33-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="b4a33-131">See Also</span></span>  
 [<span data-ttu-id="b4a33-132">ICLRAssemblyIdentityManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b4a33-132">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="b4a33-133">ICLRAssemblyReferenceList (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b4a33-133">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
