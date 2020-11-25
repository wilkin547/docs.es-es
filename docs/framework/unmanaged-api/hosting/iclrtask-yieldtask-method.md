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
ms.openlocfilehash: 7b9b47daa96ffcb1f66b462ff8e227250c5a81ca
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720287"
---
# <a name="iclrtaskyieldtask-method"></a><span data-ttu-id="8e65d-102">ICLRTask::YieldTask (Método)</span><span class="sxs-lookup"><span data-stu-id="8e65d-102">ICLRTask::YieldTask Method</span></span>

<span data-ttu-id="8e65d-103">Solicita que el Common Language Runtime (CLR) Reserve la tarea que representa la instancia actual de [ICLRTask](iclrtask-interface.md) y que el tiempo de procesador esté disponible para otras tareas.</span><span class="sxs-lookup"><span data-stu-id="8e65d-103">Requests that the common language runtime (CLR) put aside the task that the current [ICLRTask](iclrtask-interface.md) instance represents, and make the processor time available to other tasks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e65d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8e65d-104">Syntax</span></span>  
  
```cpp  
HRESULT YieldTask ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="8e65d-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8e65d-105">Return Value</span></span>  
  
|<span data-ttu-id="8e65d-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8e65d-106">HRESULT</span></span>|<span data-ttu-id="8e65d-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="8e65d-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8e65d-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="8e65d-108">S_OK</span></span>|<span data-ttu-id="8e65d-109">`YieldTask` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="8e65d-109">`YieldTask` returned successfully.</span></span>|  
|<span data-ttu-id="8e65d-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8e65d-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8e65d-111">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="8e65d-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8e65d-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8e65d-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8e65d-113">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="8e65d-113">The call timed out.</span></span>|  
|<span data-ttu-id="8e65d-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8e65d-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8e65d-115">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="8e65d-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8e65d-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8e65d-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8e65d-117">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="8e65d-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8e65d-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8e65d-118">E_FAIL</span></span>|<span data-ttu-id="8e65d-119">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="8e65d-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8e65d-120">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="8e65d-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8e65d-121">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="8e65d-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8e65d-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8e65d-122">Remarks</span></span>  

 <span data-ttu-id="8e65d-123">Un host llama `YieldTask` a para solicitar recursos del procesador para otras tareas o procesos.</span><span class="sxs-lookup"><span data-stu-id="8e65d-123">A host calls `YieldTask` to request processor resources for other tasks or processes.</span></span> <span data-ttu-id="8e65d-124">Este método está pensado principalmente para permitir que el código de ejecución prolongada deje tiempo de CPU.</span><span class="sxs-lookup"><span data-stu-id="8e65d-124">This method is primarily intended to allow long-running code to give up CPU time.</span></span> <span data-ttu-id="8e65d-125">El motor en tiempo de ejecución intenta colocar la tarea que la `ICLRTask` instancia actual representa en un estado en el que puede producir el tiempo de procesamiento, pero no garantiza el éxito.</span><span class="sxs-lookup"><span data-stu-id="8e65d-125">The runtime attempts to put the task that the current `ICLRTask` instance represents in a state where it can yield processing time, but makes no guarantee of success.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e65d-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8e65d-126">Requirements</span></span>  

 <span data-ttu-id="8e65d-127">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8e65d-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e65d-128">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="8e65d-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8e65d-129">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8e65d-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8e65d-130">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e65d-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e65d-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8e65d-131">See also</span></span>

- [<span data-ttu-id="8e65d-132">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8e65d-132">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="8e65d-133">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8e65d-133">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="8e65d-134">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8e65d-134">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="8e65d-135">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8e65d-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
