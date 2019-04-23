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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 81da8052b79047933b4afc6d5686029465d83eba
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59191502"
---
# <a name="ihosttaskmanagerleaveruntime-method"></a><span data-ttu-id="b4ff8-102">IHostTaskManager::LeaveRuntime (Método)</span><span class="sxs-lookup"><span data-stu-id="b4ff8-102">IHostTaskManager::LeaveRuntime Method</span></span>
<span data-ttu-id="b4ff8-103">Notifica al host que la tarea actualmente en ejecución está a punto de dejar de common language runtime (CLR) y escriba el código no administrado.</span><span class="sxs-lookup"><span data-stu-id="b4ff8-103">Notifies the host that the currently executing task is about to leave the common language runtime (CLR) and enter unmanaged code.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b4ff8-104">Una llamada correspondiente a [IHostTaskManager:: EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md) notifica al host que la tarea actualmente en ejecución es volver a escribir código administrado.</span><span class="sxs-lookup"><span data-stu-id="b4ff8-104">A corresponding call to [IHostTaskManager::EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md) notifies the host that the currently executing task is reentering managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4ff8-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b4ff8-105">Syntax</span></span>  
  
```  
HRESULT LeaveRuntime (  
    [in] SIZE_T target  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b4ff8-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b4ff8-106">Parameters</span></span>  
 `target`  
 <span data-ttu-id="b4ff8-107">[in] La dirección dentro del archivo portable ejecutable asignada de la llamada a función no administrada.</span><span class="sxs-lookup"><span data-stu-id="b4ff8-107">[in] The address within the mapped portable executable file of the unmanaged function to be called.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b4ff8-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b4ff8-108">Return Value</span></span>  
  
|<span data-ttu-id="b4ff8-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b4ff8-109">HRESULT</span></span>|<span data-ttu-id="b4ff8-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="b4ff8-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b4ff8-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="b4ff8-111">S_OK</span></span>|<span data-ttu-id="b4ff8-112">`LeaveRuntime` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="b4ff8-112">`LeaveRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="b4ff8-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b4ff8-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b4ff8-114">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="b4ff8-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b4ff8-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b4ff8-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b4ff8-116">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="b4ff8-116">The call timed out.</span></span>|  
|<span data-ttu-id="b4ff8-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b4ff8-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b4ff8-118">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="b4ff8-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b4ff8-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b4ff8-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b4ff8-120">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="b4ff8-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b4ff8-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b4ff8-121">E_FAIL</span></span>|<span data-ttu-id="b4ff8-122">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="b4ff8-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b4ff8-123">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="b4ff8-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b4ff8-124">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b4ff8-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="b4ff8-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="b4ff8-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="b4ff8-126">No hay suficiente memoria disponible para completar la asignación solicitada.</span><span class="sxs-lookup"><span data-stu-id="b4ff8-126">Not enough memory is available to complete the requested allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b4ff8-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b4ff8-127">Remarks</span></span>  
 <span data-ttu-id="b4ff8-128">Las secuencias de llamadas a y desde código no administrado se pueden anidar.</span><span class="sxs-lookup"><span data-stu-id="b4ff8-128">Call sequences to and from unmanaged code can be nested.</span></span> <span data-ttu-id="b4ff8-129">Por ejemplo, la siguiente lista describe una situación hipotética en el que la secuencia de llamadas a `LeaveRuntime`, [IHostTaskManager:: ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), [IHostTaskManager:: ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md), y `IHostTaskManager::EnterRuntime` permite al host identificar las capas anidadas.</span><span class="sxs-lookup"><span data-stu-id="b4ff8-129">For example, the list below describes a hypothetical situation in which the sequence of calls to `LeaveRuntime`, [IHostTaskManager::ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), [IHostTaskManager::ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md), and `IHostTaskManager::EnterRuntime` allows the host to identify the nested layers.</span></span>  
  
|<span data-ttu-id="b4ff8-130">Acción</span><span class="sxs-lookup"><span data-stu-id="b4ff8-130">Action</span></span>|<span data-ttu-id="b4ff8-131">Llamada al método correspondiente</span><span class="sxs-lookup"><span data-stu-id="b4ff8-131">Corresponding Method Call</span></span>|  
|------------|-------------------------------|  
|<span data-ttu-id="b4ff8-132">Invocar una función no administrada escrita en C con la plataforma de un llamadas ejecutable administrado de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="b4ff8-132">A managed Visual Basic executable calls an unmanaged function written in C by using platform invoke.</span></span>|`IHostTaskManager::LeaveRuntime`|  
|<span data-ttu-id="b4ff8-133">La función de C no administrada llama a un método en un archivo DLL administrado escrita en C#.</span><span class="sxs-lookup"><span data-stu-id="b4ff8-133">The unmanaged C function calls a method in a managed DLL written in C#.</span></span>|`IHostTaskManager::ReverseEnterRuntime`|  
|<span data-ttu-id="b4ff8-134">Los recursos administrados C# función llama a otra función no administrado escrito en C, también usar invocación de plataforma.</span><span class="sxs-lookup"><span data-stu-id="b4ff8-134">The managed C# function calls another unmanaged function written in C, also using platform invoke.</span></span>|`IHostTaskManager::LeaveRuntime`|  
|<span data-ttu-id="b4ff8-135">La segunda función no administrada devuelve la ejecución a la C# función.</span><span class="sxs-lookup"><span data-stu-id="b4ff8-135">The second unmanaged function returns execution to the C# function.</span></span>|`IHostTaskManager::EnterRuntime`|  
|<span data-ttu-id="b4ff8-136">El C# función devuelve la ejecución a la primera función no administrada.</span><span class="sxs-lookup"><span data-stu-id="b4ff8-136">The C# function returns execution to the first unmanaged function.</span></span>|`IHostTaskManager::ReverseLeaveRuntime`|  
|<span data-ttu-id="b4ff8-137">La primera función no administrada devuelve la ejecución al programa de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="b4ff8-137">The first unmanaged function returns execution to the Visual Basic program.</span></span>|`IHostTaskManager::EnterRuntime`|  
  
## <a name="requirements"></a><span data-ttu-id="b4ff8-138">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b4ff8-138">Requirements</span></span>  
 <span data-ttu-id="b4ff8-139">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4ff8-139">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4ff8-140">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b4ff8-140">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b4ff8-141">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b4ff8-141">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b4ff8-142">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4ff8-142">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4ff8-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="b4ff8-143">See also</span></span>

- [<span data-ttu-id="b4ff8-144">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b4ff8-144">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="b4ff8-145">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b4ff8-145">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="b4ff8-146">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b4ff8-146">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="b4ff8-147">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b4ff8-147">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
