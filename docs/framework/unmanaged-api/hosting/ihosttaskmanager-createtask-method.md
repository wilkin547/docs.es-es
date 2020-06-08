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
ms.openlocfilehash: 4037ffe63d8ebfca67cbd0b3293d36be7481b1bd
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501422"
---
# <a name="ihosttaskmanagercreatetask-method"></a><span data-ttu-id="663d9-102">IHostTaskManager::CreateTask (Método)</span><span class="sxs-lookup"><span data-stu-id="663d9-102">IHostTaskManager::CreateTask Method</span></span>
<span data-ttu-id="663d9-103">Solicita que el host cree una nueva tarea.</span><span class="sxs-lookup"><span data-stu-id="663d9-103">Requests that the host create a new task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="663d9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="663d9-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateTask (  
    [in]  DWORD stacksize,
    [in]  LPTHREAD_START_ROUTINE pStartAddress,  
    [in]  PVOID pParameter,  
    [out] IHostTask **ppTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="663d9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="663d9-105">Parameters</span></span>  
 `stacksize`  
 <span data-ttu-id="663d9-106">de Tamaño solicitado, en bytes, de la pila solicitada o 0 (cero) para el tamaño predeterminado.</span><span class="sxs-lookup"><span data-stu-id="663d9-106">[in] The requested size, in bytes, of the requested stack, or 0 (zero) for the default size.</span></span>  
  
 `pStartAddress`  
 <span data-ttu-id="663d9-107">de Puntero a la función que va a ejecutar la tarea.</span><span class="sxs-lookup"><span data-stu-id="663d9-107">[in] A pointer to the function the task is to execute.</span></span>  
  
 `pParameter`  
 <span data-ttu-id="663d9-108">de Un puntero a los datos de usuario que se van a pasar a la función, o null si la función no toma ningún parámetro.</span><span class="sxs-lookup"><span data-stu-id="663d9-108">[in] A pointer to the user data to be passed to the function, or null if the function takes no parameters.</span></span>  
  
 `ppTask`  
 <span data-ttu-id="663d9-109">enuncia Un puntero a la dirección de una instancia de [IHostTask](ihosttask-interface.md) creada por el host, o null si no se puede crear la tarea.</span><span class="sxs-lookup"><span data-stu-id="663d9-109">[out] A pointer to the address of an [IHostTask](ihosttask-interface.md) instance created by the host, or null if the task cannot be created.</span></span> <span data-ttu-id="663d9-110">La tarea permanece en estado suspendido hasta que se inicia explícitamente mediante una llamada a [IHostTask:: Start](ihosttask-start-method.md).</span><span class="sxs-lookup"><span data-stu-id="663d9-110">The task remains in a suspended state until it is explicitly started by a call to [IHostTask::Start](ihosttask-start-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="663d9-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="663d9-111">Return Value</span></span>  
  
|<span data-ttu-id="663d9-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="663d9-112">HRESULT</span></span>|<span data-ttu-id="663d9-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="663d9-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="663d9-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="663d9-114">S_OK</span></span>|<span data-ttu-id="663d9-115">`CreateTask`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="663d9-115">`CreateTask` returned successfully.</span></span>|  
|<span data-ttu-id="663d9-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="663d9-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="663d9-117">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="663d9-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="663d9-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="663d9-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="663d9-119">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="663d9-119">The call timed out.</span></span>|  
|<span data-ttu-id="663d9-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="663d9-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="663d9-121">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="663d9-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="663d9-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="663d9-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="663d9-123">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="663d9-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="663d9-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="663d9-124">E_FAIL</span></span>|<span data-ttu-id="663d9-125">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="663d9-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="663d9-126">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="663d9-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="663d9-127">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="663d9-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="663d9-128">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="663d9-128">E_OUTOFMEMORY</span></span>|<span data-ttu-id="663d9-129">No había suficiente memoria disponible para crear la tarea solicitada.</span><span class="sxs-lookup"><span data-stu-id="663d9-129">Not enough memory was available to create the requested task.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="663d9-130">Comentarios</span><span class="sxs-lookup"><span data-stu-id="663d9-130">Remarks</span></span>  
 <span data-ttu-id="663d9-131">CLR llama `CreateTask` a para solicitar que el host cree una nueva tarea.</span><span class="sxs-lookup"><span data-stu-id="663d9-131">The CLR calls `CreateTask` to request that the host create a new task.</span></span> <span data-ttu-id="663d9-132">El host devuelve un puntero de interfaz a una `IHostTask` instancia de.</span><span class="sxs-lookup"><span data-stu-id="663d9-132">The host returns an interface pointer to an `IHostTask` instance.</span></span> <span data-ttu-id="663d9-133">La tarea devuelta debe permanecer suspendida hasta que se inicie explícitamente mediante una llamada a `IHostTask::Start` .</span><span class="sxs-lookup"><span data-stu-id="663d9-133">The returned task must remain suspended until it is explicitly started by a call to `IHostTask::Start`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="663d9-134">Requisitos</span><span class="sxs-lookup"><span data-stu-id="663d9-134">Requirements</span></span>  
 <span data-ttu-id="663d9-135">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="663d9-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="663d9-136">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="663d9-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="663d9-137">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="663d9-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="663d9-138">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="663d9-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="663d9-139">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="663d9-139">See also</span></span>

- [<span data-ttu-id="663d9-140">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="663d9-140">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="663d9-141">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="663d9-141">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="663d9-142">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="663d9-142">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="663d9-143">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="663d9-143">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
