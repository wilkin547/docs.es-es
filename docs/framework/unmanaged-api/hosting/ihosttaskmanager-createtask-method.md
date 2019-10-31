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
ms.openlocfilehash: 16916d62a528222db952a1d29dc7c69de2352191
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133123"
---
# <a name="ihosttaskmanagercreatetask-method"></a><span data-ttu-id="1920a-102">IHostTaskManager::CreateTask (Método)</span><span class="sxs-lookup"><span data-stu-id="1920a-102">IHostTaskManager::CreateTask Method</span></span>
<span data-ttu-id="1920a-103">Solicita que el host cree una nueva tarea.</span><span class="sxs-lookup"><span data-stu-id="1920a-103">Requests that the host create a new task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1920a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1920a-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateTask (  
    [in]  DWORD stacksize,   
    [in]  LPTHREAD_START_ROUTINE pStartAddress,  
    [in]  PVOID pParameter,  
    [out] IHostTask **ppTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1920a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1920a-105">Parameters</span></span>  
 `stacksize`  
 <span data-ttu-id="1920a-106">de Tamaño solicitado, en bytes, de la pila solicitada o 0 (cero) para el tamaño predeterminado.</span><span class="sxs-lookup"><span data-stu-id="1920a-106">[in] The requested size, in bytes, of the requested stack, or 0 (zero) for the default size.</span></span>  
  
 `pStartAddress`  
 <span data-ttu-id="1920a-107">de Puntero a la función que va a ejecutar la tarea.</span><span class="sxs-lookup"><span data-stu-id="1920a-107">[in] A pointer to the function the task is to execute.</span></span>  
  
 `pParameter`  
 <span data-ttu-id="1920a-108">de Un puntero a los datos de usuario que se van a pasar a la función, o null si la función no toma ningún parámetro.</span><span class="sxs-lookup"><span data-stu-id="1920a-108">[in] A pointer to the user data to be passed to the function, or null if the function takes no parameters.</span></span>  
  
 `ppTask`  
 <span data-ttu-id="1920a-109">enuncia Un puntero a la dirección de una instancia de [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) creada por el host, o null si no se puede crear la tarea.</span><span class="sxs-lookup"><span data-stu-id="1920a-109">[out] A pointer to the address of an [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance created by the host, or null if the task cannot be created.</span></span> <span data-ttu-id="1920a-110">La tarea permanece en estado suspendido hasta que se inicia explícitamente mediante una llamada a [IHostTask:: Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md).</span><span class="sxs-lookup"><span data-stu-id="1920a-110">The task remains in a suspended state until it is explicitly started by a call to [IHostTask::Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1920a-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1920a-111">Return Value</span></span>  
  
|<span data-ttu-id="1920a-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1920a-112">HRESULT</span></span>|<span data-ttu-id="1920a-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="1920a-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1920a-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="1920a-114">S_OK</span></span>|<span data-ttu-id="1920a-115">`CreateTask` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="1920a-115">`CreateTask` returned successfully.</span></span>|  
|<span data-ttu-id="1920a-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1920a-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1920a-117">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="1920a-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1920a-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1920a-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1920a-119">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="1920a-119">The call timed out.</span></span>|  
|<span data-ttu-id="1920a-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1920a-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1920a-121">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="1920a-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1920a-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1920a-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1920a-123">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="1920a-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1920a-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1920a-124">E_FAIL</span></span>|<span data-ttu-id="1920a-125">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="1920a-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1920a-126">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="1920a-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1920a-127">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="1920a-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="1920a-128">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="1920a-128">E_OUTOFMEMORY</span></span>|<span data-ttu-id="1920a-129">No había suficiente memoria disponible para crear la tarea solicitada.</span><span class="sxs-lookup"><span data-stu-id="1920a-129">Not enough memory was available to create the requested task.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1920a-130">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1920a-130">Remarks</span></span>  
 <span data-ttu-id="1920a-131">CLR llama a `CreateTask` para solicitar que el host cree una nueva tarea.</span><span class="sxs-lookup"><span data-stu-id="1920a-131">The CLR calls `CreateTask` to request that the host create a new task.</span></span> <span data-ttu-id="1920a-132">El host devuelve un puntero de interfaz a una instancia de `IHostTask`.</span><span class="sxs-lookup"><span data-stu-id="1920a-132">The host returns an interface pointer to an `IHostTask` instance.</span></span> <span data-ttu-id="1920a-133">La tarea devuelta debe permanecer suspendida hasta que se inicie explícitamente mediante una llamada a `IHostTask::Start`.</span><span class="sxs-lookup"><span data-stu-id="1920a-133">The returned task must remain suspended until it is explicitly started by a call to `IHostTask::Start`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1920a-134">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1920a-134">Requirements</span></span>  
 <span data-ttu-id="1920a-135">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1920a-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1920a-136">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="1920a-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1920a-137">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="1920a-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1920a-138">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1920a-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1920a-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="1920a-139">See also</span></span>

- [<span data-ttu-id="1920a-140">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1920a-140">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="1920a-141">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1920a-141">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="1920a-142">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1920a-142">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="1920a-143">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1920a-143">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
