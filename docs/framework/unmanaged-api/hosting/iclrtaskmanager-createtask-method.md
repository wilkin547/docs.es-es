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
ms.openlocfilehash: 8833daa9cd385a1a76c5b706f15a76bb15139b84
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59079687"
---
# <a name="iclrtaskmanagercreatetask-method"></a><span data-ttu-id="3fcba-102">ICLRTaskManager::CreateTask (Método)</span><span class="sxs-lookup"><span data-stu-id="3fcba-102">ICLRTaskManager::CreateTask Method</span></span>
<span data-ttu-id="3fcba-103">Solicita explícitamente que common language runtime (CLR) cree una nueva tarea.</span><span class="sxs-lookup"><span data-stu-id="3fcba-103">Requests explicitly that the common language runtime (CLR) create a new task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fcba-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3fcba-104">Syntax</span></span>  
  
```  
HRESULT CreateTask (  
    [out] ICLRTask **pTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3fcba-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3fcba-105">Parameters</span></span>  
 `pTask`  
 <span data-ttu-id="3fcba-106">[out] Un puntero a la dirección de un recién creado [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md), o null si no se pudo crear la tarea.</span><span class="sxs-lookup"><span data-stu-id="3fcba-106">[out] A pointer to the address of a newly created [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md), or null, if the task could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3fcba-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3fcba-107">Return Value</span></span>  
  
|<span data-ttu-id="3fcba-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3fcba-108">HRESULT</span></span>|<span data-ttu-id="3fcba-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="3fcba-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3fcba-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="3fcba-110">S_OK</span></span>|<span data-ttu-id="3fcba-111">El método se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="3fcba-111">The method returned successfully.</span></span>|  
|<span data-ttu-id="3fcba-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3fcba-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3fcba-113">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="3fcba-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3fcba-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3fcba-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3fcba-115">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="3fcba-115">The call timed out.</span></span>|  
|<span data-ttu-id="3fcba-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3fcba-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3fcba-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="3fcba-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3fcba-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3fcba-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3fcba-119">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="3fcba-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3fcba-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3fcba-120">E_FAIL</span></span>|<span data-ttu-id="3fcba-121">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="3fcba-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3fcba-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="3fcba-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3fcba-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="3fcba-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="3fcba-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="3fcba-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="3fcba-125">No hay suficiente memoria disponible para asignar el recurso solicitado.</span><span class="sxs-lookup"><span data-stu-id="3fcba-125">Not enough memory is available to allocate the requested resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3fcba-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3fcba-126">Remarks</span></span>  
 <span data-ttu-id="3fcba-127">El CLR crea una nueva tarea automáticamente en la inicialización, cuando el código de usuario crea un subproceso mediante el uso de tipos en el <xref:System.Threading> espacio de nombres, o cuando se aumenta el tamaño del grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="3fcba-127">The CLR creates a new task automatically upon initialization, when user code creates a thread by using types in the <xref:System.Threading> namespace, or when the size of the thread pool is increased.</span></span> <span data-ttu-id="3fcba-128">También crea tareas al código no administrado realiza una llamada a una función administrada.</span><span class="sxs-lookup"><span data-stu-id="3fcba-128">It also creates tasks when unmanaged code makes a call to a managed function.</span></span>  
  
 `CreateTask` <span data-ttu-id="3fcba-129">permite al host realizar una solicitud explícita que el CLR crea una nueva tarea.</span><span class="sxs-lookup"><span data-stu-id="3fcba-129">allows the host to make an explicit request that the CLR create a new task.</span></span> <span data-ttu-id="3fcba-130">Por ejemplo, el host puede invocar este método para preinicializar las estructuras de datos.</span><span class="sxs-lookup"><span data-stu-id="3fcba-130">For example, the host can invoke this method to preinitialize data structures.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3fcba-131">La nueva tarea se devuelve en un estado suspendido y permanece suspendida hasta que el host llama explícitamente [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md).</span><span class="sxs-lookup"><span data-stu-id="3fcba-131">The new task is returned in a suspended state and remains suspended until the host explicitly calls [IHostTask::Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3fcba-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3fcba-132">Requirements</span></span>  
 <span data-ttu-id="3fcba-133">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3fcba-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3fcba-134">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3fcba-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3fcba-135">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3fcba-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="3fcba-136">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="3fcba-136">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3fcba-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="3fcba-137">See also</span></span>

- [<span data-ttu-id="3fcba-138">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3fcba-138">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="3fcba-139">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3fcba-139">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="3fcba-140">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3fcba-140">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="3fcba-141">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3fcba-141">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
