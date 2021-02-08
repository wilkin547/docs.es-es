---
description: 'Más información acerca de: IHostTaskManager:: CreateTask (método)'
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
ms.openlocfilehash: c14c80ea9067b0a28e7b9186ea66eb695687bf27
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784579"
---
# <a name="ihosttaskmanagercreatetask-method"></a><span data-ttu-id="0cc5d-103">IHostTaskManager::CreateTask (Método)</span><span class="sxs-lookup"><span data-stu-id="0cc5d-103">IHostTaskManager::CreateTask Method</span></span>

<span data-ttu-id="0cc5d-104">Solicita que el host cree una nueva tarea.</span><span class="sxs-lookup"><span data-stu-id="0cc5d-104">Requests that the host create a new task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0cc5d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0cc5d-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateTask (  
    [in]  DWORD stacksize,
    [in]  LPTHREAD_START_ROUTINE pStartAddress,  
    [in]  PVOID pParameter,  
    [out] IHostTask **ppTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0cc5d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0cc5d-106">Parameters</span></span>  

 `stacksize`  
 <span data-ttu-id="0cc5d-107">de Tamaño solicitado, en bytes, de la pila solicitada o 0 (cero) para el tamaño predeterminado.</span><span class="sxs-lookup"><span data-stu-id="0cc5d-107">[in] The requested size, in bytes, of the requested stack, or 0 (zero) for the default size.</span></span>  
  
 `pStartAddress`  
 <span data-ttu-id="0cc5d-108">de Puntero a la función que va a ejecutar la tarea.</span><span class="sxs-lookup"><span data-stu-id="0cc5d-108">[in] A pointer to the function the task is to execute.</span></span>  
  
 `pParameter`  
 <span data-ttu-id="0cc5d-109">de Un puntero a los datos de usuario que se van a pasar a la función, o null si la función no toma ningún parámetro.</span><span class="sxs-lookup"><span data-stu-id="0cc5d-109">[in] A pointer to the user data to be passed to the function, or null if the function takes no parameters.</span></span>  
  
 `ppTask`  
 <span data-ttu-id="0cc5d-110">enuncia Un puntero a la dirección de una instancia de [IHostTask](ihosttask-interface.md) creada por el host, o null si no se puede crear la tarea.</span><span class="sxs-lookup"><span data-stu-id="0cc5d-110">[out] A pointer to the address of an [IHostTask](ihosttask-interface.md) instance created by the host, or null if the task cannot be created.</span></span> <span data-ttu-id="0cc5d-111">La tarea permanece en estado suspendido hasta que se inicia explícitamente mediante una llamada a [IHostTask:: Start](ihosttask-start-method.md).</span><span class="sxs-lookup"><span data-stu-id="0cc5d-111">The task remains in a suspended state until it is explicitly started by a call to [IHostTask::Start](ihosttask-start-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0cc5d-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0cc5d-112">Return Value</span></span>  
  
|<span data-ttu-id="0cc5d-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0cc5d-113">HRESULT</span></span>|<span data-ttu-id="0cc5d-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="0cc5d-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0cc5d-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="0cc5d-115">S_OK</span></span>|<span data-ttu-id="0cc5d-116">`CreateTask` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="0cc5d-116">`CreateTask` returned successfully.</span></span>|  
|<span data-ttu-id="0cc5d-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0cc5d-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0cc5d-118">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="0cc5d-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0cc5d-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0cc5d-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0cc5d-120">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="0cc5d-120">The call timed out.</span></span>|  
|<span data-ttu-id="0cc5d-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0cc5d-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0cc5d-122">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="0cc5d-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0cc5d-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0cc5d-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0cc5d-124">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="0cc5d-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0cc5d-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0cc5d-125">E_FAIL</span></span>|<span data-ttu-id="0cc5d-126">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="0cc5d-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0cc5d-127">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="0cc5d-127">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0cc5d-128">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="0cc5d-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="0cc5d-129">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="0cc5d-129">E_OUTOFMEMORY</span></span>|<span data-ttu-id="0cc5d-130">No había suficiente memoria disponible para crear la tarea solicitada.</span><span class="sxs-lookup"><span data-stu-id="0cc5d-130">Not enough memory was available to create the requested task.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0cc5d-131">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0cc5d-131">Remarks</span></span>  

 <span data-ttu-id="0cc5d-132">CLR llama `CreateTask` a para solicitar que el host cree una nueva tarea.</span><span class="sxs-lookup"><span data-stu-id="0cc5d-132">The CLR calls `CreateTask` to request that the host create a new task.</span></span> <span data-ttu-id="0cc5d-133">El host devuelve un puntero de interfaz a una `IHostTask` instancia de.</span><span class="sxs-lookup"><span data-stu-id="0cc5d-133">The host returns an interface pointer to an `IHostTask` instance.</span></span> <span data-ttu-id="0cc5d-134">La tarea devuelta debe permanecer suspendida hasta que se inicie explícitamente mediante una llamada a `IHostTask::Start` .</span><span class="sxs-lookup"><span data-stu-id="0cc5d-134">The returned task must remain suspended until it is explicitly started by a call to `IHostTask::Start`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0cc5d-135">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0cc5d-135">Requirements</span></span>  

 <span data-ttu-id="0cc5d-136">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0cc5d-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0cc5d-137">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="0cc5d-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0cc5d-138">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0cc5d-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0cc5d-139">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0cc5d-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cc5d-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="0cc5d-140">See also</span></span>

- [<span data-ttu-id="0cc5d-141">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0cc5d-141">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="0cc5d-142">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0cc5d-142">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="0cc5d-143">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0cc5d-143">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="0cc5d-144">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0cc5d-144">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
