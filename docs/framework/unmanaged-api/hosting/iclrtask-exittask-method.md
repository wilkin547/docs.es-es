---
description: 'Más información acerca de: ICLRTask:: ExitTask (método)'
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
ms.openlocfilehash: 267b7f284ccac5b535a72dab425c035b6c689361
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784970"
---
# <a name="iclrtaskexittask-method"></a><span data-ttu-id="27a06-103">ICLRTask::ExitTask (Método)</span><span class="sxs-lookup"><span data-stu-id="27a06-103">ICLRTask::ExitTask Method</span></span>

<span data-ttu-id="27a06-104">Notifica a la Common Language Runtime (CLR) que la tarea representada por la instancia de [ICLRTask](iclrtask-interface.md) actual está finalizando e intenta cerrar la tarea correctamente.</span><span class="sxs-lookup"><span data-stu-id="27a06-104">Notifies the common language runtime (CLR) that the task represented by the current [ICLRTask](iclrtask-interface.md) instance is ending, and attempts to shut the task down gracefully.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27a06-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="27a06-105">Syntax</span></span>  
  
```cpp  
HRESULT ExitTask ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="27a06-106">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="27a06-106">Return Value</span></span>  
  
|<span data-ttu-id="27a06-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="27a06-107">HRESULT</span></span>|<span data-ttu-id="27a06-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="27a06-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="27a06-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="27a06-109">S_OK</span></span>|<span data-ttu-id="27a06-110">`ExitTask` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="27a06-110">`ExitTask` returned successfully.</span></span>|  
|<span data-ttu-id="27a06-111">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="27a06-111">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="27a06-112">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="27a06-112">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="27a06-113">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="27a06-113">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="27a06-114">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="27a06-114">The call timed out.</span></span>|  
|<span data-ttu-id="27a06-115">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="27a06-115">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="27a06-116">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="27a06-116">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="27a06-117">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="27a06-117">HOST_E_ABANDONED</span></span>|<span data-ttu-id="27a06-118">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="27a06-118">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="27a06-119">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="27a06-119">E_FAIL</span></span>|<span data-ttu-id="27a06-120">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="27a06-120">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="27a06-121">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="27a06-121">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="27a06-122">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="27a06-122">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="27a06-123">Observaciones</span><span class="sxs-lookup"><span data-stu-id="27a06-123">Remarks</span></span>  

 <span data-ttu-id="27a06-124">`ExitTask` intenta cerrar una tarea de forma similar a desasociar un subproceso de una biblioteca de tipos no administrada.</span><span class="sxs-lookup"><span data-stu-id="27a06-124">`ExitTask` attempts a clean shutdown of a task, in a manner analogous to detaching a thread from an unmanaged type library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27a06-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="27a06-125">Requirements</span></span>  

 <span data-ttu-id="27a06-126">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="27a06-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27a06-127">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="27a06-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="27a06-128">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="27a06-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="27a06-129">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27a06-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27a06-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="27a06-130">See also</span></span>

- [<span data-ttu-id="27a06-131">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="27a06-131">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="27a06-132">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="27a06-132">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="27a06-133">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="27a06-133">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="27a06-134">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="27a06-134">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
