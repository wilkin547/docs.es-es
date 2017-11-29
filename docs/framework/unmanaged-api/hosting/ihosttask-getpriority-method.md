---
title: "IHostTask::GetPriority (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTask.GetPriority
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTask::GetPriority
helpviewer_keywords:
- GetPriority method [.NET Framework hosting]
- IHostTask::GetPriority method [.NET Framework hosting]
ms.assetid: 4b463cd6-77c1-4f9a-8518-346ad8fc4b70
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ba32e8c442042f59c8346d68cef7d9f6678ae7dc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ihosttaskgetpriority-method"></a><span data-ttu-id="6fee6-102">IHostTask::GetPriority (Método)</span><span class="sxs-lookup"><span data-stu-id="6fee6-102">IHostTask::GetPriority Method</span></span>
<span data-ttu-id="6fee6-103">Obtiene el nivel de prioridad de subproceso de la tarea representada por el actual [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instancia.</span><span class="sxs-lookup"><span data-stu-id="6fee6-103">Gets the thread priority level of the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fee6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6fee6-104">Syntax</span></span>  
  
```  
HRESULT GetPriority (  
    [out] int *pPriority  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6fee6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6fee6-105">Parameters</span></span>  
 `pPriority`  
 <span data-ttu-id="6fee6-106">[out] Un puntero a un entero que indica el nivel de prioridad de subproceso de la tarea representada por el actual `IHostTask` instancia.</span><span class="sxs-lookup"><span data-stu-id="6fee6-106">[out] A pointer to an integer that indicates the thread priority level of the task represented by the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6fee6-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="6fee6-107">Return Value</span></span>  
  
|<span data-ttu-id="6fee6-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6fee6-108">HRESULT</span></span>|<span data-ttu-id="6fee6-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="6fee6-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6fee6-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="6fee6-110">S_OK</span></span>|<span data-ttu-id="6fee6-111">`GetPriority`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="6fee6-111">`GetPriority` returned successfully.</span></span>|  
|<span data-ttu-id="6fee6-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6fee6-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6fee6-113">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="6fee6-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6fee6-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6fee6-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6fee6-115">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="6fee6-115">The call timed out.</span></span>|  
|<span data-ttu-id="6fee6-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6fee6-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6fee6-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="6fee6-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6fee6-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6fee6-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6fee6-119">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="6fee6-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6fee6-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6fee6-120">E_FAIL</span></span>|<span data-ttu-id="6fee6-121">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="6fee6-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6fee6-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="6fee6-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6fee6-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="6fee6-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6fee6-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6fee6-124">Remarks</span></span>  
 <span data-ttu-id="6fee6-125">Definen los valores de nivel de prioridad de subproceso Win32 `SetThreadPriority` función.</span><span class="sxs-lookup"><span data-stu-id="6fee6-125">Thread priority level values are defined by the Win32 `SetThreadPriority` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6fee6-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6fee6-126">Requirements</span></span>  
 <span data-ttu-id="6fee6-127">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6fee6-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6fee6-128">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6fee6-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6fee6-129">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6fee6-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6fee6-130">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6fee6-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fee6-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="6fee6-131">See Also</span></span>  
 [<span data-ttu-id="6fee6-132">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6fee6-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="6fee6-133">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6fee6-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="6fee6-134">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6fee6-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="6fee6-135">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6fee6-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
