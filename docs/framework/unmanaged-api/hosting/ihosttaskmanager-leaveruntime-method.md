---
title: IHostTaskManager::LeaveRuntime (Método)
ms.date: 03/30/2017
api_name:
- IHostTaskManager.LeaveRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::LeaveRuntime
helpviewer_keywords:
- IHostTaskManager::LeaveRuntime method [.NET Framework hosting]
- LeaveRuntime method [.NET Framework hosting]
ms.assetid: 43689cc4-e48e-46e5-a22d-bafd768b8759
topic_type:
- apiref
ms.openlocfilehash: deaebbce3b9b8a26bf9668b826a6818dba94dcc3
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501387"
---
# <a name="ihosttaskmanagerleaveruntime-method"></a><span data-ttu-id="4a2b6-102">IHostTaskManager::LeaveRuntime (Método)</span><span class="sxs-lookup"><span data-stu-id="4a2b6-102">IHostTaskManager::LeaveRuntime Method</span></span>
<span data-ttu-id="4a2b6-103">Notifica al host que la tarea que se está ejecutando actualmente está a punto de abandonar el Common Language Runtime (CLR) y especificar código no administrado.</span><span class="sxs-lookup"><span data-stu-id="4a2b6-103">Notifies the host that the currently executing task is about to leave the common language runtime (CLR) and enter unmanaged code.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="4a2b6-104">Una llamada correspondiente a [IHostTaskManager:: EnterRuntime (](ihosttaskmanager-enterruntime-method.md) notifica al host que la tarea que se está ejecutando actualmente está reentrando el código administrado.</span><span class="sxs-lookup"><span data-stu-id="4a2b6-104">A corresponding call to [IHostTaskManager::EnterRuntime](ihosttaskmanager-enterruntime-method.md) notifies the host that the currently executing task is reentering managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a2b6-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4a2b6-105">Syntax</span></span>  
  
```cpp  
HRESULT LeaveRuntime (  
    [in] SIZE_T target  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4a2b6-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4a2b6-106">Parameters</span></span>  
 `target`  
 <span data-ttu-id="4a2b6-107">de Dirección dentro del archivo ejecutable portable asignado de la función no administrada a la que se va a llamar.</span><span class="sxs-lookup"><span data-stu-id="4a2b6-107">[in] The address within the mapped portable executable file of the unmanaged function to be called.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4a2b6-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4a2b6-108">Return Value</span></span>  
  
|<span data-ttu-id="4a2b6-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4a2b6-109">HRESULT</span></span>|<span data-ttu-id="4a2b6-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="4a2b6-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4a2b6-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="4a2b6-111">S_OK</span></span>|<span data-ttu-id="4a2b6-112">`LeaveRuntime`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="4a2b6-112">`LeaveRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="4a2b6-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4a2b6-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4a2b6-114">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="4a2b6-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4a2b6-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4a2b6-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4a2b6-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="4a2b6-116">The call timed out.</span></span>|  
|<span data-ttu-id="4a2b6-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4a2b6-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4a2b6-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="4a2b6-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4a2b6-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4a2b6-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4a2b6-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="4a2b6-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4a2b6-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4a2b6-121">E_FAIL</span></span>|<span data-ttu-id="4a2b6-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="4a2b6-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4a2b6-123">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="4a2b6-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4a2b6-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="4a2b6-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="4a2b6-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="4a2b6-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="4a2b6-126">No hay suficiente memoria disponible para completar la asignación solicitada.</span><span class="sxs-lookup"><span data-stu-id="4a2b6-126">Not enough memory is available to complete the requested allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4a2b6-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4a2b6-127">Remarks</span></span>  
 <span data-ttu-id="4a2b6-128">Las secuencias de llamadas a y desde código no administrado se pueden anidar.</span><span class="sxs-lookup"><span data-stu-id="4a2b6-128">Call sequences to and from unmanaged code can be nested.</span></span> <span data-ttu-id="4a2b6-129">Por ejemplo, en la lista siguiente se describe una situación hipotética en la que la secuencia de llamadas a `LeaveRuntime` , [IHostTaskManager:: ReverseEnterRuntime](ihosttaskmanager-reverseenterruntime-method.md), [IHostTaskManager:: ReverseLeaveRuntime](ihosttaskmanager-reverseleaveruntime-method.md), y `IHostTaskManager::EnterRuntime` permite al host identificar las capas anidadas.</span><span class="sxs-lookup"><span data-stu-id="4a2b6-129">For example, the list below describes a hypothetical situation in which the sequence of calls to `LeaveRuntime`, [IHostTaskManager::ReverseEnterRuntime](ihosttaskmanager-reverseenterruntime-method.md), [IHostTaskManager::ReverseLeaveRuntime](ihosttaskmanager-reverseleaveruntime-method.md), and `IHostTaskManager::EnterRuntime` allows the host to identify the nested layers.</span></span>  
  
|<span data-ttu-id="4a2b6-130">Acción</span><span class="sxs-lookup"><span data-stu-id="4a2b6-130">Action</span></span>|<span data-ttu-id="4a2b6-131">Llamada al método correspondiente</span><span class="sxs-lookup"><span data-stu-id="4a2b6-131">Corresponding Method Call</span></span>|  
|------------|-------------------------------|  
|<span data-ttu-id="4a2b6-132">Un ejecutable de Visual Basic administrado llama a una función no administrada escrita en C mediante la invocación de plataforma.</span><span class="sxs-lookup"><span data-stu-id="4a2b6-132">A managed Visual Basic executable calls an unmanaged function written in C by using platform invoke.</span></span>|`IHostTaskManager::LeaveRuntime`|  
|<span data-ttu-id="4a2b6-133">La función de C no administrada llama a un método en un archivo DLL administrado escrito en C#.</span><span class="sxs-lookup"><span data-stu-id="4a2b6-133">The unmanaged C function calls a method in a managed DLL written in C#.</span></span>|`IHostTaskManager::ReverseEnterRuntime`|  
|<span data-ttu-id="4a2b6-134">La función administrada de C# llama a otra función no administrada escrita en C, también mediante la invocación de plataforma.</span><span class="sxs-lookup"><span data-stu-id="4a2b6-134">The managed C# function calls another unmanaged function written in C, also using platform invoke.</span></span>|`IHostTaskManager::LeaveRuntime`|  
|<span data-ttu-id="4a2b6-135">La segunda función no administrada devuelve la ejecución a la función de C#.</span><span class="sxs-lookup"><span data-stu-id="4a2b6-135">The second unmanaged function returns execution to the C# function.</span></span>|`IHostTaskManager::EnterRuntime`|  
|<span data-ttu-id="4a2b6-136">La función de C# devuelve la ejecución a la primera función no administrada.</span><span class="sxs-lookup"><span data-stu-id="4a2b6-136">The C# function returns execution to the first unmanaged function.</span></span>|`IHostTaskManager::ReverseLeaveRuntime`|  
|<span data-ttu-id="4a2b6-137">La primera función no administrada devuelve la ejecución al programa Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="4a2b6-137">The first unmanaged function returns execution to the Visual Basic program.</span></span>|`IHostTaskManager::EnterRuntime`|  
  
## <a name="requirements"></a><span data-ttu-id="4a2b6-138">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4a2b6-138">Requirements</span></span>  
 <span data-ttu-id="4a2b6-139">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a2b6-139">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a2b6-140">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="4a2b6-140">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4a2b6-141">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="4a2b6-141">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4a2b6-142">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a2b6-142">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a2b6-143">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="4a2b6-143">See also</span></span>

- [<span data-ttu-id="4a2b6-144">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4a2b6-144">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="4a2b6-145">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4a2b6-145">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="4a2b6-146">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4a2b6-146">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="4a2b6-147">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4a2b6-147">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
