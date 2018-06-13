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
ms.openlocfilehash: df1fb24c4003f77523ef01a4029fd19cc55a3fef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33442226"
---
# <a name="ihosttask-interface"></a><span data-ttu-id="35d1b-102">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="35d1b-102">IHostTask Interface</span></span>
<span data-ttu-id="35d1b-103">Proporciona métodos que permiten a common language runtime (CLR) para comunicarse con el host para administrar las tareas.</span><span class="sxs-lookup"><span data-stu-id="35d1b-103">Provides methods that allow the common language runtime (CLR) to communicate with the host to manage tasks.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="35d1b-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="35d1b-104">Methods</span></span>  
  
|<span data-ttu-id="35d1b-105">Método</span><span class="sxs-lookup"><span data-stu-id="35d1b-105">Method</span></span>|<span data-ttu-id="35d1b-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="35d1b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="35d1b-107">Alert (método)</span><span class="sxs-lookup"><span data-stu-id="35d1b-107">Alert Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md)|<span data-ttu-id="35d1b-108">Las solicitudes que el host reactive la tarea representada por el actual `IHostTask` instancia, por lo que se puede anular la tarea.</span><span class="sxs-lookup"><span data-stu-id="35d1b-108">Requests that the host wake the task represented by the current `IHostTask` instance, so the task can be aborted.</span></span>|  
|[<span data-ttu-id="35d1b-109">GetPriority (método)</span><span class="sxs-lookup"><span data-stu-id="35d1b-109">GetPriority Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md)|<span data-ttu-id="35d1b-110">Obtiene el nivel de prioridad de subproceso de la tarea representada por el actual `IHostTask` instancia.</span><span class="sxs-lookup"><span data-stu-id="35d1b-110">Gets the thread priority level of the task represented by the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="35d1b-111">Join (método)</span><span class="sxs-lookup"><span data-stu-id="35d1b-111">Join Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-join-method.md)|<span data-ttu-id="35d1b-112">La tarea que realiza la llamada se bloquea hasta que finaliza la tarea representada por el actual `IHostTask` completa de la instancia, se agota el tiempo especificado, o [IHostTask:: Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) se llama.</span><span class="sxs-lookup"><span data-stu-id="35d1b-112">Blocks the calling task until the task represented by the current `IHostTask` instance completes, the specified time interval elapses, or [IHostTask::Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) is called.</span></span>|  
|[<span data-ttu-id="35d1b-113">SetCLRTask (método)</span><span class="sxs-lookup"><span data-stu-id="35d1b-113">SetCLRTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md)|<span data-ttu-id="35d1b-114">Asocia un [ICLRTask (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instancia con el actual `IHostTask` instancia.</span><span class="sxs-lookup"><span data-stu-id="35d1b-114">Associates an [ICLRTask Interface](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance with the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="35d1b-115">SetPriority (método)</span><span class="sxs-lookup"><span data-stu-id="35d1b-115">SetPriority Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setpriority-method.md)|<span data-ttu-id="35d1b-116">Solicita que el host ajuste la prioridad del subproceso de nivel para la tarea representada por el actual `IHostTask` instancia.</span><span class="sxs-lookup"><span data-stu-id="35d1b-116">Requests that the host adjust the thread priority level for the task represented by the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="35d1b-117">Start (método)</span><span class="sxs-lookup"><span data-stu-id="35d1b-117">Start Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md)|<span data-ttu-id="35d1b-118">Solicita que el host mueva la tarea representada por el actual `IHostTask` instancia desde un estado suspendido al estado activo, en el que se puede ejecutar código.</span><span class="sxs-lookup"><span data-stu-id="35d1b-118">Requests that the host move the task represented by the current `IHostTask` instance from a suspended state to a live state, in which code can be executed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="35d1b-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="35d1b-119">Remarks</span></span>  
 <span data-ttu-id="35d1b-120">CLR llama a métodos definidos por `IHostTask` para iniciar una tarea, establece su prioridad de subproceso nivel, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="35d1b-120">The CLR calls methods defined by `IHostTask` to start a task, set its thread priority level, and so on.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35d1b-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="35d1b-121">Requirements</span></span>  
 <span data-ttu-id="35d1b-122">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35d1b-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35d1b-123">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="35d1b-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="35d1b-124">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="35d1b-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="35d1b-125">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35d1b-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35d1b-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="35d1b-126">See Also</span></span>  
 [<span data-ttu-id="35d1b-127">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="35d1b-127">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="35d1b-128">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="35d1b-128">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="35d1b-129">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="35d1b-129">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="35d1b-130">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="35d1b-130">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
