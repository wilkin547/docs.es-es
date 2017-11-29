---
title: "IHostAutoEvent::Set (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostAutoEvent.Set
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostAutoEvent::Set
helpviewer_keywords:
- Set method, IHostAutoEvent interface [.NET Framework hosting]
- IHostAutoEvent::Set method [.NET Framework hosting]
ms.assetid: 46becf3e-bc0e-4338-85c0-9ab0df76a1d0
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 07de2321c1c7760293c53ad77dd3bbdf7f82a564
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ihostautoeventset-method"></a><span data-ttu-id="d325d-102">IHostAutoEvent::Set (Método)</span><span class="sxs-lookup"><span data-stu-id="d325d-102">IHostAutoEvent::Set Method</span></span>
<span data-ttu-id="d325d-103">Establece la actual [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instancia en un estado señalado.</span><span class="sxs-lookup"><span data-stu-id="d325d-103">Sets the current [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance to a signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d325d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d325d-104">Syntax</span></span>  
  
```  
HRESULT Set ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="d325d-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d325d-105">Return Value</span></span>  
  
|<span data-ttu-id="d325d-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d325d-106">HRESULT</span></span>|<span data-ttu-id="d325d-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="d325d-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d325d-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="d325d-108">S_OK</span></span>|<span data-ttu-id="d325d-109">`Set`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="d325d-109">`Set` returned successfully.</span></span>|  
|<span data-ttu-id="d325d-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d325d-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d325d-111">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="d325d-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d325d-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d325d-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d325d-113">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="d325d-113">The call timed out.</span></span>|  
|<span data-ttu-id="d325d-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d325d-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d325d-115">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="d325d-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d325d-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d325d-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d325d-117">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="d325d-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d325d-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d325d-118">E_FAIL</span></span>|<span data-ttu-id="d325d-119">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="d325d-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d325d-120">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="d325d-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d325d-121">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d325d-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d325d-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d325d-122">Requirements</span></span>  
 <span data-ttu-id="d325d-123">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d325d-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d325d-124">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d325d-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d325d-125">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d325d-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d325d-126">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d325d-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d325d-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="d325d-127">See Also</span></span>  
 [<span data-ttu-id="d325d-128">ICLRSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d325d-128">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="d325d-129">IHostAutoEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d325d-129">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="d325d-130">IHostManualEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d325d-130">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 [<span data-ttu-id="d325d-131">IHostSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d325d-131">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
