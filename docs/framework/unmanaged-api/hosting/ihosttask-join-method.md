---
title: IHostTask::Join (Método)
ms.date: 03/30/2017
api_name:
- IHostTask.Join
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::Join
helpviewer_keywords:
- IHostTask::Join method [.NET Framework hosting]
- Join method, IHostTask interface [.NET Framework hosting]
ms.assetid: 2cffcc52-19e0-4ced-a440-fc7375078ac9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4373fc4e8a4c414c40e8d3c5547b5998b9300348
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59170776"
---
# <a name="ihosttaskjoin-method"></a><span data-ttu-id="8b4f5-102">IHostTask::Join (Método)</span><span class="sxs-lookup"><span data-stu-id="8b4f5-102">IHostTask::Join Method</span></span>
<span data-ttu-id="8b4f5-103">Bloquea la tarea que realiza la llamada hasta que la tarea representada por el actual [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instancia se haya completado, transcurre el intervalo de tiempo especificado, o [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) se llama.</span><span class="sxs-lookup"><span data-stu-id="8b4f5-103">Blocks the calling task until the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance completes, the specified time interval elapses, or [IHostTask::Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) is called.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b4f5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8b4f5-104">Syntax</span></span>  
  
```  
HRESULT Join (  
    [in] DWORD milliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8b4f5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8b4f5-105">Parameters</span></span>  
 `milliseconds`  
 <span data-ttu-id="8b4f5-106">[in] El intervalo de tiempo, en milisegundos, que espere a que finalice la tarea.</span><span class="sxs-lookup"><span data-stu-id="8b4f5-106">[in] The time interval, in milliseconds, to wait for the task to terminate.</span></span> <span data-ttu-id="8b4f5-107">Si este intervalo transcurre antes de que termine la tarea, se desbloquea la tarea que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="8b4f5-107">If this interval elapses before the task terminates, the calling task unblocks.</span></span>  
  
 `option`  
 <span data-ttu-id="8b4f5-108">[in] Uno de los [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) valores.</span><span class="sxs-lookup"><span data-stu-id="8b4f5-108">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values.</span></span> <span data-ttu-id="8b4f5-109">Un valor de WAIT_ALERTABLE indica al host que reactivar la tarea si `Alert` se llama antes de `milliseconds` transcurre.</span><span class="sxs-lookup"><span data-stu-id="8b4f5-109">A value of WAIT_ALERTABLE instructs the host to wake the task if `Alert` is called before `milliseconds` elapses.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8b4f5-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8b4f5-110">Return Value</span></span>  
  
|<span data-ttu-id="8b4f5-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8b4f5-111">HRESULT</span></span>|<span data-ttu-id="8b4f5-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="8b4f5-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8b4f5-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="8b4f5-113">S_OK</span></span>|<span data-ttu-id="8b4f5-114">`Join` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="8b4f5-114">`Join` returned successfully.</span></span>|  
|<span data-ttu-id="8b4f5-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8b4f5-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8b4f5-116">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="8b4f5-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8b4f5-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8b4f5-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8b4f5-118">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="8b4f5-118">The call timed out.</span></span>|  
|<span data-ttu-id="8b4f5-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8b4f5-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8b4f5-120">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="8b4f5-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8b4f5-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8b4f5-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8b4f5-122">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en la base de datos o actual `IHostTask` instancia no está asociada a una tarea.</span><span class="sxs-lookup"><span data-stu-id="8b4f5-122">An event was canceled while a blocked thread or fiber was waiting on it, or the current `IHostTask` instance is not associated with a task.</span></span>|  
|<span data-ttu-id="8b4f5-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8b4f5-123">E_FAIL</span></span>|<span data-ttu-id="8b4f5-124">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="8b4f5-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8b4f5-125">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="8b4f5-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8b4f5-126">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="8b4f5-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8b4f5-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8b4f5-127">Requirements</span></span>  
 <span data-ttu-id="8b4f5-128">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8b4f5-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b4f5-129">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8b4f5-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8b4f5-130">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8b4f5-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8b4f5-131">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b4f5-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b4f5-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="8b4f5-132">See also</span></span>

- [<span data-ttu-id="8b4f5-133">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8b4f5-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="8b4f5-134">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8b4f5-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="8b4f5-135">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8b4f5-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="8b4f5-136">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8b4f5-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="8b4f5-137">WAIT_OPTION (enumeración)</span><span class="sxs-lookup"><span data-stu-id="8b4f5-137">WAIT_OPTION Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md)
