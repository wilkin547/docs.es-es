---
title: ICLRTask::YieldTask (Método)
ms.date: 03/30/2017
api_name:
- ICLRTask.YieldTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::YieldTask
helpviewer_keywords:
- ICLRTask::YieldTask method [.NET Framework hosting]
- YieldTask method [.NET Framework hosting]
ms.assetid: b8eb4095-3a8f-4be3-9446-63e9893dce7d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bc8d936ac4fca704e7e3069209d8ff75d46b044d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59113677"
---
# <a name="iclrtaskyieldtask-method"></a><span data-ttu-id="e3b3e-102">ICLRTask::YieldTask (Método)</span><span class="sxs-lookup"><span data-stu-id="e3b3e-102">ICLRTask::YieldTask Method</span></span>
<span data-ttu-id="e3b3e-103">Solicita que common language runtime (CLR) aparte la tarea que actual [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) representa la instancia y que el tiempo de procesador esté disponible para otras tareas.</span><span class="sxs-lookup"><span data-stu-id="e3b3e-103">Requests that the common language runtime (CLR) put aside the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents, and make the processor time available to other tasks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3b3e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e3b3e-104">Syntax</span></span>  
  
```  
HRESULT YieldTask ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="e3b3e-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e3b3e-105">Return Value</span></span>  
  
|<span data-ttu-id="e3b3e-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e3b3e-106">HRESULT</span></span>|<span data-ttu-id="e3b3e-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="e3b3e-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e3b3e-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="e3b3e-108">S_OK</span></span>|<span data-ttu-id="e3b3e-109">`YieldTask` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="e3b3e-109">`YieldTask` returned successfully.</span></span>|  
|<span data-ttu-id="e3b3e-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e3b3e-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e3b3e-111">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="e3b3e-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e3b3e-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e3b3e-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e3b3e-113">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="e3b3e-113">The call timed out.</span></span>|  
|<span data-ttu-id="e3b3e-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e3b3e-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e3b3e-115">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="e3b3e-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e3b3e-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e3b3e-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e3b3e-117">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="e3b3e-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e3b3e-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e3b3e-118">E_FAIL</span></span>|<span data-ttu-id="e3b3e-119">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="e3b3e-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e3b3e-120">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="e3b3e-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e3b3e-121">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e3b3e-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e3b3e-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e3b3e-122">Remarks</span></span>  
 <span data-ttu-id="e3b3e-123">Un host llama `YieldTask` para solicitar recursos del procesador para otras tareas o procesos.</span><span class="sxs-lookup"><span data-stu-id="e3b3e-123">A host calls `YieldTask` to request processor resources for other tasks or processes.</span></span> <span data-ttu-id="e3b3e-124">Este método está pensado principalmente para permitir que el código de ejecución prolongada dar tiempo de CPU.</span><span class="sxs-lookup"><span data-stu-id="e3b3e-124">This method is primarily intended to allow long-running code to give up CPU time.</span></span> <span data-ttu-id="e3b3e-125">El tiempo de ejecución intenta colocar la tarea que actual `ICLRTask` instancia representa un estado donde se puede producir tiempo de procesamiento, pero no otorga ninguna garantía de éxito.</span><span class="sxs-lookup"><span data-stu-id="e3b3e-125">The runtime attempts to put the task that the current `ICLRTask` instance represents in a state where it can yield processing time, but makes no guarantee of success.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3b3e-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e3b3e-126">Requirements</span></span>  
 <span data-ttu-id="e3b3e-127">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e3b3e-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3b3e-128">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e3b3e-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e3b3e-129">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e3b3e-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e3b3e-130">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3b3e-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3b3e-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="e3b3e-131">See also</span></span>

- [<span data-ttu-id="e3b3e-132">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e3b3e-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="e3b3e-133">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e3b3e-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="e3b3e-134">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e3b3e-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="e3b3e-135">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e3b3e-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
