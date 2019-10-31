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
ms.openlocfilehash: b2fc1d6c45eb72410ccfa1071064aa1a31ae46e6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121406"
---
# <a name="ihosttaskalert-method"></a><span data-ttu-id="75d1d-102">IHostTask::Alert (Método)</span><span class="sxs-lookup"><span data-stu-id="75d1d-102">IHostTask::Alert Method</span></span>
<span data-ttu-id="75d1d-103">Solicita que el host reactive la tarea representada por la instancia actual de [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) , por lo que se puede anular la tarea.</span><span class="sxs-lookup"><span data-stu-id="75d1d-103">Requests that the host wake the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance, so the task can be aborted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75d1d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="75d1d-104">Syntax</span></span>  
  
```cpp  
HRESULT Alert ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="75d1d-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="75d1d-105">Return Value</span></span>  
  
|<span data-ttu-id="75d1d-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="75d1d-106">HRESULT</span></span>|<span data-ttu-id="75d1d-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="75d1d-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="75d1d-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="75d1d-108">S_OK</span></span>|<span data-ttu-id="75d1d-109">El método se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="75d1d-109">The method returned successfully.</span></span>|  
|<span data-ttu-id="75d1d-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="75d1d-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="75d1d-111">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="75d1d-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="75d1d-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="75d1d-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="75d1d-113">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="75d1d-113">The call timed out.</span></span>|  
|<span data-ttu-id="75d1d-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="75d1d-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="75d1d-115">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="75d1d-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="75d1d-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="75d1d-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="75d1d-117">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="75d1d-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="75d1d-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="75d1d-118">E_FAIL</span></span>|<span data-ttu-id="75d1d-119">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="75d1d-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="75d1d-120">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="75d1d-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="75d1d-121">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="75d1d-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="75d1d-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="75d1d-122">Remarks</span></span>  
 <span data-ttu-id="75d1d-123">CLR llama al método `Alert` cuando se llama a <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> desde el código de usuario o cuando se cierra el <xref:System.AppDomain> asociado al <xref:System.Threading.Thread> actual.</span><span class="sxs-lookup"><span data-stu-id="75d1d-123">The CLR calls the `Alert` method when <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> is called from user code, or when the <xref:System.AppDomain> associated with the current <xref:System.Threading.Thread> shuts down.</span></span> <span data-ttu-id="75d1d-124">El host debe volver inmediatamente, porque la llamada se realiza de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="75d1d-124">The host must return immediately, because the call is made asynchronously.</span></span> <span data-ttu-id="75d1d-125">Si el host no puede avisar inmediatamente de la tarea, se debe reactivar la próxima vez que entre en un estado en el que se pueda avisar.</span><span class="sxs-lookup"><span data-stu-id="75d1d-125">If the host cannot alert the task immediately, it must wake up the next time it enters a state in which it can be alerted.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="75d1d-126">`Alert` solo afecta a las tareas en las que el tiempo de ejecución ha pasado un valor [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) de WAIT_ALERTABLE a métodos como [join](../../../../docs/framework/unmanaged-api/hosting/ihosttask-join-method.md).</span><span class="sxs-lookup"><span data-stu-id="75d1d-126">`Alert` affects only those tasks to which the runtime has passed a [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) value of WAIT_ALERTABLE to methods such as [Join](../../../../docs/framework/unmanaged-api/hosting/ihosttask-join-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75d1d-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="75d1d-127">Requirements</span></span>  
 <span data-ttu-id="75d1d-128">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="75d1d-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75d1d-129">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="75d1d-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="75d1d-130">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="75d1d-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="75d1d-131">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75d1d-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75d1d-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="75d1d-132">See also</span></span>

- [<span data-ttu-id="75d1d-133">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="75d1d-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="75d1d-134">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="75d1d-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="75d1d-135">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="75d1d-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="75d1d-136">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="75d1d-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
