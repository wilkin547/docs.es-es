---
title: IHostGCManager::SuspensionStarting (Método)
ms.date: 03/30/2017
api_name:
- IHostGCManager.SuspensionStarting
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostGCManager::SuspensionStarting
helpviewer_keywords:
- SuspensionStarting method, IHostGCManager interface [.NET Framework hosting]
- IHostGCManager::SuspensionStarting method [.NET Framework hosting]
ms.assetid: c381f524-94cf-4fa2-9298-50f847a03431
topic_type:
- apiref
ms.openlocfilehash: 7e610676e86dde3ab0bdea2ce2314f02b3da9976
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729504"
---
# <a name="ihostgcmanagersuspensionstarting-method"></a><span data-ttu-id="9365a-102">IHostGCManager::SuspensionStarting (Método)</span><span class="sxs-lookup"><span data-stu-id="9365a-102">IHostGCManager::SuspensionStarting Method</span></span>

<span data-ttu-id="9365a-103">Notifica al host que el Common Language Runtime (CLR) está suspendiendo la ejecución de las tareas, para realizar una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="9365a-103">Notifies the host that the common language runtime (CLR) is suspending execution of tasks, to perform a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9365a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9365a-104">Syntax</span></span>  
  
```cpp  
HRESULT SuspensionStarting ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="9365a-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9365a-105">Return Value</span></span>  
  
|<span data-ttu-id="9365a-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9365a-106">HRESULT</span></span>|<span data-ttu-id="9365a-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="9365a-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9365a-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="9365a-108">S_OK</span></span>|<span data-ttu-id="9365a-109">`SuspensionStarting` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="9365a-109">`SuspensionStarting` returned successfully.</span></span>|  
|<span data-ttu-id="9365a-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9365a-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9365a-111">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="9365a-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9365a-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9365a-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9365a-113">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="9365a-113">The call timed out.</span></span>|  
|<span data-ttu-id="9365a-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9365a-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9365a-115">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="9365a-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9365a-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9365a-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9365a-117">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="9365a-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9365a-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9365a-118">E_FAIL</span></span>|<span data-ttu-id="9365a-119">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="9365a-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9365a-120">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="9365a-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9365a-121">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="9365a-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9365a-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9365a-122">Remarks</span></span>  

 <span data-ttu-id="9365a-123">Las llamadas CLR `SuspensionStarting` para informar al host de que se está produciendo la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="9365a-123">The CLR calls `SuspensionStarting` to inform the host that garbage collection is occurring.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="9365a-124">No vuelva a programar esta tarea.</span><span class="sxs-lookup"><span data-stu-id="9365a-124">Do not reschedule this task.</span></span> <span data-ttu-id="9365a-125">El host debe volver a programar una tarea cuando se llama a [ThreadIsBlockingForSuspension (](ihostgcmanager-threadisblockingforsuspension-method.md) .</span><span class="sxs-lookup"><span data-stu-id="9365a-125">The host must reschedule a task when [ThreadIsBlockingForSuspension](ihostgcmanager-threadisblockingforsuspension-method.md) is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9365a-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9365a-126">Requirements</span></span>  

 <span data-ttu-id="9365a-127">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9365a-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9365a-128">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="9365a-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9365a-129">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9365a-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9365a-130">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9365a-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9365a-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9365a-131">See also</span></span>

- [<span data-ttu-id="9365a-132">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9365a-132">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="9365a-133">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9365a-133">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="9365a-134">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9365a-134">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="9365a-135">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9365a-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="9365a-136">IHostGCManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9365a-136">IHostGCManager Interface</span></span>](ihostgcmanager-interface.md)
