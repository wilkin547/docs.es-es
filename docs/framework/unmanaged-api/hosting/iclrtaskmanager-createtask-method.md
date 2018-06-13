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
ms.openlocfilehash: f731e121324793a027c5977a02e1973b0d6fff20
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33439653"
---
# <a name="iclrtaskmanagercreatetask-method"></a><span data-ttu-id="53119-102">ICLRTaskManager::CreateTask (Método)</span><span class="sxs-lookup"><span data-stu-id="53119-102">ICLRTaskManager::CreateTask Method</span></span>
<span data-ttu-id="53119-103">Solicita explícitamente que common language runtime (CLR) cree una nueva tarea.</span><span class="sxs-lookup"><span data-stu-id="53119-103">Requests explicitly that the common language runtime (CLR) create a new task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53119-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="53119-104">Syntax</span></span>  
  
```  
HRESULT CreateTask (  
    [out] ICLRTask **pTask  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="53119-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="53119-105">Parameters</span></span>  
 `pTask`  
 <span data-ttu-id="53119-106">[out] Un puntero a la dirección de otra recién creada [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md), o null si no se pudo crear la tarea.</span><span class="sxs-lookup"><span data-stu-id="53119-106">[out] A pointer to the address of a newly created [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md), or null, if the task could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="53119-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="53119-107">Return Value</span></span>  
  
|<span data-ttu-id="53119-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="53119-108">HRESULT</span></span>|<span data-ttu-id="53119-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="53119-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="53119-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="53119-110">S_OK</span></span>|<span data-ttu-id="53119-111">El método se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="53119-111">The method returned successfully.</span></span>|  
|<span data-ttu-id="53119-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="53119-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="53119-113">El CLR no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="53119-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="53119-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="53119-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="53119-115">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="53119-115">The call timed out.</span></span>|  
|<span data-ttu-id="53119-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="53119-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="53119-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="53119-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="53119-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="53119-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="53119-119">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="53119-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="53119-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="53119-120">E_FAIL</span></span>|<span data-ttu-id="53119-121">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="53119-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="53119-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="53119-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="53119-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="53119-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="53119-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="53119-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="53119-125">No hay suficiente memoria disponible para asignar el recurso solicitado.</span><span class="sxs-lookup"><span data-stu-id="53119-125">Not enough memory is available to allocate the requested resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="53119-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="53119-126">Remarks</span></span>  
 <span data-ttu-id="53119-127">El CLR crea una nueva tarea automáticamente tras la inicialización, cuando el código de usuario crea un subproceso mediante el uso de tipos en el <xref:System.Threading> espacio de nombres, o cuando se aumenta el tamaño del grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="53119-127">The CLR creates a new task automatically upon initialization, when user code creates a thread by using types in the <xref:System.Threading> namespace, or when the size of the thread pool is increased.</span></span> <span data-ttu-id="53119-128">También crea tareas cuando el código no administrado realiza una llamada a una función administrada.</span><span class="sxs-lookup"><span data-stu-id="53119-128">It also creates tasks when unmanaged code makes a call to a managed function.</span></span>  
  
 <span data-ttu-id="53119-129">`CreateTask` permite al host realizar una solicitud explícita que CLR cree una nueva tarea.</span><span class="sxs-lookup"><span data-stu-id="53119-129">`CreateTask` allows the host to make an explicit request that the CLR create a new task.</span></span> <span data-ttu-id="53119-130">Por ejemplo, el host puede invocar este método para preinicializar las estructuras de datos.</span><span class="sxs-lookup"><span data-stu-id="53119-130">For example, the host can invoke this method to preinitialize data structures.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="53119-131">La nueva tarea se devuelve en un estado suspendido y permanece suspendida hasta que el host llame explícitamente a [IHostTask:: Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md).</span><span class="sxs-lookup"><span data-stu-id="53119-131">The new task is returned in a suspended state and remains suspended until the host explicitly calls [IHostTask::Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53119-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="53119-132">Requirements</span></span>  
 <span data-ttu-id="53119-133">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="53119-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53119-134">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="53119-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="53119-135">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="53119-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="53119-136">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53119-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53119-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="53119-137">See Also</span></span>  
 [<span data-ttu-id="53119-138">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="53119-138">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="53119-139">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="53119-139">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="53119-140">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="53119-140">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="53119-141">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="53119-141">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
