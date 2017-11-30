---
title: "IHostTask::Join (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTask.Join
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTask::Join
helpviewer_keywords:
- IHostTask::Join method [.NET Framework hosting]
- Join method, IHostTask interface [.NET Framework hosting]
ms.assetid: 2cffcc52-19e0-4ced-a440-fc7375078ac9
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b5dbfcfc87a520925f36e09d4f2d21dbffadfe1e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ihosttaskjoin-method"></a><span data-ttu-id="33f2a-102">IHostTask::Join (Método)</span><span class="sxs-lookup"><span data-stu-id="33f2a-102">IHostTask::Join Method</span></span>
<span data-ttu-id="33f2a-103">La tarea que realiza la llamada se bloquea hasta que finaliza la tarea representada por el actual [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) completa de la instancia, se agota el tiempo especificado, o [IHostTask:: Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) se llama.</span><span class="sxs-lookup"><span data-stu-id="33f2a-103">Blocks the calling task until the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance completes, the specified time interval elapses, or [IHostTask::Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) is called.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33f2a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="33f2a-104">Syntax</span></span>  
  
```  
HRESULT Join (  
    [in] DWORD milliseconds,  
    [in] DWORD option  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="33f2a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="33f2a-105">Parameters</span></span>  
 `milliseconds`  
 <span data-ttu-id="33f2a-106">[in] El intervalo de tiempo, en milisegundos, para esperar a que finalice la tarea.</span><span class="sxs-lookup"><span data-stu-id="33f2a-106">[in] The time interval, in milliseconds, to wait for the task to terminate.</span></span> <span data-ttu-id="33f2a-107">Si este intervalo transcurre antes de que finalice la tarea, se desbloquea la tarea que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="33f2a-107">If this interval elapses before the task terminates, the calling task unblocks.</span></span>  
  
 `option`  
 <span data-ttu-id="33f2a-108">[in] Uno de los [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) valores.</span><span class="sxs-lookup"><span data-stu-id="33f2a-108">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values.</span></span> <span data-ttu-id="33f2a-109">Un valor de WAIT_ALERTABLE indica al host que reactivar la tarea si `Alert` se llama antes de `milliseconds` transcurre.</span><span class="sxs-lookup"><span data-stu-id="33f2a-109">A value of WAIT_ALERTABLE instructs the host to wake the task if `Alert` is called before `milliseconds` elapses.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="33f2a-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="33f2a-110">Return Value</span></span>  
  
|<span data-ttu-id="33f2a-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="33f2a-111">HRESULT</span></span>|<span data-ttu-id="33f2a-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="33f2a-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="33f2a-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="33f2a-113">S_OK</span></span>|<span data-ttu-id="33f2a-114">`Join`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="33f2a-114">`Join` returned successfully.</span></span>|  
|<span data-ttu-id="33f2a-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="33f2a-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="33f2a-116">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="33f2a-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="33f2a-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="33f2a-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="33f2a-118">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="33f2a-118">The call timed out.</span></span>|  
|<span data-ttu-id="33f2a-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="33f2a-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="33f2a-120">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="33f2a-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="33f2a-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="33f2a-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="33f2a-122">Se canceló un evento mientras un subproceso bloqueado o fibra estuvo esperando en la base de datos o actual `IHostTask` instancia no está asociada a una tarea.</span><span class="sxs-lookup"><span data-stu-id="33f2a-122">An event was canceled while a blocked thread or fiber was waiting on it, or the current `IHostTask` instance is not associated with a task.</span></span>|  
|<span data-ttu-id="33f2a-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="33f2a-123">E_FAIL</span></span>|<span data-ttu-id="33f2a-124">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="33f2a-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="33f2a-125">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="33f2a-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="33f2a-126">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="33f2a-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="33f2a-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="33f2a-127">Requirements</span></span>  
 <span data-ttu-id="33f2a-128">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33f2a-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33f2a-129">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="33f2a-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="33f2a-130">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="33f2a-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="33f2a-131">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33f2a-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33f2a-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="33f2a-132">See Also</span></span>  
 [<span data-ttu-id="33f2a-133">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="33f2a-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="33f2a-134">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="33f2a-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="33f2a-135">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="33f2a-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="33f2a-136">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="33f2a-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="33f2a-137">WAIT_OPTION (enumeración)</span><span class="sxs-lookup"><span data-stu-id="33f2a-137">WAIT_OPTION Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md)
