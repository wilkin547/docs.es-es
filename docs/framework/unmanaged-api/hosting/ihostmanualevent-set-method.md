---
title: "IHostManualEvent::Set (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostManualEvent.Set
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostManualEvent::Set
helpviewer_keywords:
- Set method, IHostManualEvent interface [.NET Framework hosting]
- IHostManualEvent::Set method [.NET Framework hosting]
ms.assetid: e930c174-f71d-4faa-bb59-f0fb3df4d77b
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 30dcb7232d6e0f7d42de48fefd2fbb9433a50405
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ihostmanualeventset-method"></a><span data-ttu-id="d831f-102">IHostManualEvent::Set (Método)</span><span class="sxs-lookup"><span data-stu-id="d831f-102">IHostManualEvent::Set Method</span></span>
<span data-ttu-id="d831f-103">Establece la actual [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instancia en un estado señalado.</span><span class="sxs-lookup"><span data-stu-id="d831f-103">Sets the current [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance to a signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d831f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d831f-104">Syntax</span></span>  
  
```  
HRESULT Set ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="d831f-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d831f-105">Return Value</span></span>  
  
|<span data-ttu-id="d831f-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d831f-106">HRESULT</span></span>|<span data-ttu-id="d831f-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="d831f-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d831f-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="d831f-108">S_OK</span></span>|<span data-ttu-id="d831f-109">`Set`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="d831f-109">`Set` returned successfully.</span></span>|  
|<span data-ttu-id="d831f-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d831f-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d831f-111">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="d831f-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d831f-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d831f-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d831f-113">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="d831f-113">The call timed out.</span></span>|  
|<span data-ttu-id="d831f-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d831f-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d831f-115">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="d831f-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d831f-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d831f-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d831f-117">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="d831f-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d831f-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d831f-118">E_FAIL</span></span>|<span data-ttu-id="d831f-119">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="d831f-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d831f-120">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="d831f-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d831f-121">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d831f-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d831f-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d831f-122">Requirements</span></span>  
 <span data-ttu-id="d831f-123">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d831f-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d831f-124">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d831f-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d831f-125">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d831f-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d831f-126">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d831f-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d831f-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="d831f-127">See Also</span></span>  
 [<span data-ttu-id="d831f-128">ICLRSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d831f-128">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="d831f-129">IHostAutoEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d831f-129">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="d831f-130">IHostManualEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d831f-130">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 [<span data-ttu-id="d831f-131">IHostSemaphore (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d831f-131">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 [<span data-ttu-id="d831f-132">IHostSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d831f-132">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
