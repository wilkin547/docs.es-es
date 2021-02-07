---
description: 'Más información acerca de: IHostTaskManager:: ReverseEnterRuntime (método)'
title: IHostTaskManager::ReverseEnterRuntime (Método)
ms.date: 03/30/2017
api_name:
- IHostTaskManager.ReverseEnterRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::ReverseEnterRuntime
helpviewer_keywords:
- IHostTaskManager::ReverseEnterRuntime method [.NET Framework hosting]
- ReverseEnterRuntime method [.NET Framework hosting]
ms.assetid: b1e26bff-d3ea-436e-9867-29720df999f4
topic_type:
- apiref
ms.openlocfilehash: 1c2d2d7d60bd110999591ed5e94c86d680560d12
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99707553"
---
# <a name="ihosttaskmanagerreverseenterruntime-method"></a><span data-ttu-id="a00bd-103">IHostTaskManager::ReverseEnterRuntime (Método)</span><span class="sxs-lookup"><span data-stu-id="a00bd-103">IHostTaskManager::ReverseEnterRuntime Method</span></span>

<span data-ttu-id="a00bd-104">Notifica al host que se está realizando una llamada en el Common Language Runtime (CLR) desde el código no administrado.</span><span class="sxs-lookup"><span data-stu-id="a00bd-104">Notifies the host that a call is being made into the common language runtime (CLR) from unmanaged code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a00bd-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a00bd-105">Syntax</span></span>  
  
```cpp  
HRESULT ReverseEnterRuntime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="a00bd-106">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a00bd-106">Return Value</span></span>  
  
|<span data-ttu-id="a00bd-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a00bd-107">HRESULT</span></span>|<span data-ttu-id="a00bd-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="a00bd-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a00bd-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="a00bd-109">S_OK</span></span>|<span data-ttu-id="a00bd-110">`ReverseEnterRuntime` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="a00bd-110">`ReverseEnterRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="a00bd-111">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a00bd-111">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a00bd-112">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="a00bd-112">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a00bd-113">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a00bd-113">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a00bd-114">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a00bd-114">The call timed out.</span></span>|  
|<span data-ttu-id="a00bd-115">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a00bd-115">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a00bd-116">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="a00bd-116">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a00bd-117">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a00bd-117">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a00bd-118">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="a00bd-118">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a00bd-119">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a00bd-119">E_FAIL</span></span>|<span data-ttu-id="a00bd-120">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="a00bd-120">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a00bd-121">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="a00bd-121">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a00bd-122">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a00bd-122">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a00bd-123">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="a00bd-123">E_OUTOFMEMORY</span></span>|<span data-ttu-id="a00bd-124">No hay suficiente memoria disponible para completar la asignación de recursos solicitada.</span><span class="sxs-lookup"><span data-stu-id="a00bd-124">Not enough memory is available to complete the requested resource allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a00bd-125">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a00bd-125">Remarks</span></span>  

 <span data-ttu-id="a00bd-126">Si la llamada a CLR se realiza a partir de una secuencia que se originó en código administrado, cada llamada a `ReverseEnterRuntime` corresponde a una llamada a [ReverseLeaveRuntime](ihosttaskmanager-reverseleaveruntime-method.md).</span><span class="sxs-lookup"><span data-stu-id="a00bd-126">If the call into the CLR is made from a sequence that originated in managed code, each call to `ReverseEnterRuntime` corresponds to a call to [ReverseLeaveRuntime](ihosttaskmanager-reverseleaveruntime-method.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a00bd-127">Las llamadas se pueden originar a partir de código no administrado sin anidarse.</span><span class="sxs-lookup"><span data-stu-id="a00bd-127">Calls can originate from unmanaged code without being nested.</span></span> <span data-ttu-id="a00bd-128">En este caso, no hay ninguna llamada a [EnterRuntime (](ihosttaskmanager-enterruntime-method.md), [LeaveRuntime (](ihosttaskmanager-leaveruntime-method.md)o `ReverseLeaveRuntime` , y el número de llamadas a no es `ReverseEnterRuntime` igual al número de llamadas a `ReverseLeaveRuntime` .</span><span class="sxs-lookup"><span data-stu-id="a00bd-128">In this case, there is no call to [EnterRuntime](ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](ihosttaskmanager-leaveruntime-method.md), or `ReverseLeaveRuntime`, and the number of calls to `ReverseEnterRuntime` does not equal the number of calls to `ReverseLeaveRuntime`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a00bd-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a00bd-129">Requirements</span></span>  

 <span data-ttu-id="a00bd-130">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a00bd-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a00bd-131">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="a00bd-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a00bd-132">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a00bd-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a00bd-133">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a00bd-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a00bd-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="a00bd-134">See also</span></span>

- [<span data-ttu-id="a00bd-135">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a00bd-135">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="a00bd-136">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a00bd-136">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="a00bd-137">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a00bd-137">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="a00bd-138">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a00bd-138">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
