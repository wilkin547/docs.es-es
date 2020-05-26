---
title: IHostGCManager::ThreadIsBlockingForSuspension (Método)
ms.date: 03/30/2017
api_name:
- IHostGCManager.ThreadIsBlockingForSuspension
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostGCManager::ThreadIsBlockingForSuspension
helpviewer_keywords:
- IHostGCManager::ThreadIsBlockingForSuspension method [.NET Framework hosting]
- ThreadIsBlockingForSuspension method [.NET Framework hosting]
ms.assetid: 2657d45d-26d2-4d0a-8473-32b652e3321d
topic_type:
- apiref
ms.openlocfilehash: 0417a4acc0f4f39d8254eb5d5df3b3e690921a8a
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804828"
---
# <a name="ihostgcmanagerthreadisblockingforsuspension-method"></a><span data-ttu-id="3130a-102">IHostGCManager::ThreadIsBlockingForSuspension (Método)</span><span class="sxs-lookup"><span data-stu-id="3130a-102">IHostGCManager::ThreadIsBlockingForSuspension Method</span></span>
<span data-ttu-id="3130a-103">Notifica al host que el subproceso del que se realizó la llamada al método está a punto de bloquearse para una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="3130a-103">Notifies the host that the thread from which the method call was made is about to block for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3130a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3130a-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadIsBlockingForSuspension ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="3130a-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3130a-105">Return Value</span></span>  
  
|<span data-ttu-id="3130a-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3130a-106">HRESULT</span></span>|<span data-ttu-id="3130a-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="3130a-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3130a-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="3130a-108">S_OK</span></span>|<span data-ttu-id="3130a-109">`ThreadIsBlockingForSuspension`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="3130a-109">`ThreadIsBlockingForSuspension` returned successfully.</span></span>|  
|<span data-ttu-id="3130a-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3130a-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3130a-111">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="3130a-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3130a-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3130a-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3130a-113">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="3130a-113">The call timed out.</span></span>|  
|<span data-ttu-id="3130a-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3130a-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3130a-115">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="3130a-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3130a-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3130a-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3130a-117">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="3130a-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3130a-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3130a-118">E_FAIL</span></span>|<span data-ttu-id="3130a-119">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="3130a-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3130a-120">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="3130a-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3130a-121">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="3130a-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3130a-122">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3130a-122">Remarks</span></span>  
 <span data-ttu-id="3130a-123">El CLR normalmente llama al `ThreadIsBlockForSuspension` método como preparación para una recolección de elementos no utilizados, para dar al host una oportunidad de volver a programar el subproceso para las tareas no administradas.</span><span class="sxs-lookup"><span data-stu-id="3130a-123">The CLR typically calls the `ThreadIsBlockForSuspension` method in preparation for a garbage collection, to give the host an opportunity to reschedule the thread for unmanaged tasks.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="3130a-124">El host puede volver a programar las tareas solo después de una llamada a `ThreadIsBlockingForSuspension` .</span><span class="sxs-lookup"><span data-stu-id="3130a-124">The host can reschedule tasks only after a call to `ThreadIsBlockingForSuspension`.</span></span> <span data-ttu-id="3130a-125">Una vez que el Runtime llama a [SuspensionStarting (](ihostgcmanager-suspensionstarting-method.md), el host no debe volver a programar una tarea.</span><span class="sxs-lookup"><span data-stu-id="3130a-125">After the runtime calls [SuspensionStarting](ihostgcmanager-suspensionstarting-method.md), the host must not reschedule a task.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3130a-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3130a-126">Requirements</span></span>  
 <span data-ttu-id="3130a-127">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3130a-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3130a-128">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="3130a-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3130a-129">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="3130a-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3130a-130">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3130a-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3130a-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3130a-131">See also</span></span>

- [<span data-ttu-id="3130a-132">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3130a-132">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="3130a-133">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3130a-133">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="3130a-134">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3130a-134">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="3130a-135">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3130a-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="3130a-136">IHostGCManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3130a-136">IHostGCManager Interface</span></span>](ihostgcmanager-interface.md)
