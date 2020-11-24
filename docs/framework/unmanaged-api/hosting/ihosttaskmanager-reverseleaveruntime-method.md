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
ms.openlocfilehash: 8e0981415c03120cc30e6349daced51e79216938
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95669970"
---
# <a name="ihosttaskmanagerreverseleaveruntime-method"></a><span data-ttu-id="3ea0c-102">IHostTaskManager::ReverseLeaveRuntime (Método)</span><span class="sxs-lookup"><span data-stu-id="3ea0c-102">IHostTaskManager::ReverseLeaveRuntime Method</span></span>

<span data-ttu-id="3ea0c-103">Notifica al host que el control está saliendo del Common Language Runtime (CLR) y entra en una función no administrada a la que se llama a su vez desde código administrado.</span><span class="sxs-lookup"><span data-stu-id="3ea0c-103">Notifies the host that control is leaving the common language runtime (CLR) and entering an unmanaged function that was, in turn, called from managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ea0c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3ea0c-104">Syntax</span></span>  
  
```cpp  
HRESULT ReverseLeaveRuntime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="3ea0c-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3ea0c-105">Return Value</span></span>  
  
|<span data-ttu-id="3ea0c-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3ea0c-106">HRESULT</span></span>|<span data-ttu-id="3ea0c-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="3ea0c-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3ea0c-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="3ea0c-108">S_OK</span></span>|<span data-ttu-id="3ea0c-109">`ReverseLeaveRuntime` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="3ea0c-109">`ReverseLeaveRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="3ea0c-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3ea0c-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3ea0c-111">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="3ea0c-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3ea0c-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3ea0c-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3ea0c-113">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="3ea0c-113">The call timed out.</span></span>|  
|<span data-ttu-id="3ea0c-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3ea0c-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3ea0c-115">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="3ea0c-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3ea0c-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3ea0c-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3ea0c-117">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="3ea0c-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3ea0c-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3ea0c-118">E_FAIL</span></span>|<span data-ttu-id="3ea0c-119">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="3ea0c-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3ea0c-120">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="3ea0c-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3ea0c-121">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="3ea0c-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="3ea0c-122">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="3ea0c-122">E_OUTOFMEMORY</span></span>|<span data-ttu-id="3ea0c-123">No hay suficiente memoria disponible para completar la asignación de recursos solicitada.</span><span class="sxs-lookup"><span data-stu-id="3ea0c-123">Not enough memory is available to complete the requested resource allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3ea0c-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3ea0c-124">Remarks</span></span>  

 <span data-ttu-id="3ea0c-125">CLR llama `ReverseLeaveRuntime` a para informar al host de que la tarea que se está ejecutando actualmente devuelve el control a una función no administrada que, a su vez, se ha llamado desde código administrado a través de la invocación de plataforma.</span><span class="sxs-lookup"><span data-stu-id="3ea0c-125">The CLR calls `ReverseLeaveRuntime` to inform the host that the currently executing task is returning control to an unmanaged function that was, in turn, called from managed code through platform invoke.</span></span> <span data-ttu-id="3ea0c-126">Cada llamada a `ReverseLeaveRuntime` coincide con una llamada correspondiente a [ReverseEnterRuntime](ihosttaskmanager-reverseenterruntime-method.md).</span><span class="sxs-lookup"><span data-stu-id="3ea0c-126">Each call to `ReverseLeaveRuntime` matches a corresponding call to [ReverseEnterRuntime](ihosttaskmanager-reverseenterruntime-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ea0c-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3ea0c-127">Requirements</span></span>  

 <span data-ttu-id="3ea0c-128">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3ea0c-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ea0c-129">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="3ea0c-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3ea0c-130">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3ea0c-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3ea0c-131">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ea0c-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ea0c-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3ea0c-132">See also</span></span>

- [<span data-ttu-id="3ea0c-133">Método CallNeedsHostHook</span><span class="sxs-lookup"><span data-stu-id="3ea0c-133">CallNeedsHostHook Method</span></span>](ihosttaskmanager-callneedshosthook-method.md)
- [<span data-ttu-id="3ea0c-134">Método EnterRuntime</span><span class="sxs-lookup"><span data-stu-id="3ea0c-134">EnterRuntime Method</span></span>](ihosttaskmanager-enterruntime-method.md)
- [<span data-ttu-id="3ea0c-135">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3ea0c-135">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="3ea0c-136">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3ea0c-136">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="3ea0c-137">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3ea0c-137">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="3ea0c-138">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3ea0c-138">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="3ea0c-139">Método LeaveRuntime</span><span class="sxs-lookup"><span data-stu-id="3ea0c-139">LeaveRuntime Method</span></span>](ihosttaskmanager-leaveruntime-method.md)
- <span data-ttu-id="3ea0c-140">[Aproximación a la invocación de plataforma](/previous-versions/dotnet/netframework-4.0/0h9e9t7d(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="3ea0c-140">[A Closer Look at Platform Invoke](/previous-versions/dotnet/netframework-4.0/0h9e9t7d(v=vs.100))</span></span>
