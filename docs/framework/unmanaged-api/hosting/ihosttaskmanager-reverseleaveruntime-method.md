---
title: IHostTaskManager::ReverseLeaveRuntime (Método)
ms.date: 03/30/2017
api_name:
- IHostTaskManager.ReverseLeaveRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::ReverseLeaveRuntime
helpviewer_keywords:
- IHostTaskManager::ReverseLeaveRuntime method [.NET Framework hosting]
- ReverseLeaveRuntime method [.NET Framework hosting]
ms.assetid: 4837d398-16a1-4e32-902c-022cd1aad3ca
topic_type:
- apiref
ms.openlocfilehash: 362239c584f469c9bd88f9f937bb3cdae7235429
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132952"
---
# <a name="ihosttaskmanagerreverseleaveruntime-method"></a><span data-ttu-id="ed3f5-102">IHostTaskManager::ReverseLeaveRuntime (Método)</span><span class="sxs-lookup"><span data-stu-id="ed3f5-102">IHostTaskManager::ReverseLeaveRuntime Method</span></span>
<span data-ttu-id="ed3f5-103">Notifica al host que el control está saliendo del Common Language Runtime (CLR) y entra en una función no administrada a la que se llama a su vez desde código administrado.</span><span class="sxs-lookup"><span data-stu-id="ed3f5-103">Notifies the host that control is leaving the common language runtime (CLR) and entering an unmanaged function that was, in turn, called from managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed3f5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ed3f5-104">Syntax</span></span>  
  
```cpp  
HRESULT ReverseLeaveRuntime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="ed3f5-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ed3f5-105">Return Value</span></span>  
  
|<span data-ttu-id="ed3f5-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ed3f5-106">HRESULT</span></span>|<span data-ttu-id="ed3f5-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="ed3f5-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ed3f5-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="ed3f5-108">S_OK</span></span>|<span data-ttu-id="ed3f5-109">`ReverseLeaveRuntime` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="ed3f5-109">`ReverseLeaveRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="ed3f5-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ed3f5-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ed3f5-111">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="ed3f5-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ed3f5-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ed3f5-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ed3f5-113">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="ed3f5-113">The call timed out.</span></span>|  
|<span data-ttu-id="ed3f5-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ed3f5-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ed3f5-115">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="ed3f5-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ed3f5-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ed3f5-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ed3f5-117">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="ed3f5-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ed3f5-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ed3f5-118">E_FAIL</span></span>|<span data-ttu-id="ed3f5-119">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="ed3f5-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ed3f5-120">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="ed3f5-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ed3f5-121">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ed3f5-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ed3f5-122">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="ed3f5-122">E_OUTOFMEMORY</span></span>|<span data-ttu-id="ed3f5-123">No hay suficiente memoria disponible para completar la asignación de recursos solicitada.</span><span class="sxs-lookup"><span data-stu-id="ed3f5-123">Not enough memory is available to complete the requested resource allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ed3f5-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ed3f5-124">Remarks</span></span>  
 <span data-ttu-id="ed3f5-125">CLR llama `ReverseLeaveRuntime` para informar al host de que la tarea que se está ejecutando actualmente devuelve el control a una función no administrada que, a su vez, se ha llamado desde código administrado a través de la invocación de plataforma.</span><span class="sxs-lookup"><span data-stu-id="ed3f5-125">The CLR calls `ReverseLeaveRuntime` to inform the host that the currently executing task is returning control to an unmanaged function that was, in turn, called from managed code through platform invoke.</span></span> <span data-ttu-id="ed3f5-126">Cada llamada a `ReverseLeaveRuntime` coincide con una llamada correspondiente a [ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md).</span><span class="sxs-lookup"><span data-stu-id="ed3f5-126">Each call to `ReverseLeaveRuntime` matches a corresponding call to [ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed3f5-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ed3f5-127">Requirements</span></span>  
 <span data-ttu-id="ed3f5-128">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ed3f5-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed3f5-129">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ed3f5-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ed3f5-130">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ed3f5-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ed3f5-131">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed3f5-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed3f5-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="ed3f5-132">See also</span></span>

- [<span data-ttu-id="ed3f5-133">CallNeedsHostHook (método)</span><span class="sxs-lookup"><span data-stu-id="ed3f5-133">CallNeedsHostHook Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-callneedshosthook-method.md)
- [<span data-ttu-id="ed3f5-134">EnterRuntime (método)</span><span class="sxs-lookup"><span data-stu-id="ed3f5-134">EnterRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md)
- [<span data-ttu-id="ed3f5-135">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ed3f5-135">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="ed3f5-136">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ed3f5-136">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="ed3f5-137">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ed3f5-137">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="ed3f5-138">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ed3f5-138">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="ed3f5-139">LeaveRuntime (método)</span><span class="sxs-lookup"><span data-stu-id="ed3f5-139">LeaveRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)
- <span data-ttu-id="ed3f5-140">[Aproximación a la invocación de plataforma](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0h9e9t7d(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="ed3f5-140">[A Closer Look at Platform Invoke](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0h9e9t7d(v=vs.100))</span></span>
