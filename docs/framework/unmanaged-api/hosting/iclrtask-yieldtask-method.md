---
description: 'Más información acerca de: ICLRTask:: Yieldtask ((método)'
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
ms.openlocfilehash: b72b31b0a1c10a2b0b1e2ad379b140ff33419fa1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784930"
---
# <a name="iclrtaskyieldtask-method"></a><span data-ttu-id="30253-103">ICLRTask::YieldTask (Método)</span><span class="sxs-lookup"><span data-stu-id="30253-103">ICLRTask::YieldTask Method</span></span>

<span data-ttu-id="30253-104">Solicita que el Common Language Runtime (CLR) Reserve la tarea que representa la instancia actual de [ICLRTask](iclrtask-interface.md) y que el tiempo de procesador esté disponible para otras tareas.</span><span class="sxs-lookup"><span data-stu-id="30253-104">Requests that the common language runtime (CLR) put aside the task that the current [ICLRTask](iclrtask-interface.md) instance represents, and make the processor time available to other tasks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30253-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="30253-105">Syntax</span></span>  
  
```cpp  
HRESULT YieldTask ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="30253-106">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="30253-106">Return Value</span></span>  
  
|<span data-ttu-id="30253-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="30253-107">HRESULT</span></span>|<span data-ttu-id="30253-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="30253-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="30253-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="30253-109">S_OK</span></span>|<span data-ttu-id="30253-110">`YieldTask` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="30253-110">`YieldTask` returned successfully.</span></span>|  
|<span data-ttu-id="30253-111">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="30253-111">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="30253-112">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="30253-112">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="30253-113">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="30253-113">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="30253-114">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="30253-114">The call timed out.</span></span>|  
|<span data-ttu-id="30253-115">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="30253-115">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="30253-116">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="30253-116">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="30253-117">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="30253-117">HOST_E_ABANDONED</span></span>|<span data-ttu-id="30253-118">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="30253-118">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="30253-119">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="30253-119">E_FAIL</span></span>|<span data-ttu-id="30253-120">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="30253-120">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="30253-121">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="30253-121">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="30253-122">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="30253-122">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="30253-123">Observaciones</span><span class="sxs-lookup"><span data-stu-id="30253-123">Remarks</span></span>  

 <span data-ttu-id="30253-124">Un host llama `YieldTask` a para solicitar recursos del procesador para otras tareas o procesos.</span><span class="sxs-lookup"><span data-stu-id="30253-124">A host calls `YieldTask` to request processor resources for other tasks or processes.</span></span> <span data-ttu-id="30253-125">Este método está pensado principalmente para permitir que el código de ejecución prolongada deje tiempo de CPU.</span><span class="sxs-lookup"><span data-stu-id="30253-125">This method is primarily intended to allow long-running code to give up CPU time.</span></span> <span data-ttu-id="30253-126">El motor en tiempo de ejecución intenta colocar la tarea que la `ICLRTask` instancia actual representa en un estado en el que puede producir el tiempo de procesamiento, pero no garantiza el éxito.</span><span class="sxs-lookup"><span data-stu-id="30253-126">The runtime attempts to put the task that the current `ICLRTask` instance represents in a state where it can yield processing time, but makes no guarantee of success.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30253-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="30253-127">Requirements</span></span>  

 <span data-ttu-id="30253-128">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30253-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30253-129">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="30253-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="30253-130">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="30253-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="30253-131">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30253-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30253-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="30253-132">See also</span></span>

- [<span data-ttu-id="30253-133">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="30253-133">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="30253-134">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="30253-134">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="30253-135">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="30253-135">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="30253-136">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="30253-136">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
