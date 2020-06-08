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
ms.openlocfilehash: 1b7209a36f8e9d6f02bd4cc1882adeef8af30c3d
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503935"
---
# <a name="ihosttask-interface"></a><span data-ttu-id="f7f6a-102">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f7f6a-102">IHostTask Interface</span></span>
<span data-ttu-id="f7f6a-103">Proporciona métodos que permiten al Common Language Runtime (CLR) comunicarse con el host para administrar tareas.</span><span class="sxs-lookup"><span data-stu-id="f7f6a-103">Provides methods that allow the common language runtime (CLR) to communicate with the host to manage tasks.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f7f6a-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="f7f6a-104">Methods</span></span>  
  
|<span data-ttu-id="f7f6a-105">Método</span><span class="sxs-lookup"><span data-stu-id="f7f6a-105">Method</span></span>|<span data-ttu-id="f7f6a-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="f7f6a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f7f6a-107">Método Alert</span><span class="sxs-lookup"><span data-stu-id="f7f6a-107">Alert Method</span></span>](ihosttask-alert-method.md)|<span data-ttu-id="f7f6a-108">Solicita que el host reactive la tarea representada por la `IHostTask` instancia actual, por lo que se puede anular la tarea.</span><span class="sxs-lookup"><span data-stu-id="f7f6a-108">Requests that the host wake the task represented by the current `IHostTask` instance, so the task can be aborted.</span></span>|  
|[<span data-ttu-id="f7f6a-109">Método GetPriority</span><span class="sxs-lookup"><span data-stu-id="f7f6a-109">GetPriority Method</span></span>](ihosttask-getpriority-method.md)|<span data-ttu-id="f7f6a-110">Obtiene el nivel de prioridad del subproceso de la tarea representada por la `IHostTask` instancia actual.</span><span class="sxs-lookup"><span data-stu-id="f7f6a-110">Gets the thread priority level of the task represented by the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="f7f6a-111">Método Join</span><span class="sxs-lookup"><span data-stu-id="f7f6a-111">Join Method</span></span>](ihosttask-join-method.md)|<span data-ttu-id="f7f6a-112">Bloquea la tarea que realiza la llamada hasta que se completa la tarea representada por la `IHostTask` instancia actual, el intervalo de tiempo especificado transcurre o se llama a [IHostTask:: Alert](ihosttask-alert-method.md) .</span><span class="sxs-lookup"><span data-stu-id="f7f6a-112">Blocks the calling task until the task represented by the current `IHostTask` instance completes, the specified time interval elapses, or [IHostTask::Alert](ihosttask-alert-method.md) is called.</span></span>|  
|[<span data-ttu-id="f7f6a-113">Método SetCLRTask</span><span class="sxs-lookup"><span data-stu-id="f7f6a-113">SetCLRTask Method</span></span>](ihosttask-setclrtask-method.md)|<span data-ttu-id="f7f6a-114">Asocia una instancia de la [interfaz ICLRTask](iclrtask-interface.md) a la `IHostTask` instancia actual.</span><span class="sxs-lookup"><span data-stu-id="f7f6a-114">Associates an [ICLRTask Interface](iclrtask-interface.md) instance with the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="f7f6a-115">Método SetPriority</span><span class="sxs-lookup"><span data-stu-id="f7f6a-115">SetPriority Method</span></span>](ihosttask-setpriority-method.md)|<span data-ttu-id="f7f6a-116">Solicita que el host ajuste el nivel de prioridad del subproceso para la tarea representada por la `IHostTask` instancia actual.</span><span class="sxs-lookup"><span data-stu-id="f7f6a-116">Requests that the host adjust the thread priority level for the task represented by the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="f7f6a-117">Start (método)</span><span class="sxs-lookup"><span data-stu-id="f7f6a-117">Start Method</span></span>](ihosttask-start-method.md)|<span data-ttu-id="f7f6a-118">Solicita que el host mueva la tarea representada por la `IHostTask` instancia actual de un estado suspendido a un estado activo, en el que se puede ejecutar el código.</span><span class="sxs-lookup"><span data-stu-id="f7f6a-118">Requests that the host move the task represented by the current `IHostTask` instance from a suspended state to a live state, in which code can be executed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f7f6a-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f7f6a-119">Remarks</span></span>  
 <span data-ttu-id="f7f6a-120">CLR llama a los métodos definidos por `IHostTask` para iniciar una tarea, establecer su nivel de prioridad de subprocesos, etc.</span><span class="sxs-lookup"><span data-stu-id="f7f6a-120">The CLR calls methods defined by `IHostTask` to start a task, set its thread priority level, and so on.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7f6a-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f7f6a-121">Requirements</span></span>  
 <span data-ttu-id="f7f6a-122">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f7f6a-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7f6a-123">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f7f6a-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f7f6a-124">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f7f6a-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f7f6a-125">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7f6a-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7f6a-126">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="f7f6a-126">See also</span></span>

- [<span data-ttu-id="f7f6a-127">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f7f6a-127">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="f7f6a-128">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f7f6a-128">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="f7f6a-129">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f7f6a-129">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="f7f6a-130">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="f7f6a-130">Hosting Interfaces</span></span>](hosting-interfaces.md)
