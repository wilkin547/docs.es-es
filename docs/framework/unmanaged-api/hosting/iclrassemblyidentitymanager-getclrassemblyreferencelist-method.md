---
title: ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList (Método)
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetCLRAssemblyReferenceList
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList
helpviewer_keywords:
- GetClrAssemblyReferenceList method [.NET Framework hosting]
- ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList method [.NET Framework hosting]
ms.assetid: cb5ffae5-287b-4a87-9ca8-7ce3ae0601b7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 72bfb896ccff23938a4fc218fb1f95eebcf5bb93
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67773508"
---
# <a name="iclrassemblyidentitymanagergetclrassemblyreferencelist-method"></a><span data-ttu-id="43fd7-102">ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList (Método)</span><span class="sxs-lookup"><span data-stu-id="43fd7-102">ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList Method</span></span>
<span data-ttu-id="43fd7-103">Obtiene un puntero de interfaz a un [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) instancia desde la lista proporcionada de identidades de ensamblado parciales.</span><span class="sxs-lookup"><span data-stu-id="43fd7-103">Gets an interface pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) instance from the supplied list of partial assembly identities.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43fd7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="43fd7-104">Syntax</span></span>  
  
```cpp  
HRESULT  GetCLRAssemblyReferenceList (  
    [in] LPCWSTR *ppwzAssemblyReferences,  
    [in] DWORD    dwNumOfReferences,  
    [out] ICLRAssemblyReferenceList **ppReferenceList  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="43fd7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="43fd7-105">Parameters</span></span>  
 `ppwzAssemblyReferences`  
 <span data-ttu-id="43fd7-106">[in] Una matriz de cadenas terminadas en null con el formato "nombre de propiedad = valor..." que especifica una lista de identidades de ensamblado parciales.</span><span class="sxs-lookup"><span data-stu-id="43fd7-106">[in] An array of null-terminated strings in the form "name, property=value..." that specify a list of partial assembly identities.</span></span>  
  
 `dwNumOfReferences`  
 <span data-ttu-id="43fd7-107">[in] El número de elementos de `ppwzAssemblyReferences`.</span><span class="sxs-lookup"><span data-stu-id="43fd7-107">[in] The number of items in `ppwzAssemblyReferences`.</span></span>  
  
 `ppReferenceList`  
 <span data-ttu-id="43fd7-108">[out] Un puntero de interfaz a un `ICLRAssemblyReferenceList` objeto que contiene los datos de identidad de ensamblado de la lista de ensamblados especificados en `ppwzAssemblyReferences`.</span><span class="sxs-lookup"><span data-stu-id="43fd7-108">[out] An interface pointer to an `ICLRAssemblyReferenceList` object that contains the assembly identity data for the list of assemblies specified in `ppwzAssemblyReferences`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="43fd7-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="43fd7-109">Return Value</span></span>  
  
|<span data-ttu-id="43fd7-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="43fd7-110">HRESULT</span></span>|<span data-ttu-id="43fd7-111">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="43fd7-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="43fd7-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="43fd7-112">S_OK</span></span>|<span data-ttu-id="43fd7-113">El método se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="43fd7-113">The method returned successfully.</span></span>|  
|<span data-ttu-id="43fd7-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="43fd7-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="43fd7-115">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="43fd7-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="43fd7-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="43fd7-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="43fd7-117">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="43fd7-117">The call timed out.</span></span>|  
|<span data-ttu-id="43fd7-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="43fd7-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="43fd7-119">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="43fd7-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="43fd7-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="43fd7-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="43fd7-121">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="43fd7-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="43fd7-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="43fd7-122">E_FAIL</span></span>|<span data-ttu-id="43fd7-123">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="43fd7-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="43fd7-124">Si el método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="43fd7-124">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="43fd7-125">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="43fd7-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="43fd7-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="43fd7-126">Requirements</span></span>  
 <span data-ttu-id="43fd7-127">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43fd7-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43fd7-128">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="43fd7-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="43fd7-129">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="43fd7-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="43fd7-130">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43fd7-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43fd7-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="43fd7-131">See also</span></span>

- [<span data-ttu-id="43fd7-132">ICLRAssemblyIdentityManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="43fd7-132">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="43fd7-133">ICLRAssemblyReferenceList (interfaz)</span><span class="sxs-lookup"><span data-stu-id="43fd7-133">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
