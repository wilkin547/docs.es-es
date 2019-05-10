---
title: IHostAssemblyManager::GetNonHostStoreAssemblies (Método)
ms.date: 03/30/2017
api_name:
- IHostAssemblyManager.GetNonHostStoreAssemblies
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyManager::GetNonHostStoreAssemblies
helpviewer_keywords:
- IHostAssemblyManager::GetNonHostStoreAssemblies method [.NET Framework hosting]
- GetNonHostStoreAssemblies method [.NET Framework hosting]
ms.assetid: d2250b38-c76a-40ce-80c8-ba45149886e8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 750263f5620569ec1d51a4eebe7ea5d74bb84df2
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64650294"
---
# <a name="ihostassemblymanagergetnonhoststoreassemblies-method"></a><span data-ttu-id="d8958-102">IHostAssemblyManager::GetNonHostStoreAssemblies (Método)</span><span class="sxs-lookup"><span data-stu-id="d8958-102">IHostAssemblyManager::GetNonHostStoreAssemblies Method</span></span>
<span data-ttu-id="d8958-103">Obtiene un puntero de interfaz a un [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) que representa la lista de ensamblados que el host espera common language runtime (CLR) para cargar.</span><span class="sxs-lookup"><span data-stu-id="d8958-103">Gets an interface pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) that represents the list of assemblies that the host expects the common language runtime (CLR) to load.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8958-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d8958-104">Syntax</span></span>  
  
```  
HRESULT GetNonHostStoreAssemblies (  
    [out] ICLRAssemblyReferenceList **ppReferenceList  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d8958-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d8958-105">Parameters</span></span>  
 `ppReferenceList`  
 <span data-ttu-id="d8958-106">[out] Un puntero a la dirección de un `ICLRAssemblyReferenceList` que contiene una lista de referencias a ensamblados que el host espera que CLR cargue.</span><span class="sxs-lookup"><span data-stu-id="d8958-106">[out] A pointer to the address of an `ICLRAssemblyReferenceList` that contains a list of references to assemblies that the host expects the CLR to load.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d8958-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d8958-107">Return Value</span></span>  
  
|<span data-ttu-id="d8958-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d8958-108">HRESULT</span></span>|<span data-ttu-id="d8958-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="d8958-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d8958-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d8958-110">S_OK</span></span>|<span data-ttu-id="d8958-111">`GetNonHostStoreAssemblies` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="d8958-111">`GetNonHostStoreAssemblies` returned successfully.</span></span>|  
|<span data-ttu-id="d8958-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d8958-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d8958-113">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="d8958-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d8958-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d8958-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d8958-115">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="d8958-115">The call timed out.</span></span>|  
|<span data-ttu-id="d8958-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d8958-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d8958-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="d8958-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d8958-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d8958-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d8958-119">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="d8958-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d8958-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d8958-120">E_FAIL</span></span>|<span data-ttu-id="d8958-121">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="d8958-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d8958-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="d8958-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d8958-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d8958-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="d8958-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="d8958-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="d8958-125">No había suficiente memoria disponible para crear la lista de referencias para solicitado `ICLRAssemblyReferenceList`.</span><span class="sxs-lookup"><span data-stu-id="d8958-125">Not enough memory was available to create the list of references for the requested `ICLRAssemblyReferenceList`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d8958-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d8958-126">Remarks</span></span>  
 <span data-ttu-id="d8958-127">El CLR resuelve las referencias mediante el siguiente conjunto de instrucciones:</span><span class="sxs-lookup"><span data-stu-id="d8958-127">The CLR resolves references using the following set of guidelines:</span></span>  
  
- <span data-ttu-id="d8958-128">En primer lugar, consulta la lista de referencias de ensamblado devuelto por `GetNonHostStoreAssemblies`.</span><span class="sxs-lookup"><span data-stu-id="d8958-128">First, it consults the list of assembly references returned by `GetNonHostStoreAssemblies`.</span></span>  
  
- <span data-ttu-id="d8958-129">Si el ensamblado aparece en la lista, el CLR se enlaza a él normalmente.</span><span class="sxs-lookup"><span data-stu-id="d8958-129">If the assembly appears in the list, the CLR binds to it normally.</span></span>  
  
- <span data-ttu-id="d8958-130">Si el ensamblado no aparece en la lista y el host ha proporcionado una implementación de [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md), CLR llama a [IHostAssemblyStore:: ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) para permitir que el host proporcione la ensamblado que se va a enlazar.</span><span class="sxs-lookup"><span data-stu-id="d8958-130">If the assembly does not appear in the list and the host has provided an implementation of [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md), the CLR calls [IHostAssemblyStore::ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) to allow the host to supply the assembly to bind to.</span></span>  
  
- <span data-ttu-id="d8958-131">En caso contrario, el CLR no se puede enlazar al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d8958-131">Otherwise, the CLR fails to bind to the assembly.</span></span>  
  
 <span data-ttu-id="d8958-132">Si el host establece `ppReferenceList` en null, CLR sondea primero llama la caché global de ensamblados, `ProvideAssembly`y, a continuación, sondea la base de la aplicación para resolver una referencia de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="d8958-132">If the host sets `ppReferenceList` to null, the CLR first probes the global assembly cache, calls `ProvideAssembly`, and then probes the application base to resolve an assembly reference.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d8958-133">En la inicialización, CLR llama `GetNonHostStoreAssemblies` una sola vez.</span><span class="sxs-lookup"><span data-stu-id="d8958-133">Upon initialization, the CLR calls `GetNonHostStoreAssemblies` only once.</span></span> <span data-ttu-id="d8958-134">No se llama al método nuevo.</span><span class="sxs-lookup"><span data-stu-id="d8958-134">The method is not called again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8958-135">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d8958-135">Requirements</span></span>  
 <span data-ttu-id="d8958-136">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8958-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8958-137">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d8958-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d8958-138">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d8958-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d8958-139">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8958-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8958-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="d8958-140">See also</span></span>

- [<span data-ttu-id="d8958-141">ICLRAssemblyReferenceList (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d8958-141">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="d8958-142">IHostAssemblyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d8958-142">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="d8958-143">IHostAssemblyStore (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d8958-143">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
