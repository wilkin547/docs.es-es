---
title: ICLRTaskManager::CreateTask (Método)
ms.date: 03/30/2017
api_name:
- ICLRTaskManager.CreateTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::CreateTask
helpviewer_keywords:
- ICLRTaskManager::CreateTask method [.NET Framework hosting]
- CreateTask method, ICLRTaskManager interface [.NET Framework hosting]
ms.assetid: eea570d9-2e53-4320-9ea0-eb777bf9dcf3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 804a295cf74067eb23ed8e8c860252a1f2fcf5d5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67770191"
---
# <a name="iclrtaskmanagercreatetask-method"></a><span data-ttu-id="32d86-102">ICLRTaskManager::CreateTask (Método)</span><span class="sxs-lookup"><span data-stu-id="32d86-102">ICLRTaskManager::CreateTask Method</span></span>
<span data-ttu-id="32d86-103">Solicita explícitamente que common language runtime (CLR) cree una nueva tarea.</span><span class="sxs-lookup"><span data-stu-id="32d86-103">Requests explicitly that the common language runtime (CLR) create a new task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32d86-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="32d86-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateTask (  
    [out] ICLRTask **pTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="32d86-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="32d86-105">Parameters</span></span>  
 `pTask`  
 <span data-ttu-id="32d86-106">[out] Un puntero a la dirección de un recién creado [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md), o null si no se pudo crear la tarea.</span><span class="sxs-lookup"><span data-stu-id="32d86-106">[out] A pointer to the address of a newly created [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md), or null, if the task could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="32d86-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="32d86-107">Return Value</span></span>  
  
|<span data-ttu-id="32d86-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="32d86-108">HRESULT</span></span>|<span data-ttu-id="32d86-109">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="32d86-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="32d86-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="32d86-110">S_OK</span></span>|<span data-ttu-id="32d86-111">El método se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="32d86-111">The method returned successfully.</span></span>|  
|<span data-ttu-id="32d86-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="32d86-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="32d86-113">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="32d86-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="32d86-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="32d86-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="32d86-115">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="32d86-115">The call timed out.</span></span>|  
|<span data-ttu-id="32d86-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="32d86-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="32d86-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="32d86-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="32d86-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="32d86-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="32d86-119">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="32d86-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="32d86-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="32d86-120">E_FAIL</span></span>|<span data-ttu-id="32d86-121">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="32d86-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="32d86-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="32d86-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="32d86-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="32d86-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="32d86-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="32d86-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="32d86-125">No hay suficiente memoria disponible para asignar el recurso solicitado.</span><span class="sxs-lookup"><span data-stu-id="32d86-125">Not enough memory is available to allocate the requested resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="32d86-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="32d86-126">Remarks</span></span>  
 <span data-ttu-id="32d86-127">El CLR crea una nueva tarea automáticamente en la inicialización, cuando el código de usuario crea un subproceso mediante el uso de tipos en el <xref:System.Threading> espacio de nombres, o cuando se aumenta el tamaño del grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="32d86-127">The CLR creates a new task automatically upon initialization, when user code creates a thread by using types in the <xref:System.Threading> namespace, or when the size of the thread pool is increased.</span></span> <span data-ttu-id="32d86-128">También crea tareas al código no administrado realiza una llamada a una función administrada.</span><span class="sxs-lookup"><span data-stu-id="32d86-128">It also creates tasks when unmanaged code makes a call to a managed function.</span></span>  
  
 <span data-ttu-id="32d86-129">`CreateTask` permite al host realizar una solicitud explícita que el CLR crea una nueva tarea.</span><span class="sxs-lookup"><span data-stu-id="32d86-129">`CreateTask` allows the host to make an explicit request that the CLR create a new task.</span></span> <span data-ttu-id="32d86-130">Por ejemplo, el host puede invocar este método para preinicializar las estructuras de datos.</span><span class="sxs-lookup"><span data-stu-id="32d86-130">For example, the host can invoke this method to preinitialize data structures.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="32d86-131">La nueva tarea se devuelve en un estado suspendido y permanece suspendida hasta que el host llama explícitamente [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md).</span><span class="sxs-lookup"><span data-stu-id="32d86-131">The new task is returned in a suspended state and remains suspended until the host explicitly calls [IHostTask::Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32d86-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="32d86-132">Requirements</span></span>  
 <span data-ttu-id="32d86-133">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="32d86-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32d86-134">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="32d86-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="32d86-135">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="32d86-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="32d86-136">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32d86-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32d86-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="32d86-137">See also</span></span>

- [<span data-ttu-id="32d86-138">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="32d86-138">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="32d86-139">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="32d86-139">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="32d86-140">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="32d86-140">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="32d86-141">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="32d86-141">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
