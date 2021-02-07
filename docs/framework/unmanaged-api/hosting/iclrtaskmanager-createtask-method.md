---
description: 'Más información acerca de: ICLRTaskManager:: CreateTask (método)'
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
ms.openlocfilehash: 98a287f10a84b18579ebf2a4294cbb8a67cabc9c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99728618"
---
# <a name="iclrtaskmanagercreatetask-method"></a><span data-ttu-id="caa49-103">ICLRTaskManager::CreateTask (Método)</span><span class="sxs-lookup"><span data-stu-id="caa49-103">ICLRTaskManager::CreateTask Method</span></span>

<span data-ttu-id="caa49-104">Solicita explícitamente que el Common Language Runtime (CLR) cree una nueva tarea.</span><span class="sxs-lookup"><span data-stu-id="caa49-104">Requests explicitly that the common language runtime (CLR) create a new task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="caa49-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="caa49-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateTask (  
    [out] ICLRTask **pTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="caa49-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="caa49-106">Parameters</span></span>  

 `pTask`  
 <span data-ttu-id="caa49-107">enuncia Puntero a la dirección de una [ICLRTask](iclrtask-interface.md)recién creada, o null si no se pudo crear la tarea.</span><span class="sxs-lookup"><span data-stu-id="caa49-107">[out] A pointer to the address of a newly created [ICLRTask](iclrtask-interface.md), or null, if the task could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="caa49-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="caa49-108">Return Value</span></span>  
  
|<span data-ttu-id="caa49-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="caa49-109">HRESULT</span></span>|<span data-ttu-id="caa49-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="caa49-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="caa49-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="caa49-111">S_OK</span></span>|<span data-ttu-id="caa49-112">El método se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="caa49-112">The method returned successfully.</span></span>|  
|<span data-ttu-id="caa49-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="caa49-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="caa49-114">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="caa49-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="caa49-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="caa49-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="caa49-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="caa49-116">The call timed out.</span></span>|  
|<span data-ttu-id="caa49-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="caa49-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="caa49-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="caa49-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="caa49-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="caa49-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="caa49-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="caa49-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="caa49-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="caa49-121">E_FAIL</span></span>|<span data-ttu-id="caa49-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="caa49-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="caa49-123">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="caa49-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="caa49-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="caa49-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="caa49-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="caa49-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="caa49-126">No hay suficiente memoria disponible para asignar el recurso solicitado.</span><span class="sxs-lookup"><span data-stu-id="caa49-126">Not enough memory is available to allocate the requested resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="caa49-127">Observaciones</span><span class="sxs-lookup"><span data-stu-id="caa49-127">Remarks</span></span>  

 <span data-ttu-id="caa49-128">CLR crea una nueva tarea automáticamente durante la inicialización, cuando el código de usuario crea un subproceso mediante los tipos del <xref:System.Threading> espacio de nombres o cuando aumenta el tamaño del grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="caa49-128">The CLR creates a new task automatically upon initialization, when user code creates a thread by using types in the <xref:System.Threading> namespace, or when the size of the thread pool is increased.</span></span> <span data-ttu-id="caa49-129">También crea tareas cuando el código no administrado realiza una llamada a una función administrada.</span><span class="sxs-lookup"><span data-stu-id="caa49-129">It also creates tasks when unmanaged code makes a call to a managed function.</span></span>  
  
 <span data-ttu-id="caa49-130">`CreateTask` permite al host realizar una solicitud explícita de que CLR cree una nueva tarea.</span><span class="sxs-lookup"><span data-stu-id="caa49-130">`CreateTask` allows the host to make an explicit request that the CLR create a new task.</span></span> <span data-ttu-id="caa49-131">Por ejemplo, el host puede invocar este método para preinicializar las estructuras de datos.</span><span class="sxs-lookup"><span data-stu-id="caa49-131">For example, the host can invoke this method to preinitialize data structures.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="caa49-132">La nueva tarea se devuelve en un estado suspendido y permanece suspendida hasta que el host llama explícitamente a [IHostTask:: Start](ihosttask-start-method.md).</span><span class="sxs-lookup"><span data-stu-id="caa49-132">The new task is returned in a suspended state and remains suspended until the host explicitly calls [IHostTask::Start](ihosttask-start-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="caa49-133">Requisitos</span><span class="sxs-lookup"><span data-stu-id="caa49-133">Requirements</span></span>  

 <span data-ttu-id="caa49-134">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="caa49-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="caa49-135">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="caa49-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="caa49-136">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="caa49-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="caa49-137">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="caa49-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="caa49-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="caa49-138">See also</span></span>

- [<span data-ttu-id="caa49-139">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="caa49-139">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="caa49-140">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="caa49-140">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="caa49-141">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="caa49-141">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="caa49-142">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="caa49-142">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
