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
ms.openlocfilehash: 9ae9a8e9e26f05675611ac4c6acd8ecfe5704b0c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61760199"
---
# <a name="ihostassemblymanagergetnonhoststoreassemblies-method"></a><span data-ttu-id="4d93d-102">IHostAssemblyManager::GetNonHostStoreAssemblies (Método)</span><span class="sxs-lookup"><span data-stu-id="4d93d-102">IHostAssemblyManager::GetNonHostStoreAssemblies Method</span></span>
<span data-ttu-id="4d93d-103">Obtiene un puntero de interfaz a un [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) que representa la lista de ensamblados que el host espera common language runtime (CLR) para cargar.</span><span class="sxs-lookup"><span data-stu-id="4d93d-103">Gets an interface pointer to an [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) that represents the list of assemblies that the host expects the common language runtime (CLR) to load.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d93d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4d93d-104">Syntax</span></span>  
  
```  
HRESULT GetNonHostStoreAssemblies (  
    [out] ICLRAssemblyReferenceList **ppReferenceList  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4d93d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4d93d-105">Parameters</span></span>  
 `ppReferenceList`  
 <span data-ttu-id="4d93d-106">[out] Un puntero a la dirección de un `ICLRAssemblyReferenceList` que contiene una lista de referencias a ensamblados que el host espera que CLR cargue.</span><span class="sxs-lookup"><span data-stu-id="4d93d-106">[out] A pointer to the address of an `ICLRAssemblyReferenceList` that contains a list of references to assemblies that the host expects the CLR to load.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4d93d-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4d93d-107">Return Value</span></span>  
  
|<span data-ttu-id="4d93d-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4d93d-108">HRESULT</span></span>|<span data-ttu-id="4d93d-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="4d93d-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4d93d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="4d93d-110">S_OK</span></span>|<span data-ttu-id="4d93d-111">`GetNonHostStoreAssemblies` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="4d93d-111">`GetNonHostStoreAssemblies` returned successfully.</span></span>|  
|<span data-ttu-id="4d93d-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4d93d-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4d93d-113">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="4d93d-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4d93d-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4d93d-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4d93d-115">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="4d93d-115">The call timed out.</span></span>|  
|<span data-ttu-id="4d93d-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4d93d-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4d93d-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="4d93d-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4d93d-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4d93d-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4d93d-119">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="4d93d-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4d93d-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4d93d-120">E_FAIL</span></span>|<span data-ttu-id="4d93d-121">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="4d93d-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4d93d-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="4d93d-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4d93d-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="4d93d-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="4d93d-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="4d93d-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="4d93d-125">No había suficiente memoria disponible para crear la lista de referencias para solicitado `ICLRAssemblyReferenceList`.</span><span class="sxs-lookup"><span data-stu-id="4d93d-125">Not enough memory was available to create the list of references for the requested `ICLRAssemblyReferenceList`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4d93d-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4d93d-126">Remarks</span></span>  
 <span data-ttu-id="4d93d-127">El CLR resuelve las referencias mediante el siguiente conjunto de instrucciones:</span><span class="sxs-lookup"><span data-stu-id="4d93d-127">The CLR resolves references using the following set of guidelines:</span></span>  
  
- <span data-ttu-id="4d93d-128">En primer lugar, consulta la lista de referencias de ensamblado devuelto por `GetNonHostStoreAssemblies`.</span><span class="sxs-lookup"><span data-stu-id="4d93d-128">First, it consults the list of assembly references returned by `GetNonHostStoreAssemblies`.</span></span>  
  
- <span data-ttu-id="4d93d-129">Si el ensamblado aparece en la lista, el CLR se enlaza a él normalmente.</span><span class="sxs-lookup"><span data-stu-id="4d93d-129">If the assembly appears in the list, the CLR binds to it normally.</span></span>  
  
- <span data-ttu-id="4d93d-130">Si el ensamblado no aparece en la lista y el host ha proporcionado una implementación de [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md), CLR llama a [IHostAssemblyStore:: ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) para permitir que el host proporcione la ensamblado que se va a enlazar.</span><span class="sxs-lookup"><span data-stu-id="4d93d-130">If the assembly does not appear in the list and the host has provided an implementation of [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md), the CLR calls [IHostAssemblyStore::ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) to allow the host to supply the assembly to bind to.</span></span>  
  
- <span data-ttu-id="4d93d-131">En caso contrario, el CLR no se puede enlazar al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="4d93d-131">Otherwise, the CLR fails to bind to the assembly.</span></span>  
  
 <span data-ttu-id="4d93d-132">Si el host establece `ppReferenceList` en null, CLR sondea primero llama la caché global de ensamblados, `ProvideAssembly`y, a continuación, sondea la base de la aplicación para resolver una referencia de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="4d93d-132">If the host sets `ppReferenceList` to null, the CLR first probes the global assembly cache, calls `ProvideAssembly`, and then probes the application base to resolve an assembly reference.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4d93d-133">En la inicialización, CLR llama `GetNonHostStoreAssemblies` una sola vez.</span><span class="sxs-lookup"><span data-stu-id="4d93d-133">Upon initialization, the CLR calls `GetNonHostStoreAssemblies` only once.</span></span> <span data-ttu-id="4d93d-134">No se llama al método nuevo.</span><span class="sxs-lookup"><span data-stu-id="4d93d-134">The method is not called again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d93d-135">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4d93d-135">Requirements</span></span>  
 <span data-ttu-id="4d93d-136">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4d93d-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d93d-137">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4d93d-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4d93d-138">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4d93d-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4d93d-139">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d93d-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d93d-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="4d93d-140">See also</span></span>

- [<span data-ttu-id="4d93d-141">ICLRAssemblyReferenceList (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4d93d-141">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="4d93d-142">IHostAssemblyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4d93d-142">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="4d93d-143">IHostAssemblyStore (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4d93d-143">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
