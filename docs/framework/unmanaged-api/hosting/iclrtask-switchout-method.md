---
description: 'Más información sobre: ICLRTask:: SwitchOut (método)'
title: ICLRTask::SwitchOut (Método)
ms.date: 03/30/2017
api_name:
- ICLRTask.SwitchOut
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::SwitchOut
helpviewer_keywords:
- ICLRTask::SwitchOut method [.NET Framework hosting]
- SwitchOut method [.NET Framework hosting]
ms.assetid: b6fb168c-b24b-4ecf-a390-2b5ba3317ae6
topic_type:
- apiref
ms.openlocfilehash: 6c491c4d9005fb850c5adecd025730f1ea71f513
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784943"
---
# <a name="iclrtaskswitchout-method"></a><span data-ttu-id="219e2-103">ICLRTask::SwitchOut (Método)</span><span class="sxs-lookup"><span data-stu-id="219e2-103">ICLRTask::SwitchOut Method</span></span>

<span data-ttu-id="219e2-104">Notifica a la Common Language Runtime (CLR) que la tarea representada por la instancia de [ICLRTask](iclrtask-interface.md) actual ya no se encuentra en un estado operativo.</span><span class="sxs-lookup"><span data-stu-id="219e2-104">Notifies the common language runtime (CLR) that the task represented by the current [ICLRTask](iclrtask-interface.md) instance is no longer in an operable state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="219e2-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="219e2-105">Syntax</span></span>  
  
```cpp  
HRESULT SwitchOut ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="219e2-106">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="219e2-106">Return Value</span></span>  
  
|<span data-ttu-id="219e2-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="219e2-107">HRESULT</span></span>|<span data-ttu-id="219e2-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="219e2-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="219e2-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="219e2-109">S_OK</span></span>|<span data-ttu-id="219e2-110">`SwitchOut` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="219e2-110">`SwitchOut` returned successfully.</span></span>|  
|<span data-ttu-id="219e2-111">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="219e2-111">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="219e2-112">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="219e2-112">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="219e2-113">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="219e2-113">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="219e2-114">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="219e2-114">The call timed out.</span></span>|  
|<span data-ttu-id="219e2-115">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="219e2-115">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="219e2-116">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="219e2-116">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="219e2-117">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="219e2-117">HOST_E_ABANDONED</span></span>|<span data-ttu-id="219e2-118">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="219e2-118">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="219e2-119">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="219e2-119">E_FAIL</span></span>|<span data-ttu-id="219e2-120">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="219e2-120">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="219e2-121">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="219e2-121">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="219e2-122">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="219e2-122">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="219e2-123">Observaciones</span><span class="sxs-lookup"><span data-stu-id="219e2-123">Remarks</span></span>  

 <span data-ttu-id="219e2-124">Un host llama `SwitchOut` a para informar a CLR de que ha detenido temporalmente la ejecución de la tarea que `ICLRTask` representa la instancia actual y volverá a programar la tarea.</span><span class="sxs-lookup"><span data-stu-id="219e2-124">A host calls `SwitchOut` to inform the CLR that it has temporarily stopped executing the task that the current `ICLRTask` instance represents, and will reschedule the task.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="219e2-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="219e2-125">Requirements</span></span>  

 <span data-ttu-id="219e2-126">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="219e2-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="219e2-127">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="219e2-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="219e2-128">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="219e2-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="219e2-129">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="219e2-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="219e2-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="219e2-130">See also</span></span>

- [<span data-ttu-id="219e2-131">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="219e2-131">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="219e2-132">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="219e2-132">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="219e2-133">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="219e2-133">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="219e2-134">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="219e2-134">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
