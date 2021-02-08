---
description: 'Más información sobre: interfaz IHostTask'
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
ms.openlocfilehash: c46bbdd2e881c20d1ffd634bec8ddfa3b70b0f82
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784670"
---
# <a name="ihosttask-interface"></a><span data-ttu-id="499c2-103">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="499c2-103">IHostTask Interface</span></span>

<span data-ttu-id="499c2-104">Proporciona métodos que permiten al Common Language Runtime (CLR) comunicarse con el host para administrar tareas.</span><span class="sxs-lookup"><span data-stu-id="499c2-104">Provides methods that allow the common language runtime (CLR) to communicate with the host to manage tasks.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="499c2-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="499c2-105">Methods</span></span>  
  
|<span data-ttu-id="499c2-106">Método</span><span class="sxs-lookup"><span data-stu-id="499c2-106">Method</span></span>|<span data-ttu-id="499c2-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="499c2-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="499c2-108">Método Alert</span><span class="sxs-lookup"><span data-stu-id="499c2-108">Alert Method</span></span>](ihosttask-alert-method.md)|<span data-ttu-id="499c2-109">Solicita que el host reactive la tarea representada por la `IHostTask` instancia actual, por lo que se puede anular la tarea.</span><span class="sxs-lookup"><span data-stu-id="499c2-109">Requests that the host wake the task represented by the current `IHostTask` instance, so the task can be aborted.</span></span>|  
|[<span data-ttu-id="499c2-110">Método GetPriority</span><span class="sxs-lookup"><span data-stu-id="499c2-110">GetPriority Method</span></span>](ihosttask-getpriority-method.md)|<span data-ttu-id="499c2-111">Obtiene el nivel de prioridad del subproceso de la tarea representada por la `IHostTask` instancia actual.</span><span class="sxs-lookup"><span data-stu-id="499c2-111">Gets the thread priority level of the task represented by the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="499c2-112">Método Join</span><span class="sxs-lookup"><span data-stu-id="499c2-112">Join Method</span></span>](ihosttask-join-method.md)|<span data-ttu-id="499c2-113">Bloquea la tarea que realiza la llamada hasta que se completa la tarea representada por la `IHostTask` instancia actual, el intervalo de tiempo especificado transcurre o se llama a [IHostTask:: Alert](ihosttask-alert-method.md) .</span><span class="sxs-lookup"><span data-stu-id="499c2-113">Blocks the calling task until the task represented by the current `IHostTask` instance completes, the specified time interval elapses, or [IHostTask::Alert](ihosttask-alert-method.md) is called.</span></span>|  
|[<span data-ttu-id="499c2-114">Método SetCLRTask</span><span class="sxs-lookup"><span data-stu-id="499c2-114">SetCLRTask Method</span></span>](ihosttask-setclrtask-method.md)|<span data-ttu-id="499c2-115">Asocia una instancia de la [interfaz ICLRTask](iclrtask-interface.md) a la `IHostTask` instancia actual.</span><span class="sxs-lookup"><span data-stu-id="499c2-115">Associates an [ICLRTask Interface](iclrtask-interface.md) instance with the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="499c2-116">Método SetPriority</span><span class="sxs-lookup"><span data-stu-id="499c2-116">SetPriority Method</span></span>](ihosttask-setpriority-method.md)|<span data-ttu-id="499c2-117">Solicita que el host ajuste el nivel de prioridad del subproceso para la tarea representada por la `IHostTask` instancia actual.</span><span class="sxs-lookup"><span data-stu-id="499c2-117">Requests that the host adjust the thread priority level for the task represented by the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="499c2-118">Start (método)</span><span class="sxs-lookup"><span data-stu-id="499c2-118">Start Method</span></span>](ihosttask-start-method.md)|<span data-ttu-id="499c2-119">Solicita que el host mueva la tarea representada por la `IHostTask` instancia actual de un estado suspendido a un estado activo, en el que se puede ejecutar el código.</span><span class="sxs-lookup"><span data-stu-id="499c2-119">Requests that the host move the task represented by the current `IHostTask` instance from a suspended state to a live state, in which code can be executed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="499c2-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="499c2-120">Remarks</span></span>  

 <span data-ttu-id="499c2-121">CLR llama a los métodos definidos por `IHostTask` para iniciar una tarea, establecer su nivel de prioridad de subprocesos, etc.</span><span class="sxs-lookup"><span data-stu-id="499c2-121">The CLR calls methods defined by `IHostTask` to start a task, set its thread priority level, and so on.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="499c2-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="499c2-122">Requirements</span></span>  

 <span data-ttu-id="499c2-123">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="499c2-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="499c2-124">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="499c2-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="499c2-125">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="499c2-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="499c2-126">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="499c2-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="499c2-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="499c2-127">See also</span></span>

- [<span data-ttu-id="499c2-128">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="499c2-128">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="499c2-129">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="499c2-129">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="499c2-130">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="499c2-130">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="499c2-131">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="499c2-131">Hosting Interfaces</span></span>](hosting-interfaces.md)
