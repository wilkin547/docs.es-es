---
title: IHostTaskManager::CallNeedsHostHook (Método)
ms.date: 03/30/2017
api_name:
- IHostTaskManager.CallNeedsHostHook
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::CallNeedsHostHook
helpviewer_keywords:
- CallNeedsHostHook method [.NET Framework hosting]
- IHostTaskManager::CallNeedsHostHook method [.NET Framework hosting]
ms.assetid: b60f1f59-9825-4b57-961f-d2979518e6a7
topic_type:
- apiref
ms.openlocfilehash: 8b8b8521a09fa54a105e8263a471ab0467fb6ccc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176297"
---
# <a name="ihosttaskmanagercallneedshosthook-method"></a><span data-ttu-id="86529-102">IHostTaskManager::CallNeedsHostHook (Método)</span><span class="sxs-lookup"><span data-stu-id="86529-102">IHostTaskManager::CallNeedsHostHook Method</span></span>
<span data-ttu-id="86529-103">Permite al host especificar si Common Language Runtime (CLR) puede inlinear la llamada especificada a una función no administrada.</span><span class="sxs-lookup"><span data-stu-id="86529-103">Enables the host to specify whether the common language runtime (CLR) can inline the specified call to an unmanaged function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86529-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="86529-104">Syntax</span></span>  
  
```cpp  
HRESULT CallNeedsHostHook (  
    [in]  SIZE_T target,
    [out] BOOL   *pbCallNeedsHostHook  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="86529-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="86529-105">Parameters</span></span>  
 `target`  
 <span data-ttu-id="86529-106">[en] La dirección dentro del archivo ejecutable portátil (PE) asignado de la función no administrada que se va a llamar.</span><span class="sxs-lookup"><span data-stu-id="86529-106">[in] The address within the mapped portable executable (PE) file of the unmanaged function that is to be called.</span></span>  
  
 `pbCallNeedsHostHook`  
 <span data-ttu-id="86529-107">[fuera] Puntero a un valor booleano que indica si el host requiere que se enganche la llamada.</span><span class="sxs-lookup"><span data-stu-id="86529-107">[out] A pointer to a Boolean value that indicates whether the host requires the call to be hooked.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="86529-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="86529-108">Return Value</span></span>  
  
|<span data-ttu-id="86529-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="86529-109">HRESULT</span></span>|<span data-ttu-id="86529-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="86529-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="86529-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="86529-111">S_OK</span></span>|<span data-ttu-id="86529-112">`CallNeedsHostHook`regresó con éxito.</span><span class="sxs-lookup"><span data-stu-id="86529-112">`CallNeedsHostHook` returned successfully.</span></span>|  
|<span data-ttu-id="86529-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="86529-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="86529-114">El CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="86529-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="86529-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="86529-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="86529-116">Se adelantó la llamada.</span><span class="sxs-lookup"><span data-stu-id="86529-116">The call timed out.</span></span>|  
|<span data-ttu-id="86529-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="86529-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="86529-118">El autor de la llamada no es el propietario de la cerradura.</span><span class="sxs-lookup"><span data-stu-id="86529-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="86529-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="86529-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="86529-120">Un evento se canceló mientras un hilo bloqueado o fibra lo esperaba.</span><span class="sxs-lookup"><span data-stu-id="86529-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="86529-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="86529-121">E_FAIL</span></span>|<span data-ttu-id="86529-122">Se ha producido un fallo catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="86529-122">An unknown catastrophic failure has occurred.</span></span> <span data-ttu-id="86529-123">Cuando un método devuelve E_FAIL, CLR ya no se puede usar dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="86529-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="86529-124">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="86529-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="86529-125">Observaciones</span><span class="sxs-lookup"><span data-stu-id="86529-125">Remarks</span></span>  
 <span data-ttu-id="86529-126">Para ayudar a optimizar la ejecución de código, CLR realiza un análisis de cada llamada de invocación de plataforma durante la compilación para determinar si la llamada se puede insertar.</span><span class="sxs-lookup"><span data-stu-id="86529-126">To help optimize code execution, the CLR performs an analysis of each platform invoke call during compilation to determine whether the call can be inlined.</span></span> <span data-ttu-id="86529-127">`CallNeedsHostHook`permite al host invalidar esa decisión exigiendo que se enganche una llamada a una función no administrada.</span><span class="sxs-lookup"><span data-stu-id="86529-127">`CallNeedsHostHook` enables the host to override that decision by requiring that a call to an unmanaged function be hooked.</span></span> <span data-ttu-id="86529-128">Si el host requiere un enlace, el tiempo de ejecución no inline la llamada.</span><span class="sxs-lookup"><span data-stu-id="86529-128">If the host requires a hook, the runtime does not inline the call.</span></span>  
  
 <span data-ttu-id="86529-129">Normalmente, el host requeriría un enlace donde debe ajustar un estado de punto flotante, o al recibir una notificación de que una llamada está entrando en un estado donde el host no puede realizar un seguimiento de las solicitudes de memoria del tiempo de ejecución o de los bloqueos tomados.</span><span class="sxs-lookup"><span data-stu-id="86529-129">The host typically would require a hook where it must adjust a floating-point state, or upon receiving notification that a call is entering a state where the host cannot track the runtime's requests for memory or any locks taken.</span></span> <span data-ttu-id="86529-130">Cuando el host requiere que se enlace la llamada, el tiempo de ejecución notifica al host de transiciones hacia y desde código administrado mediante llamadas a [EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md), [ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md)y [ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md).</span><span class="sxs-lookup"><span data-stu-id="86529-130">When the host requires that the call be hooked, the runtime notifies the host of transitions to and from managed code by using calls to [EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md), [ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), and [ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86529-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="86529-131">Requirements</span></span>  
 <span data-ttu-id="86529-132">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="86529-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86529-133">**Encabezado:** MScorEE.h</span><span class="sxs-lookup"><span data-stu-id="86529-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="86529-134">**Biblioteca:** Incluido como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="86529-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="86529-135">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86529-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86529-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="86529-136">See also</span></span>

- [<span data-ttu-id="86529-137">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="86529-137">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="86529-138">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="86529-138">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="86529-139">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="86529-139">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="86529-140">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="86529-140">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
