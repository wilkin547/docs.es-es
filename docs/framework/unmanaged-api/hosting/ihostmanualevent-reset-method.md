---
title: "IHostManualEvent::Reset (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostManualEvent.Reset
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostManualEvent::Reset
helpviewer_keywords:
- Reset method, IHostManualEvent interface [.NET Framework hosting]
- IHostManualEvent::Reset method [.NET Framework hosting]
ms.assetid: 0d101168-b5e3-49ce-90c7-85cf2db83c4c
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e41922cb1732fe4e6727408692bbc7b99288e6dd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ihostmanualeventreset-method"></a><span data-ttu-id="b2da9-102">IHostManualEvent::Reset (Método)</span><span class="sxs-lookup"><span data-stu-id="b2da9-102">IHostManualEvent::Reset Method</span></span>
<span data-ttu-id="b2da9-103">Restablece el actual [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instancia a un estado no señalado.</span><span class="sxs-lookup"><span data-stu-id="b2da9-103">Resets the current [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance to a non-signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2da9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b2da9-104">Syntax</span></span>  
  
```  
HRESULT Reset ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="b2da9-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b2da9-105">Return Value</span></span>  
  
|<span data-ttu-id="b2da9-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b2da9-106">HRESULT</span></span>|<span data-ttu-id="b2da9-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="b2da9-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b2da9-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="b2da9-108">S_OK</span></span>|<span data-ttu-id="b2da9-109">`Reset`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="b2da9-109">`Reset` returned successfully.</span></span>|  
|<span data-ttu-id="b2da9-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b2da9-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b2da9-111">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="b2da9-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b2da9-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b2da9-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b2da9-113">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="b2da9-113">The call timed out.</span></span>|  
|<span data-ttu-id="b2da9-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b2da9-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b2da9-115">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="b2da9-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b2da9-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b2da9-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b2da9-117">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="b2da9-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b2da9-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b2da9-118">E_FAIL</span></span>|<span data-ttu-id="b2da9-119">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="b2da9-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b2da9-120">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="b2da9-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b2da9-121">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b2da9-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b2da9-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b2da9-122">Requirements</span></span>  
 <span data-ttu-id="b2da9-123">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2da9-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2da9-124">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b2da9-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b2da9-125">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b2da9-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b2da9-126">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2da9-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2da9-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="b2da9-127">See Also</span></span>  
 [<span data-ttu-id="b2da9-128">ICLRSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b2da9-128">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="b2da9-129">IHostAutoEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b2da9-129">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="b2da9-130">IHostManualEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b2da9-130">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 [<span data-ttu-id="b2da9-131">IHostSemaphore (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b2da9-131">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 [<span data-ttu-id="b2da9-132">IHostSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b2da9-132">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
