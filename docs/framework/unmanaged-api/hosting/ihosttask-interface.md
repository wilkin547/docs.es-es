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
ms.openlocfilehash: 18dfee606f3d41229aa58a5b4bb9380b87c4efa5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121396"
---
# <a name="ihosttask-interface"></a><span data-ttu-id="3d125-102">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3d125-102">IHostTask Interface</span></span>
<span data-ttu-id="3d125-103">Proporciona métodos que permiten al Common Language Runtime (CLR) comunicarse con el host para administrar tareas.</span><span class="sxs-lookup"><span data-stu-id="3d125-103">Provides methods that allow the common language runtime (CLR) to communicate with the host to manage tasks.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3d125-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="3d125-104">Methods</span></span>  
  
|<span data-ttu-id="3d125-105">Método</span><span class="sxs-lookup"><span data-stu-id="3d125-105">Method</span></span>|<span data-ttu-id="3d125-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="3d125-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3d125-107">Alert (método)</span><span class="sxs-lookup"><span data-stu-id="3d125-107">Alert Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md)|<span data-ttu-id="3d125-108">Solicita que el host reactive la tarea representada por la instancia de `IHostTask` actual, por lo que se puede anular la tarea.</span><span class="sxs-lookup"><span data-stu-id="3d125-108">Requests that the host wake the task represented by the current `IHostTask` instance, so the task can be aborted.</span></span>|  
|[<span data-ttu-id="3d125-109">GetPriority (método)</span><span class="sxs-lookup"><span data-stu-id="3d125-109">GetPriority Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md)|<span data-ttu-id="3d125-110">Obtiene el nivel de prioridad del subproceso de la tarea representada por la instancia de `IHostTask` actual.</span><span class="sxs-lookup"><span data-stu-id="3d125-110">Gets the thread priority level of the task represented by the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="3d125-111">Join (método)</span><span class="sxs-lookup"><span data-stu-id="3d125-111">Join Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-join-method.md)|<span data-ttu-id="3d125-112">Bloquea la tarea que realiza la llamada hasta que se completa la tarea representada por la instancia de `IHostTask` actual, transcurre el intervalo de tiempo especificado o se llama a [IHostTask:: Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) .</span><span class="sxs-lookup"><span data-stu-id="3d125-112">Blocks the calling task until the task represented by the current `IHostTask` instance completes, the specified time interval elapses, or [IHostTask::Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) is called.</span></span>|  
|[<span data-ttu-id="3d125-113">SetCLRTask (método)</span><span class="sxs-lookup"><span data-stu-id="3d125-113">SetCLRTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md)|<span data-ttu-id="3d125-114">Asocia una instancia de la [interfaz ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) a la instancia de `IHostTask` actual.</span><span class="sxs-lookup"><span data-stu-id="3d125-114">Associates an [ICLRTask Interface](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance with the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="3d125-115">SetPriority (método)</span><span class="sxs-lookup"><span data-stu-id="3d125-115">SetPriority Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setpriority-method.md)|<span data-ttu-id="3d125-116">Solicita que el host ajuste el nivel de prioridad del subproceso para la tarea representada por la instancia de `IHostTask` actual.</span><span class="sxs-lookup"><span data-stu-id="3d125-116">Requests that the host adjust the thread priority level for the task represented by the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="3d125-117">Start (método)</span><span class="sxs-lookup"><span data-stu-id="3d125-117">Start Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md)|<span data-ttu-id="3d125-118">Solicita que el host mueva la tarea representada por la instancia de `IHostTask` actual de un estado suspendido a un estado activo, en el que se puede ejecutar el código.</span><span class="sxs-lookup"><span data-stu-id="3d125-118">Requests that the host move the task represented by the current `IHostTask` instance from a suspended state to a live state, in which code can be executed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3d125-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3d125-119">Remarks</span></span>  
 <span data-ttu-id="3d125-120">CLR llama a métodos definidos por `IHostTask` para iniciar una tarea, establecer su nivel de prioridad de subprocesos, etc.</span><span class="sxs-lookup"><span data-stu-id="3d125-120">The CLR calls methods defined by `IHostTask` to start a task, set its thread priority level, and so on.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d125-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3d125-121">Requirements</span></span>  
 <span data-ttu-id="3d125-122">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d125-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d125-123">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="3d125-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3d125-124">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="3d125-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3d125-125">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d125-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d125-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="3d125-126">See also</span></span>

- [<span data-ttu-id="3d125-127">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3d125-127">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="3d125-128">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3d125-128">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="3d125-129">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3d125-129">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="3d125-130">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="3d125-130">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
