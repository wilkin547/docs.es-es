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
ms.openlocfilehash: 43f2048c8ab85fa7e94f73aad430400ad4c8352f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124592"
---
# <a name="iclrtaskyieldtask-method"></a><span data-ttu-id="df922-102">ICLRTask::YieldTask (Método)</span><span class="sxs-lookup"><span data-stu-id="df922-102">ICLRTask::YieldTask Method</span></span>
<span data-ttu-id="df922-103">Solicita que el Common Language Runtime (CLR) Reserve la tarea que representa la instancia actual de [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) y que el tiempo de procesador esté disponible para otras tareas.</span><span class="sxs-lookup"><span data-stu-id="df922-103">Requests that the common language runtime (CLR) put aside the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents, and make the processor time available to other tasks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df922-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="df922-104">Syntax</span></span>  
  
```cpp  
HRESULT YieldTask ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="df922-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="df922-105">Return Value</span></span>  
  
|<span data-ttu-id="df922-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="df922-106">HRESULT</span></span>|<span data-ttu-id="df922-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="df922-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="df922-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="df922-108">S_OK</span></span>|<span data-ttu-id="df922-109">`YieldTask` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="df922-109">`YieldTask` returned successfully.</span></span>|  
|<span data-ttu-id="df922-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="df922-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="df922-111">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="df922-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="df922-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="df922-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="df922-113">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="df922-113">The call timed out.</span></span>|  
|<span data-ttu-id="df922-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="df922-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="df922-115">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="df922-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="df922-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="df922-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="df922-117">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="df922-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="df922-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="df922-118">E_FAIL</span></span>|<span data-ttu-id="df922-119">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="df922-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="df922-120">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="df922-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="df922-121">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="df922-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="df922-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="df922-122">Remarks</span></span>  
 <span data-ttu-id="df922-123">Un host llama a `YieldTask` para solicitar recursos del procesador para otras tareas o procesos.</span><span class="sxs-lookup"><span data-stu-id="df922-123">A host calls `YieldTask` to request processor resources for other tasks or processes.</span></span> <span data-ttu-id="df922-124">Este método está pensado principalmente para permitir que el código de ejecución prolongada deje tiempo de CPU.</span><span class="sxs-lookup"><span data-stu-id="df922-124">This method is primarily intended to allow long-running code to give up CPU time.</span></span> <span data-ttu-id="df922-125">El motor en tiempo de ejecución intenta colocar la tarea que la instancia de `ICLRTask` actual representa en un estado en el que puede dar lugar a un tiempo de procesamiento, pero no garantiza el éxito.</span><span class="sxs-lookup"><span data-stu-id="df922-125">The runtime attempts to put the task that the current `ICLRTask` instance represents in a state where it can yield processing time, but makes no guarantee of success.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df922-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="df922-126">Requirements</span></span>  
 <span data-ttu-id="df922-127">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="df922-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df922-128">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="df922-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="df922-129">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="df922-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="df922-130">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df922-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df922-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="df922-131">See also</span></span>

- [<span data-ttu-id="df922-132">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="df922-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="df922-133">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="df922-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="df922-134">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="df922-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="df922-135">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="df922-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
