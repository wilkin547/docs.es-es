---
description: 'Más información acerca de: IHostTaskManager:: EndThreadAffinity (método)'
title: IHostTaskManager::EndThreadAffinity (Método)
ms.date: 03/30/2017
api_name:
- IHostTaskManager.EndThreadAffinity
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::EndThreadAffinity
helpviewer_keywords:
- EndThreadAffinity method [.NET Framework hosting]
- IHostTaskManager::EndThreadAffinity method [.NET Framework hosting]
ms.assetid: 7738a904-0cd7-4fde-a3eb-2323a5533157
topic_type:
- apiref
ms.openlocfilehash: 0bbe42d8e14d20fb5be18fe7ebb266100ae72fd7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789429"
---
# <a name="ihosttaskmanagerendthreadaffinity-method"></a><span data-ttu-id="e96a4-103">IHostTaskManager::EndThreadAffinity (Método)</span><span class="sxs-lookup"><span data-stu-id="e96a4-103">IHostTaskManager::EndThreadAffinity Method</span></span>

<span data-ttu-id="e96a4-104">Notifica al host que el código administrado está saliendo del período en el que la tarea actual no se debe pasar a otro subproceso del sistema operativo, siguiendo una llamada anterior a [IHostTaskManager:: BeginThreadAffinity](ihosttaskmanager-beginthreadaffinity-method.md).</span><span class="sxs-lookup"><span data-stu-id="e96a4-104">Notifies the host that managed code is exiting the period in which the current task must not be moved to another operating system thread, following an earlier call to [IHostTaskManager::BeginThreadAffinity](ihosttaskmanager-beginthreadaffinity-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e96a4-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e96a4-105">Syntax</span></span>  
  
```cpp  
HRESULT EndThreadAffinity ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="e96a4-106">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e96a4-106">Return Value</span></span>  
  
|<span data-ttu-id="e96a4-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e96a4-107">HRESULT</span></span>|<span data-ttu-id="e96a4-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="e96a4-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e96a4-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="e96a4-109">S_OK</span></span>|<span data-ttu-id="e96a4-110">`EndThreadAffinity` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="e96a4-110">`EndThreadAffinity` returned successfully.</span></span>|  
|<span data-ttu-id="e96a4-111">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e96a4-111">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e96a4-112">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="e96a4-112">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e96a4-113">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e96a4-113">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e96a4-114">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="e96a4-114">The call timed out.</span></span>|  
|<span data-ttu-id="e96a4-115">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e96a4-115">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e96a4-116">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="e96a4-116">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e96a4-117">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e96a4-117">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e96a4-118">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="e96a4-118">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e96a4-119">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e96a4-119">E_FAIL</span></span>|<span data-ttu-id="e96a4-120">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="e96a4-120">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e96a4-121">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="e96a4-121">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e96a4-122">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e96a4-122">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="e96a4-123">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="e96a4-123">E_UNEXPECTED</span></span>|<span data-ttu-id="e96a4-124">`EndThreadAffinity` se llamó a sin una llamada anterior correspondiente a `BeginThreadAffinity` .</span><span class="sxs-lookup"><span data-stu-id="e96a4-124">`EndThreadAffinity` was called without an earlier corresponding call to `BeginThreadAffinity`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e96a4-125">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e96a4-125">Remarks</span></span>  

 <span data-ttu-id="e96a4-126">CLR realiza una llamada correspondiente a `BeginThreadAffinity` en la tarea actual antes de llamar a `EndThreadAffinity` .</span><span class="sxs-lookup"><span data-stu-id="e96a4-126">The CLR makes a corresponding call to `BeginThreadAffinity` on the current task before calling `EndThreadAffinity`.</span></span> <span data-ttu-id="e96a4-127">En ausencia de esta llamada correspondiente, la implementación del host de [IHostTaskManager](ihosttaskmanager-interface.md) debe devolver E_UNEXPECTED y no realizar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="e96a4-127">In the absence of such a corresponding call, the host's implementation of [IHostTaskManager](ihosttaskmanager-interface.md) should return E_UNEXPECTED, and take no action.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e96a4-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e96a4-128">Requirements</span></span>  

 <span data-ttu-id="e96a4-129">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e96a4-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e96a4-130">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e96a4-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e96a4-131">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e96a4-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e96a4-132">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e96a4-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e96a4-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="e96a4-133">See also</span></span>

- <xref:System.Threading>
- [<span data-ttu-id="e96a4-134">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e96a4-134">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="e96a4-135">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e96a4-135">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="e96a4-136">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e96a4-136">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="e96a4-137">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e96a4-137">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
