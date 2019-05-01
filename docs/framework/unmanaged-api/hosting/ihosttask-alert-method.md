---
title: IHostTask::Alert (Método)
ms.date: 03/30/2017
api_name:
- IHostTask.Alert
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::Alert
helpviewer_keywords:
- IHostTask::Alert method [.NET Framework hosting]
- Alert method, IHostTask interface [.NET Framework hosting]
ms.assetid: 5245d4b5-b6c3-48df-9cb9-8caf059f43fb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c153e6ae8558eeab2efa99765405fb7c84632b01
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61992854"
---
# <a name="ihosttaskalert-method"></a><span data-ttu-id="ba4f1-102">IHostTask::Alert (Método)</span><span class="sxs-lookup"><span data-stu-id="ba4f1-102">IHostTask::Alert Method</span></span>
<span data-ttu-id="ba4f1-103">Las solicitudes que el host reactive la tarea representada por el actual [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) de instancia, por lo que se puede anular la tarea.</span><span class="sxs-lookup"><span data-stu-id="ba4f1-103">Requests that the host wake the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance, so the task can be aborted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba4f1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ba4f1-104">Syntax</span></span>  
  
```  
HRESULT Alert ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="ba4f1-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ba4f1-105">Return Value</span></span>  
  
|<span data-ttu-id="ba4f1-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ba4f1-106">HRESULT</span></span>|<span data-ttu-id="ba4f1-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="ba4f1-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ba4f1-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="ba4f1-108">S_OK</span></span>|<span data-ttu-id="ba4f1-109">El método se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="ba4f1-109">The method returned successfully.</span></span>|  
|<span data-ttu-id="ba4f1-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ba4f1-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ba4f1-111">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="ba4f1-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ba4f1-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ba4f1-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ba4f1-113">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="ba4f1-113">The call timed out.</span></span>|  
|<span data-ttu-id="ba4f1-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ba4f1-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ba4f1-115">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="ba4f1-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ba4f1-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ba4f1-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ba4f1-117">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="ba4f1-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ba4f1-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ba4f1-118">E_FAIL</span></span>|<span data-ttu-id="ba4f1-119">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="ba4f1-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ba4f1-120">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="ba4f1-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ba4f1-121">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ba4f1-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ba4f1-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ba4f1-122">Remarks</span></span>  
 <span data-ttu-id="ba4f1-123">CLR llama a la `Alert` método cuando <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> se llama desde el código de usuario, o cuando el <xref:System.AppDomain> asociado con el actual <xref:System.Threading.Thread> se cierra.</span><span class="sxs-lookup"><span data-stu-id="ba4f1-123">The CLR calls the `Alert` method when <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> is called from user code, or when the <xref:System.AppDomain> associated with the current <xref:System.Threading.Thread> shuts down.</span></span> <span data-ttu-id="ba4f1-124">El host debe devolver inmediatamente, porque la llamada se realiza de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="ba4f1-124">The host must return immediately, because the call is made asynchronously.</span></span> <span data-ttu-id="ba4f1-125">Si el host no puede generar una alerta la tarea inmediatamente, debe activar la próxima vez que entra en un estado en el que puede recibir alertas.</span><span class="sxs-lookup"><span data-stu-id="ba4f1-125">If the host cannot alert the task immediately, it must wake up the next time it enters a state in which it can be alerted.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ba4f1-126">`Alert` afecta a aquellas tareas a la que ha transcurrido el tiempo de ejecución un [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) valor de WAIT_ALERTABLE para métodos, como [unir](../../../../docs/framework/unmanaged-api/hosting/ihosttask-join-method.md).</span><span class="sxs-lookup"><span data-stu-id="ba4f1-126">`Alert` affects only those tasks to which the runtime has passed a [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) value of WAIT_ALERTABLE to methods such as [Join](../../../../docs/framework/unmanaged-api/hosting/ihosttask-join-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba4f1-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ba4f1-127">Requirements</span></span>  
 <span data-ttu-id="ba4f1-128">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ba4f1-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba4f1-129">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ba4f1-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ba4f1-130">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ba4f1-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ba4f1-131">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba4f1-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba4f1-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="ba4f1-132">See also</span></span>

- [<span data-ttu-id="ba4f1-133">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ba4f1-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="ba4f1-134">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ba4f1-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="ba4f1-135">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ba4f1-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="ba4f1-136">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ba4f1-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
