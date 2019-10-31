---
title: ICLRTask::ExitTask (Método)
ms.date: 03/30/2017
api_name:
- ICLRTask.ExitTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::ExitTask
helpviewer_keywords:
- ExitTask method [.NET Framework hosting]
- ICLRTask::ExitTask method [.NET Framework hosting]
ms.assetid: 746c85a6-4b33-4f72-a2e9-379fdf2e96af
topic_type:
- apiref
ms.openlocfilehash: 3f6ccf2eb25e96e0f94c558fb642b153ae3472c1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124906"
---
# <a name="iclrtaskexittask-method"></a><span data-ttu-id="985d7-102">ICLRTask::ExitTask (Método)</span><span class="sxs-lookup"><span data-stu-id="985d7-102">ICLRTask::ExitTask Method</span></span>
<span data-ttu-id="985d7-103">Notifica a la Common Language Runtime (CLR) que la tarea representada por la instancia de [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) actual está finalizando e intenta cerrar la tarea correctamente.</span><span class="sxs-lookup"><span data-stu-id="985d7-103">Notifies the common language runtime (CLR) that the task represented by the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance is ending, and attempts to shut the task down gracefully.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="985d7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="985d7-104">Syntax</span></span>  
  
```cpp  
HRESULT ExitTask ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="985d7-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="985d7-105">Return Value</span></span>  
  
|<span data-ttu-id="985d7-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="985d7-106">HRESULT</span></span>|<span data-ttu-id="985d7-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="985d7-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="985d7-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="985d7-108">S_OK</span></span>|<span data-ttu-id="985d7-109">`ExitTask` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="985d7-109">`ExitTask` returned successfully.</span></span>|  
|<span data-ttu-id="985d7-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="985d7-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="985d7-111">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="985d7-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="985d7-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="985d7-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="985d7-113">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="985d7-113">The call timed out.</span></span>|  
|<span data-ttu-id="985d7-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="985d7-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="985d7-115">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="985d7-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="985d7-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="985d7-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="985d7-117">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="985d7-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="985d7-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="985d7-118">E_FAIL</span></span>|<span data-ttu-id="985d7-119">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="985d7-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="985d7-120">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="985d7-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="985d7-121">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="985d7-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="985d7-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="985d7-122">Remarks</span></span>  
 <span data-ttu-id="985d7-123">`ExitTask` intenta cerrar una tarea de forma similar a desasociar un subproceso de una biblioteca de tipos no administrada.</span><span class="sxs-lookup"><span data-stu-id="985d7-123">`ExitTask` attempts a clean shutdown of a task, in a manner analogous to detaching a thread from an unmanaged type library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="985d7-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="985d7-124">Requirements</span></span>  
 <span data-ttu-id="985d7-125">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="985d7-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="985d7-126">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="985d7-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="985d7-127">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="985d7-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="985d7-128">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="985d7-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="985d7-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="985d7-129">See also</span></span>

- [<span data-ttu-id="985d7-130">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="985d7-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="985d7-131">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="985d7-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="985d7-132">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="985d7-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="985d7-133">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="985d7-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
