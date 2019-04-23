---
title: IHostTask (Interfaz)
ms.date: 03/30/2017
api_name:
- IHostTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask
helpviewer_keywords:
- IHostTask interface [.NET Framework hosting]
ms.assetid: a71dbbd5-64b8-47eb-9f03-8e8c85fbe2bc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cb15da31d91565d49df83099045f742866eebcaa
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59081507"
---
# <a name="ihosttask-interface"></a><span data-ttu-id="b4536-102">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b4536-102">IHostTask Interface</span></span>
<span data-ttu-id="b4536-103">Proporciona métodos que permiten a common language runtime (CLR) para comunicarse con el host para administrar las tareas.</span><span class="sxs-lookup"><span data-stu-id="b4536-103">Provides methods that allow the common language runtime (CLR) to communicate with the host to manage tasks.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b4536-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="b4536-104">Methods</span></span>  
  
|<span data-ttu-id="b4536-105">Método</span><span class="sxs-lookup"><span data-stu-id="b4536-105">Method</span></span>|<span data-ttu-id="b4536-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="b4536-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b4536-107">Alert (método)</span><span class="sxs-lookup"><span data-stu-id="b4536-107">Alert Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md)|<span data-ttu-id="b4536-108">Las solicitudes que el host reactive la tarea representada por el actual `IHostTask` de instancia, por lo que se puede anular la tarea.</span><span class="sxs-lookup"><span data-stu-id="b4536-108">Requests that the host wake the task represented by the current `IHostTask` instance, so the task can be aborted.</span></span>|  
|[<span data-ttu-id="b4536-109">GetPriority (método)</span><span class="sxs-lookup"><span data-stu-id="b4536-109">GetPriority Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md)|<span data-ttu-id="b4536-110">Obtiene el nivel de prioridad de subproceso de la tarea representada por el actual `IHostTask` instancia.</span><span class="sxs-lookup"><span data-stu-id="b4536-110">Gets the thread priority level of the task represented by the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="b4536-111">Join (método)</span><span class="sxs-lookup"><span data-stu-id="b4536-111">Join Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-join-method.md)|<span data-ttu-id="b4536-112">Bloquea la tarea que realiza la llamada hasta que la tarea representada por el actual `IHostTask` instancia se haya completado, transcurre el intervalo de tiempo especificado, o [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) se llama.</span><span class="sxs-lookup"><span data-stu-id="b4536-112">Blocks the calling task until the task represented by the current `IHostTask` instance completes, the specified time interval elapses, or [IHostTask::Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) is called.</span></span>|  
|[<span data-ttu-id="b4536-113">SetCLRTask (método)</span><span class="sxs-lookup"><span data-stu-id="b4536-113">SetCLRTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md)|<span data-ttu-id="b4536-114">Asocia un [ICLRTask (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instancia con el actual `IHostTask` instancia.</span><span class="sxs-lookup"><span data-stu-id="b4536-114">Associates an [ICLRTask Interface](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance with the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="b4536-115">SetPriority (método)</span><span class="sxs-lookup"><span data-stu-id="b4536-115">SetPriority Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setpriority-method.md)|<span data-ttu-id="b4536-116">Solicita que el host ajuste la prioridad del subproceso de nivel de la tarea representada por el actual `IHostTask` instancia.</span><span class="sxs-lookup"><span data-stu-id="b4536-116">Requests that the host adjust the thread priority level for the task represented by the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="b4536-117">Start (método)</span><span class="sxs-lookup"><span data-stu-id="b4536-117">Start Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md)|<span data-ttu-id="b4536-118">Solicita que el host mueva la tarea representada por el actual `IHostTask` instancia desde un estado suspendido al estado activo, en el que se puede ejecutar el código.</span><span class="sxs-lookup"><span data-stu-id="b4536-118">Requests that the host move the task represented by the current `IHostTask` instance from a suspended state to a live state, in which code can be executed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b4536-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b4536-119">Remarks</span></span>  
 <span data-ttu-id="b4536-120">CLR llama a métodos definidos por `IHostTask` para iniciar una tarea, establezca la prioridad de subproceso nivel, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="b4536-120">The CLR calls methods defined by `IHostTask` to start a task, set its thread priority level, and so on.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4536-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b4536-121">Requirements</span></span>  
 <span data-ttu-id="b4536-122">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4536-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4536-123">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b4536-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b4536-124">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b4536-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b4536-125">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4536-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4536-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="b4536-126">See also</span></span>

- [<span data-ttu-id="b4536-127">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b4536-127">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="b4536-128">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b4536-128">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="b4536-129">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b4536-129">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="b4536-130">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="b4536-130">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
