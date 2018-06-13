---
title: IHostTaskManager::CreateTask (Método)
ms.date: 03/30/2017
api_name:
- IHostTaskManager.CreateTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::CreateTask
helpviewer_keywords:
- CreateTask method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::CreateTask method [.NET Framework hosting]
ms.assetid: a6f8ad36-61e1-42b0-9db2-add575646d18
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0cb539d5b10c8a027a8c73c68ccc04aa490cb4df
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443172"
---
# <a name="ihosttaskmanagercreatetask-method"></a><span data-ttu-id="5e8b8-102">IHostTaskManager::CreateTask (Método)</span><span class="sxs-lookup"><span data-stu-id="5e8b8-102">IHostTaskManager::CreateTask Method</span></span>
<span data-ttu-id="5e8b8-103">Solicita que el host cree una nueva tarea.</span><span class="sxs-lookup"><span data-stu-id="5e8b8-103">Requests that the host create a new task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e8b8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5e8b8-104">Syntax</span></span>  
  
```  
HRESULT CreateTask (  
    [in]  DWORD stacksize,   
    [in]  LPTHREAD_START_ROUTINE pStartAddress,  
    [in]  PVOID pParameter,  
    [out] IHostTask **ppTask  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5e8b8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5e8b8-105">Parameters</span></span>  
 `stacksize`  
 <span data-ttu-id="5e8b8-106">[in] El tamaño solicitado, en bytes, de la pila solicitada, o 0 (cero) para el tamaño predeterminado.</span><span class="sxs-lookup"><span data-stu-id="5e8b8-106">[in] The requested size, in bytes, of the requested stack, or 0 (zero) for the default size.</span></span>  
  
 `pStartAddress`  
 <span data-ttu-id="5e8b8-107">[in] Un puntero a la función es ejecutar la tarea.</span><span class="sxs-lookup"><span data-stu-id="5e8b8-107">[in] A pointer to the function the task is to execute.</span></span>  
  
 `pParameter`  
 <span data-ttu-id="5e8b8-108">[in] Un puntero a los datos de usuario que se pasan a la función, o null si la función no toma ningún parámetro.</span><span class="sxs-lookup"><span data-stu-id="5e8b8-108">[in] A pointer to the user data to be passed to the function, or null if the function takes no parameters.</span></span>  
  
 `ppTask`  
 <span data-ttu-id="5e8b8-109">[out] Un puntero a la dirección de un [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instancia creada por el host, o null si no se puede crear la tarea.</span><span class="sxs-lookup"><span data-stu-id="5e8b8-109">[out] A pointer to the address of an [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance created by the host, or null if the task cannot be created.</span></span> <span data-ttu-id="5e8b8-110">La tarea permanece en un estado suspendido hasta que se inicia explícitamente mediante una llamada a [IHostTask:: Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md).</span><span class="sxs-lookup"><span data-stu-id="5e8b8-110">The task remains in a suspended state until it is explicitly started by a call to [IHostTask::Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5e8b8-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5e8b8-111">Return Value</span></span>  
  
|<span data-ttu-id="5e8b8-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5e8b8-112">HRESULT</span></span>|<span data-ttu-id="5e8b8-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="5e8b8-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5e8b8-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="5e8b8-114">S_OK</span></span>|<span data-ttu-id="5e8b8-115">`CreateTask` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="5e8b8-115">`CreateTask` returned successfully.</span></span>|  
|<span data-ttu-id="5e8b8-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5e8b8-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5e8b8-117">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="5e8b8-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5e8b8-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5e8b8-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5e8b8-119">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="5e8b8-119">The call timed out.</span></span>|  
|<span data-ttu-id="5e8b8-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5e8b8-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5e8b8-121">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="5e8b8-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5e8b8-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5e8b8-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5e8b8-123">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="5e8b8-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5e8b8-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5e8b8-124">E_FAIL</span></span>|<span data-ttu-id="5e8b8-125">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="5e8b8-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5e8b8-126">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="5e8b8-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5e8b8-127">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="5e8b8-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="5e8b8-128">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="5e8b8-128">E_OUTOFMEMORY</span></span>|<span data-ttu-id="5e8b8-129">No había memoria suficiente disponible para crear la tarea solicitada.</span><span class="sxs-lookup"><span data-stu-id="5e8b8-129">Not enough memory was available to create the requested task.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5e8b8-130">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5e8b8-130">Remarks</span></span>  
 <span data-ttu-id="5e8b8-131">CLR llama `CreateTask` para solicitar que el host cree una nueva tarea.</span><span class="sxs-lookup"><span data-stu-id="5e8b8-131">The CLR calls `CreateTask` to request that the host create a new task.</span></span> <span data-ttu-id="5e8b8-132">El host devuelve un puntero de interfaz a un `IHostTask` instancia.</span><span class="sxs-lookup"><span data-stu-id="5e8b8-132">The host returns an interface pointer to an `IHostTask` instance.</span></span> <span data-ttu-id="5e8b8-133">La tarea devuelta debe permanecer suspendida hasta que se inicia explícitamente mediante una llamada a `IHostTask::Start`.</span><span class="sxs-lookup"><span data-stu-id="5e8b8-133">The returned task must remain suspended until it is explicitly started by a call to `IHostTask::Start`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e8b8-134">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5e8b8-134">Requirements</span></span>  
 <span data-ttu-id="5e8b8-135">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5e8b8-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e8b8-136">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5e8b8-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5e8b8-137">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5e8b8-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5e8b8-138">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e8b8-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e8b8-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="5e8b8-139">See Also</span></span>  
 [<span data-ttu-id="5e8b8-140">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5e8b8-140">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="5e8b8-141">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5e8b8-141">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="5e8b8-142">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5e8b8-142">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="5e8b8-143">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5e8b8-143">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
