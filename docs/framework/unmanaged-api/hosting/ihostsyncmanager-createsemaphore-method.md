---
title: IHostSyncManager::CreateSemaphore (Método)
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateSemaphore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateSemaphore
helpviewer_keywords:
- CreateSemaphore method [.NET Framework hosting]
- IHostSyncManager::CreateSemaphore method [.NET Framework hosting]
ms.assetid: 37679e94-5ff9-4173-8fa5-457febeb89bf
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3ef9a5896c2ecc54b7fd48670f751d193ac74554
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59138624"
---
# <a name="ihostsyncmanagercreatesemaphore-method"></a><span data-ttu-id="d8b38-102">IHostSyncManager::CreateSemaphore (Método)</span><span class="sxs-lookup"><span data-stu-id="d8b38-102">IHostSyncManager::CreateSemaphore Method</span></span>
<span data-ttu-id="d8b38-103">Crea un [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) objeto de common language runtime (CLR) que se usará como un semáforo para los eventos de espera.</span><span class="sxs-lookup"><span data-stu-id="d8b38-103">Creates an [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) object for the common language runtime (CLR) to use as a semaphore for wait events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8b38-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d8b38-104">Syntax</span></span>  
  
```  
HRESULT CreateSemaphore (  
    [in]  DWORD dwInitial,  
    [in]  DWORD dwMax,  
    [out] IHostSemaphore **ppSemaphore  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d8b38-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d8b38-105">Parameters</span></span>  
 `dwInitial`  
 <span data-ttu-id="d8b38-106">[in] El recuento inicial de `ppSemaphore`.</span><span class="sxs-lookup"><span data-stu-id="d8b38-106">[in] The initial count for `ppSemaphore`.</span></span>  
  
 `dwMax`  
 <span data-ttu-id="d8b38-107">[in] El número máximo de `ppSemaphore`.</span><span class="sxs-lookup"><span data-stu-id="d8b38-107">[in] The maximum count for `ppSemaphore`.</span></span>  
  
 `ppSemaphore`  
 <span data-ttu-id="d8b38-108">[out] Un puntero a la dirección de un `IHostSemaphore` de instancia, o null si no se pudo crear el semáforo.</span><span class="sxs-lookup"><span data-stu-id="d8b38-108">[out] A pointer to the address of an `IHostSemaphore` instance, or null if the semaphore could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d8b38-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d8b38-109">Return Value</span></span>  
  
|<span data-ttu-id="d8b38-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d8b38-110">HRESULT</span></span>|<span data-ttu-id="d8b38-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="d8b38-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d8b38-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="d8b38-112">S_OK</span></span>|<span data-ttu-id="d8b38-113">`CreateSemaphore` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="d8b38-113">`CreateSemaphore` returned successfully.</span></span>|  
|<span data-ttu-id="d8b38-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d8b38-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d8b38-115">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="d8b38-115">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d8b38-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d8b38-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d8b38-117">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="d8b38-117">The call timed out.</span></span>|  
|<span data-ttu-id="d8b38-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d8b38-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d8b38-119">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="d8b38-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d8b38-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d8b38-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d8b38-121">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="d8b38-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d8b38-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d8b38-122">E_FAIL</span></span>|<span data-ttu-id="d8b38-123">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="d8b38-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d8b38-124">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="d8b38-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d8b38-125">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d8b38-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="d8b38-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="d8b38-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="d8b38-127">No había suficiente memoria disponible para crear el objeto de evento solicitado.</span><span class="sxs-lookup"><span data-stu-id="d8b38-127">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d8b38-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d8b38-128">Remarks</span></span>  
 <span data-ttu-id="d8b38-129">`CreateSemaphore` refleja la función de Win32 que tiene el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="d8b38-129">`CreateSemaphore` mirrors the Win32 function that has the same name.</span></span> <span data-ttu-id="d8b38-130">El `dwInitial` y `dwMax` parámetros usan la misma semántica para el recuento del semáforo como Win32 `lInitialCount` y `lMaximumCount` parámetros, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="d8b38-130">The `dwInitial` and `dwMax` parameters use the same semantics for the semaphore count as the Win32 `lInitialCount` and `lMaximumCount` parameters, respectively.</span></span> <span data-ttu-id="d8b38-131">`dwInitial` debe estar entre cero y `dwMax`, ambos inclusive.</span><span class="sxs-lookup"><span data-stu-id="d8b38-131">`dwInitial` must be between zero and `dwMax`, inclusive.</span></span> <span data-ttu-id="d8b38-132">`dwMax` Debe ser mayor que cero.</span><span class="sxs-lookup"><span data-stu-id="d8b38-132">`dwMax` must be greater than zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8b38-133">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d8b38-133">Requirements</span></span>  
 <span data-ttu-id="d8b38-134">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8b38-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8b38-135">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d8b38-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d8b38-136">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d8b38-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d8b38-137">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8b38-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8b38-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="d8b38-138">See also</span></span>

- [<span data-ttu-id="d8b38-139">ICLRSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d8b38-139">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="d8b38-140">IHostSemaphore (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d8b38-140">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="d8b38-141">IHostSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d8b38-141">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
