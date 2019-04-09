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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59191502"
---
# <a name="ihosttaskmanagerleaveruntime-method"></a><span data-ttu-id="46808-102">IHostTaskManager::LeaveRuntime (Método)</span><span class="sxs-lookup"><span data-stu-id="46808-102">IHostTaskManager::LeaveRuntime Method</span></span>
<span data-ttu-id="46808-103">Notifica al host que la tarea actualmente en ejecución está a punto de dejar de common language runtime (CLR) y escriba el código no administrado.</span><span class="sxs-lookup"><span data-stu-id="46808-103">Notifies the host that the currently executing task is about to leave the common language runtime (CLR) and enter unmanaged code.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="46808-104">Una llamada correspondiente a [IHostTaskManager:: EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md) notifica al host que la tarea actualmente en ejecución es volver a escribir código administrado.</span><span class="sxs-lookup"><span data-stu-id="46808-104">A corresponding call to [IHostTaskManager::EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md) notifies the host that the currently executing task is reentering managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46808-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="46808-105">Syntax</span></span>  
  
```  
HRESULT LeaveRuntime (  
    [in] SIZE_T target  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="46808-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="46808-106">Parameters</span></span>  
 `target`  
 <span data-ttu-id="46808-107">[in] La dirección dentro del archivo portable ejecutable asignada de la llamada a función no administrada.</span><span class="sxs-lookup"><span data-stu-id="46808-107">[in] The address within the mapped portable executable file of the unmanaged function to be called.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="46808-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="46808-108">Return Value</span></span>  
  
|<span data-ttu-id="46808-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="46808-109">HRESULT</span></span>|<span data-ttu-id="46808-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="46808-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="46808-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="46808-111">S_OK</span></span>|`LeaveRuntime` <span data-ttu-id="46808-112">se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="46808-112">returned successfully.</span></span>|  
|<span data-ttu-id="46808-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="46808-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="46808-114">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="46808-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="46808-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="46808-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="46808-116">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="46808-116">The call timed out.</span></span>|  
|<span data-ttu-id="46808-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="46808-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="46808-118">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="46808-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="46808-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="46808-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="46808-120">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="46808-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="46808-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="46808-121">E_FAIL</span></span>|<span data-ttu-id="46808-122">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="46808-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="46808-123">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="46808-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="46808-124">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="46808-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="46808-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="46808-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="46808-126">No hay suficiente memoria disponible para completar la asignación solicitada.</span><span class="sxs-lookup"><span data-stu-id="46808-126">Not enough memory is available to complete the requested allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="46808-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="46808-127">Remarks</span></span>  
 <span data-ttu-id="46808-128">Las secuencias de llamadas a y desde código no administrado se pueden anidar.</span><span class="sxs-lookup"><span data-stu-id="46808-128">Call sequences to and from unmanaged code can be nested.</span></span> <span data-ttu-id="46808-129">Por ejemplo, la siguiente lista describe una situación hipotética en el que la secuencia de llamadas a `LeaveRuntime`, [IHostTaskManager:: ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), [IHostTaskManager:: ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md), y `IHostTaskManager::EnterRuntime` permite al host identificar las capas anidadas.</span><span class="sxs-lookup"><span data-stu-id="46808-129">For example, the list below describes a hypothetical situation in which the sequence of calls to `LeaveRuntime`, [IHostTaskManager::ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), [IHostTaskManager::ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md), and `IHostTaskManager::EnterRuntime` allows the host to identify the nested layers.</span></span>  
  
|<span data-ttu-id="46808-130">Acción</span><span class="sxs-lookup"><span data-stu-id="46808-130">Action</span></span>|<span data-ttu-id="46808-131">Llamada al método correspondiente</span><span class="sxs-lookup"><span data-stu-id="46808-131">Corresponding Method Call</span></span>|  
|------------|-------------------------------|  
|<span data-ttu-id="46808-132">Invocar una función no administrada escrita en C con la plataforma de un llamadas ejecutable administrado de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="46808-132">A managed Visual Basic executable calls an unmanaged function written in C by using platform invoke.</span></span>|`IHostTaskManager::LeaveRuntime`|  
|<span data-ttu-id="46808-133">La función de C no administrada llama a un método en un archivo DLL administrado escrita en C#.</span><span class="sxs-lookup"><span data-stu-id="46808-133">The unmanaged C function calls a method in a managed DLL written in C#.</span></span>|`IHostTaskManager::ReverseEnterRuntime`|  
|<span data-ttu-id="46808-134">Los recursos administrados C# función llama a otra función no administrado escrito en C, también usar invocación de plataforma.</span><span class="sxs-lookup"><span data-stu-id="46808-134">The managed C# function calls another unmanaged function written in C, also using platform invoke.</span></span>|`IHostTaskManager::LeaveRuntime`|  
|<span data-ttu-id="46808-135">La segunda función no administrada devuelve la ejecución a la C# función.</span><span class="sxs-lookup"><span data-stu-id="46808-135">The second unmanaged function returns execution to the C# function.</span></span>|`IHostTaskManager::EnterRuntime`|  
|<span data-ttu-id="46808-136">El C# función devuelve la ejecución a la primera función no administrada.</span><span class="sxs-lookup"><span data-stu-id="46808-136">The C# function returns execution to the first unmanaged function.</span></span>|`IHostTaskManager::ReverseLeaveRuntime`|  
|<span data-ttu-id="46808-137">La primera función no administrada devuelve la ejecución al programa de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="46808-137">The first unmanaged function returns execution to the Visual Basic program.</span></span>|`IHostTaskManager::EnterRuntime`|  
  
## <a name="requirements"></a><span data-ttu-id="46808-138">Requisitos</span><span class="sxs-lookup"><span data-stu-id="46808-138">Requirements</span></span>  
 <span data-ttu-id="46808-139">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="46808-139">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46808-140">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="46808-140">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="46808-141">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="46808-141">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="46808-142">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="46808-142">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="46808-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="46808-143">See also</span></span>

- [<span data-ttu-id="46808-144">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="46808-144">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="46808-145">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="46808-145">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="46808-146">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="46808-146">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="46808-147">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="46808-147">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
