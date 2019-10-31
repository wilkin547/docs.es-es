---
title: IHostTaskManager::EndDelayAbort (Método)
ms.date: 03/30/2017
api_name:
- IHostTaskManager.EndDelayAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::EndDelayAbort
helpviewer_keywords:
- EndDelayAbort method [.NET Framework hosting]
- IHostTaskManager::EndDelayAbort method [.NET Framework hosting]
ms.assetid: 6e02facb-2504-4356-9af5-0cee1f8436a7
topic_type:
- apiref
ms.openlocfilehash: cf79c0d0f6def46d7f4d55f17afbd1f1dff00ad9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133072"
---
# <a name="ihosttaskmanagerenddelayabort-method"></a><span data-ttu-id="acf22-102">IHostTaskManager::EndDelayAbort (Método)</span><span class="sxs-lookup"><span data-stu-id="acf22-102">IHostTaskManager::EndDelayAbort Method</span></span>
<span data-ttu-id="acf22-103">Notifica al host que el código administrado está saliendo del período en el que la tarea actual no se debe anular, siguiendo una llamada anterior a [IHostTaskManager:: BeginDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-begindelayabort-method.md).</span><span class="sxs-lookup"><span data-stu-id="acf22-103">Notifies the host that managed code is exiting the period in which the current task must not be aborted, following an earlier call to [IHostTaskManager::BeginDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-begindelayabort-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acf22-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="acf22-104">Syntax</span></span>  
  
```cpp  
HRESULT EndDelayAbort ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="acf22-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="acf22-105">Return Value</span></span>  
  
|<span data-ttu-id="acf22-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="acf22-106">HRESULT</span></span>|<span data-ttu-id="acf22-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="acf22-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="acf22-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="acf22-108">S_OK</span></span>|<span data-ttu-id="acf22-109">`EndDelayAbort` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="acf22-109">`EndDelayAbort` returned successfully.</span></span>|  
|<span data-ttu-id="acf22-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="acf22-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="acf22-111">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="acf22-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="acf22-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="acf22-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="acf22-113">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="acf22-113">The call timed out.</span></span>|  
|<span data-ttu-id="acf22-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="acf22-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="acf22-115">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="acf22-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="acf22-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="acf22-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="acf22-117">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="acf22-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="acf22-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="acf22-118">E_FAIL</span></span>|<span data-ttu-id="acf22-119">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="acf22-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="acf22-120">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="acf22-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="acf22-121">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="acf22-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="acf22-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="acf22-122">E_UNEXPECTED</span></span>|<span data-ttu-id="acf22-123">se llamó a `EndDelayAbort` sin una llamada correspondiente a `BeginDelayAbort`.</span><span class="sxs-lookup"><span data-stu-id="acf22-123">`EndDelayAbort` was called without a corresponding call to `BeginDelayAbort`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="acf22-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="acf22-124">Remarks</span></span>  
 <span data-ttu-id="acf22-125">CLR realiza una llamada correspondiente a `BeginDelayAbort` en la tarea actual antes de llamar a `EndDelayAbort`.</span><span class="sxs-lookup"><span data-stu-id="acf22-125">The CLR makes a corresponding call to `BeginDelayAbort` on the current task before calling `EndDelayAbort`.</span></span> <span data-ttu-id="acf22-126">En ausencia de esta llamada correspondiente, la implementación del host de [IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md) debe devolver E_UNEXPECTED desde `EndDelayAbort`y no debe realizar ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="acf22-126">In the absence of such a corresponding call, the host's implementation of [IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md) should return E_UNEXPECTED from `EndDelayAbort`, and should take no action.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="acf22-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="acf22-127">Requirements</span></span>  
 <span data-ttu-id="acf22-128">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="acf22-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="acf22-129">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="acf22-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="acf22-130">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="acf22-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="acf22-131">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="acf22-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acf22-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="acf22-132">See also</span></span>

- <xref:System.Threading>
- [<span data-ttu-id="acf22-133">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="acf22-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="acf22-134">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="acf22-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="acf22-135">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="acf22-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="acf22-136">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="acf22-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
