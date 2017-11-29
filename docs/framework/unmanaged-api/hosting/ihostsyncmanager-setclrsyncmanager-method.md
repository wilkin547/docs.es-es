---
title: "IHostSyncManager::SetCLRSyncManager (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSyncManager.SetCLRSyncManager
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSyncManager::SetCLRSyncManager
helpviewer_keywords:
- IHostSyncManager::SetCLRSyncManager method [.NET Framework hosting]
- SetCLRSyncManager method [.NET Framework hosting]
ms.assetid: 2b8bbe76-a45d-4989-bacb-11df42f8798c
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 45899e3cb6a08aef6a9b8df197541c4d0233d92d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ihostsyncmanagersetclrsyncmanager-method"></a><span data-ttu-id="582b0-102">IHostSyncManager::SetCLRSyncManager (Método)</span><span class="sxs-lookup"><span data-stu-id="582b0-102">IHostSyncManager::SetCLRSyncManager Method</span></span>
<span data-ttu-id="582b0-103">Establece el [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) instancia asociada con el actual [IHostSyncManager](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md) instancia.</span><span class="sxs-lookup"><span data-stu-id="582b0-103">Sets the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) instance to associate with the current [IHostSyncManager](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="582b0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="582b0-104">Syntax</span></span>  
  
```  
HRESULT SetCLRSyncManager (  
    [in] ICLRSyncManager *pManager  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="582b0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="582b0-105">Parameters</span></span>  
 `pManager`  
 <span data-ttu-id="582b0-106">[in] Un puntero a un `ICLRSyncManager` instancia proporcionada por common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="582b0-106">[in] A pointer to an `ICLRSyncManager` instance supplied by the common language runtime (CLR).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="582b0-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="582b0-107">Return Value</span></span>  
  
|<span data-ttu-id="582b0-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="582b0-108">HRESULT</span></span>|<span data-ttu-id="582b0-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="582b0-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="582b0-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="582b0-110">S_OK</span></span>|<span data-ttu-id="582b0-111">`SetCLRSyncManager`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="582b0-111">`SetCLRSyncManager` returned successfully.</span></span>|  
|<span data-ttu-id="582b0-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="582b0-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="582b0-113">El CLR no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="582b0-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="582b0-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="582b0-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="582b0-115">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="582b0-115">The call timed out.</span></span>|  
|<span data-ttu-id="582b0-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="582b0-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="582b0-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="582b0-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="582b0-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="582b0-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="582b0-119">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="582b0-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="582b0-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="582b0-120">E_FAIL</span></span>|<span data-ttu-id="582b0-121">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="582b0-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="582b0-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="582b0-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="582b0-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="582b0-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="582b0-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="582b0-124">Remarks</span></span>  
 <span data-ttu-id="582b0-125">Para facilitar la comunicación entre el host y CLR, las interfaces de hospedaje generalmente vienen en parejas.</span><span class="sxs-lookup"><span data-stu-id="582b0-125">To facilitate communication between the host and the CLR, hosting interfaces generally come in pairs.</span></span> <span data-ttu-id="582b0-126">Un miembro del par es implementado por el host y el CLR implementa el otro miembro.</span><span class="sxs-lookup"><span data-stu-id="582b0-126">One member of the pair is implemented by the host, and the other member is implemented by the CLR.</span></span> <span data-ttu-id="582b0-127">Como una implementación del host, el `IHostSyncManager` interfaz se corresponde con el `ICLRSyncManager` interfaz implementada por CLR.</span><span class="sxs-lookup"><span data-stu-id="582b0-127">As a host-side implementation, the `IHostSyncManager` interface corresponds to the `ICLRSyncManager` interface implemented by the CLR.</span></span> <span data-ttu-id="582b0-128">CLR llama `SetCLRSyncManager` para proporcionar un `ICLRSyncManager` instancia para el host se asocie con el actual `IHostSyncManager` instancia.</span><span class="sxs-lookup"><span data-stu-id="582b0-128">The CLR calls `SetCLRSyncManager` to supply an `ICLRSyncManager` instance for the host to associate with the current `IHostSyncManager` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="582b0-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="582b0-129">Requirements</span></span>  
 <span data-ttu-id="582b0-130">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="582b0-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="582b0-131">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="582b0-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="582b0-132">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="582b0-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="582b0-133">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="582b0-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="582b0-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="582b0-134">See Also</span></span>  
 [<span data-ttu-id="582b0-135">ICLRSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="582b0-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="582b0-136">IHostSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="582b0-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
