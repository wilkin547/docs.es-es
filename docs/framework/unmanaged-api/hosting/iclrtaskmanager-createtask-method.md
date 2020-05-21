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
ms.openlocfilehash: 9829f57da911b43626516284e4858adc4139a3ca
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762882"
---
# <a name="iclrtaskmanagercreatetask-method"></a><span data-ttu-id="3ab40-102">ICLRTaskManager::CreateTask (Método)</span><span class="sxs-lookup"><span data-stu-id="3ab40-102">ICLRTaskManager::CreateTask Method</span></span>
<span data-ttu-id="3ab40-103">Solicita explícitamente que el Common Language Runtime (CLR) cree una nueva tarea.</span><span class="sxs-lookup"><span data-stu-id="3ab40-103">Requests explicitly that the common language runtime (CLR) create a new task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ab40-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3ab40-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateTask (  
    [out] ICLRTask **pTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3ab40-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3ab40-105">Parameters</span></span>  
 `pTask`  
 <span data-ttu-id="3ab40-106">enuncia Puntero a la dirección de una [ICLRTask](iclrtask-interface.md)recién creada, o null si no se pudo crear la tarea.</span><span class="sxs-lookup"><span data-stu-id="3ab40-106">[out] A pointer to the address of a newly created [ICLRTask](iclrtask-interface.md), or null, if the task could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3ab40-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3ab40-107">Return Value</span></span>  
  
|<span data-ttu-id="3ab40-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3ab40-108">HRESULT</span></span>|<span data-ttu-id="3ab40-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="3ab40-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3ab40-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="3ab40-110">S_OK</span></span>|<span data-ttu-id="3ab40-111">El método se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="3ab40-111">The method returned successfully.</span></span>|  
|<span data-ttu-id="3ab40-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3ab40-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3ab40-113">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="3ab40-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3ab40-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3ab40-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3ab40-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="3ab40-115">The call timed out.</span></span>|  
|<span data-ttu-id="3ab40-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3ab40-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3ab40-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="3ab40-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3ab40-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3ab40-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3ab40-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="3ab40-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3ab40-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3ab40-120">E_FAIL</span></span>|<span data-ttu-id="3ab40-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="3ab40-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3ab40-122">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="3ab40-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3ab40-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="3ab40-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="3ab40-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="3ab40-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="3ab40-125">No hay suficiente memoria disponible para asignar el recurso solicitado.</span><span class="sxs-lookup"><span data-stu-id="3ab40-125">Not enough memory is available to allocate the requested resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3ab40-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3ab40-126">Remarks</span></span>  
 <span data-ttu-id="3ab40-127">CLR crea una nueva tarea automáticamente durante la inicialización, cuando el código de usuario crea un subproceso mediante los tipos del <xref:System.Threading> espacio de nombres o cuando aumenta el tamaño del grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="3ab40-127">The CLR creates a new task automatically upon initialization, when user code creates a thread by using types in the <xref:System.Threading> namespace, or when the size of the thread pool is increased.</span></span> <span data-ttu-id="3ab40-128">También crea tareas cuando el código no administrado realiza una llamada a una función administrada.</span><span class="sxs-lookup"><span data-stu-id="3ab40-128">It also creates tasks when unmanaged code makes a call to a managed function.</span></span>  
  
 <span data-ttu-id="3ab40-129">`CreateTask`permite al host realizar una solicitud explícita de que CLR cree una nueva tarea.</span><span class="sxs-lookup"><span data-stu-id="3ab40-129">`CreateTask` allows the host to make an explicit request that the CLR create a new task.</span></span> <span data-ttu-id="3ab40-130">Por ejemplo, el host puede invocar este método para preinicializar las estructuras de datos.</span><span class="sxs-lookup"><span data-stu-id="3ab40-130">For example, the host can invoke this method to preinitialize data structures.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="3ab40-131">La nueva tarea se devuelve en un estado suspendido y permanece suspendida hasta que el host llama explícitamente a [IHostTask:: Start](ihosttask-start-method.md).</span><span class="sxs-lookup"><span data-stu-id="3ab40-131">The new task is returned in a suspended state and remains suspended until the host explicitly calls [IHostTask::Start](ihosttask-start-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ab40-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3ab40-132">Requirements</span></span>  
 <span data-ttu-id="3ab40-133">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3ab40-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ab40-134">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="3ab40-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3ab40-135">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="3ab40-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3ab40-136">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ab40-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ab40-137">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="3ab40-137">See also</span></span>

- [<span data-ttu-id="3ab40-138">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3ab40-138">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="3ab40-139">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3ab40-139">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="3ab40-140">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3ab40-140">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="3ab40-141">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3ab40-141">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
