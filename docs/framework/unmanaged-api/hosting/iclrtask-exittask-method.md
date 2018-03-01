---
title: "ICLRTask::ExitTask (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ff2adafa41ce68a824f6b01888c3565bf054c031
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="iclrtaskexittask-method"></a><span data-ttu-id="db589-102">ICLRTask::ExitTask (Método)</span><span class="sxs-lookup"><span data-stu-id="db589-102">ICLRTask::ExitTask Method</span></span>
<span data-ttu-id="db589-103">Notifica a common language runtime (CLR) que la tarea representa el actual [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instancia está finalizando e intenta cerrar la tarea correctamente.</span><span class="sxs-lookup"><span data-stu-id="db589-103">Notifies the common language runtime (CLR) that the task represented by the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance is ending, and attempts to shut the task down gracefully.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db589-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="db589-104">Syntax</span></span>  
  
```  
HRESULT ExitTask ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="db589-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="db589-105">Return Value</span></span>  
  
|<span data-ttu-id="db589-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="db589-106">HRESULT</span></span>|<span data-ttu-id="db589-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="db589-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="db589-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="db589-108">S_OK</span></span>|<span data-ttu-id="db589-109">`ExitTask`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="db589-109">`ExitTask` returned successfully.</span></span>|  
|<span data-ttu-id="db589-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="db589-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="db589-111">El CLR no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="db589-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="db589-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="db589-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="db589-113">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="db589-113">The call timed out.</span></span>|  
|<span data-ttu-id="db589-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="db589-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="db589-115">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="db589-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="db589-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="db589-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="db589-117">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="db589-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="db589-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="db589-118">E_FAIL</span></span>|<span data-ttu-id="db589-119">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="db589-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="db589-120">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="db589-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="db589-121">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="db589-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="db589-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="db589-122">Remarks</span></span>  
 <span data-ttu-id="db589-123">`ExitTask`Intente un cierre correcto de una tarea, de forma análoga a desasociar un subproceso de una biblioteca de tipos no administrados.</span><span class="sxs-lookup"><span data-stu-id="db589-123">`ExitTask` attempts a clean shutdown of a task, in a manner analogous to detaching a thread from an unmanaged type library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db589-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="db589-124">Requirements</span></span>  
 <span data-ttu-id="db589-125">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db589-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db589-126">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="db589-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="db589-127">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="db589-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="db589-128">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db589-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db589-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="db589-129">See Also</span></span>  
 [<span data-ttu-id="db589-130">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="db589-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="db589-131">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="db589-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="db589-132">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="db589-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="db589-133">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="db589-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
