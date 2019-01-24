---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5b0a4450b6cfa98d0c939c148229d48d0b1d4c7c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54556579"
---
# <a name="iclrtaskswitchout-method"></a><span data-ttu-id="9dda7-102">ICLRTask::SwitchOut (Método)</span><span class="sxs-lookup"><span data-stu-id="9dda7-102">ICLRTask::SwitchOut Method</span></span>
<span data-ttu-id="9dda7-103">Notifica a common language runtime (CLR) que la tarea representada por el actual [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instancia ya no está en un estado operable.</span><span class="sxs-lookup"><span data-stu-id="9dda7-103">Notifies the common language runtime (CLR) that the task represented by the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance is no longer in an operable state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9dda7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9dda7-104">Syntax</span></span>  
  
```  
HRESULT SwitchOut ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="9dda7-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9dda7-105">Return Value</span></span>  
  
|<span data-ttu-id="9dda7-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9dda7-106">HRESULT</span></span>|<span data-ttu-id="9dda7-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="9dda7-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9dda7-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="9dda7-108">S_OK</span></span>|<span data-ttu-id="9dda7-109">`SwitchOut` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="9dda7-109">`SwitchOut` returned successfully.</span></span>|  
|<span data-ttu-id="9dda7-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9dda7-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9dda7-111">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="9dda7-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9dda7-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9dda7-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9dda7-113">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="9dda7-113">The call timed out.</span></span>|  
|<span data-ttu-id="9dda7-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9dda7-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9dda7-115">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="9dda7-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9dda7-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9dda7-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9dda7-117">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="9dda7-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9dda7-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9dda7-118">E_FAIL</span></span>|<span data-ttu-id="9dda7-119">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="9dda7-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9dda7-120">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="9dda7-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9dda7-121">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="9dda7-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9dda7-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9dda7-122">Remarks</span></span>  
 <span data-ttu-id="9dda7-123">Un host llama `SwitchOut` para informar a CLR que ha detenido temporalmente ejecutando la tarea que actual `ICLRTask` representa la instancia y volverá a programar la tarea.</span><span class="sxs-lookup"><span data-stu-id="9dda7-123">A host calls `SwitchOut` to inform the CLR that it has temporarily stopped executing the task that the current `ICLRTask` instance represents, and will reschedule the task.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9dda7-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9dda7-124">Requirements</span></span>  
 <span data-ttu-id="9dda7-125">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9dda7-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9dda7-126">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9dda7-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9dda7-127">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9dda7-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9dda7-128">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9dda7-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9dda7-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="9dda7-129">See also</span></span>
- [<span data-ttu-id="9dda7-130">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9dda7-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="9dda7-131">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9dda7-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="9dda7-132">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9dda7-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="9dda7-133">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9dda7-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
