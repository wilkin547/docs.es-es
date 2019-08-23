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
ms.openlocfilehash: a89ea76d78431ae8833602588379d5150e473710
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69938304"
---
# <a name="iclrtaskmanagercreatetask-method"></a><span data-ttu-id="ee90a-102">ICLRTaskManager::CreateTask (Método)</span><span class="sxs-lookup"><span data-stu-id="ee90a-102">ICLRTaskManager::CreateTask Method</span></span>
<span data-ttu-id="ee90a-103">Solicita explícitamente que el Common Language Runtime (CLR) cree una nueva tarea.</span><span class="sxs-lookup"><span data-stu-id="ee90a-103">Requests explicitly that the common language runtime (CLR) create a new task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee90a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ee90a-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateTask (  
    [out] ICLRTask **pTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ee90a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ee90a-105">Parameters</span></span>  
 `pTask`  
 <span data-ttu-id="ee90a-106">enuncia Puntero a la dirección de una [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)recién creada, o null si no se pudo crear la tarea.</span><span class="sxs-lookup"><span data-stu-id="ee90a-106">[out] A pointer to the address of a newly created [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md), or null, if the task could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ee90a-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ee90a-107">Return Value</span></span>  
  
|<span data-ttu-id="ee90a-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ee90a-108">HRESULT</span></span>|<span data-ttu-id="ee90a-109">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="ee90a-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ee90a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="ee90a-110">S_OK</span></span>|<span data-ttu-id="ee90a-111">El método se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="ee90a-111">The method returned successfully.</span></span>|  
|<span data-ttu-id="ee90a-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ee90a-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ee90a-113">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="ee90a-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ee90a-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ee90a-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ee90a-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="ee90a-115">The call timed out.</span></span>|  
|<span data-ttu-id="ee90a-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ee90a-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ee90a-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="ee90a-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ee90a-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ee90a-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ee90a-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="ee90a-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ee90a-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ee90a-120">E_FAIL</span></span>|<span data-ttu-id="ee90a-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="ee90a-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ee90a-122">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="ee90a-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ee90a-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ee90a-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ee90a-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="ee90a-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="ee90a-125">No hay suficiente memoria disponible para asignar el recurso solicitado.</span><span class="sxs-lookup"><span data-stu-id="ee90a-125">Not enough memory is available to allocate the requested resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ee90a-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ee90a-126">Remarks</span></span>  
 <span data-ttu-id="ee90a-127">CLR crea una nueva tarea automáticamente durante la inicialización, cuando el código de usuario crea un subproceso mediante <xref:System.Threading> los tipos del espacio de nombres o cuando aumenta el tamaño del grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="ee90a-127">The CLR creates a new task automatically upon initialization, when user code creates a thread by using types in the <xref:System.Threading> namespace, or when the size of the thread pool is increased.</span></span> <span data-ttu-id="ee90a-128">También crea tareas cuando el código no administrado realiza una llamada a una función administrada.</span><span class="sxs-lookup"><span data-stu-id="ee90a-128">It also creates tasks when unmanaged code makes a call to a managed function.</span></span>  
  
 <span data-ttu-id="ee90a-129">`CreateTask`permite al host realizar una solicitud explícita de que CLR cree una nueva tarea.</span><span class="sxs-lookup"><span data-stu-id="ee90a-129">`CreateTask` allows the host to make an explicit request that the CLR create a new task.</span></span> <span data-ttu-id="ee90a-130">Por ejemplo, el host puede invocar este método para preinicializar las estructuras de datos.</span><span class="sxs-lookup"><span data-stu-id="ee90a-130">For example, the host can invoke this method to preinitialize data structures.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="ee90a-131">La nueva tarea se devuelve en un estado suspendido y permanece suspendida hasta que el host llama explícitamente a [IHostTask:: Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md).</span><span class="sxs-lookup"><span data-stu-id="ee90a-131">The new task is returned in a suspended state and remains suspended until the host explicitly calls [IHostTask::Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee90a-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ee90a-132">Requirements</span></span>  
 <span data-ttu-id="ee90a-133">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ee90a-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee90a-134">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ee90a-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ee90a-135">**Biblioteca** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ee90a-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ee90a-136">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee90a-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee90a-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="ee90a-137">See also</span></span>

- [<span data-ttu-id="ee90a-138">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ee90a-138">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="ee90a-139">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ee90a-139">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="ee90a-140">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ee90a-140">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="ee90a-141">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ee90a-141">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
