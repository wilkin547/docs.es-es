---
description: 'Más información acerca de: IHostTaskManager:: CallNeedsHostHook ((método)'
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
ms.openlocfilehash: 777e1e6c4ac094a7af077c481415167f57eed14d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784592"
---
# <a name="ihosttaskmanagercallneedshosthook-method"></a><span data-ttu-id="cb0dd-103">IHostTaskManager::CallNeedsHostHook (Método)</span><span class="sxs-lookup"><span data-stu-id="cb0dd-103">IHostTaskManager::CallNeedsHostHook Method</span></span>

<span data-ttu-id="cb0dd-104">Permite al host especificar si el Common Language Runtime (CLR) puede alinear la llamada especificada a una función no administrada.</span><span class="sxs-lookup"><span data-stu-id="cb0dd-104">Enables the host to specify whether the common language runtime (CLR) can inline the specified call to an unmanaged function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb0dd-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cb0dd-105">Syntax</span></span>  
  
```cpp  
HRESULT CallNeedsHostHook (  
    [in]  SIZE_T target,
    [out] BOOL   *pbCallNeedsHostHook  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cb0dd-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cb0dd-106">Parameters</span></span>  

 `target`  
 <span data-ttu-id="cb0dd-107">de Dirección dentro del archivo portable ejecutable (PE) asignado de la función no administrada a la que se va a llamar.</span><span class="sxs-lookup"><span data-stu-id="cb0dd-107">[in] The address within the mapped portable executable (PE) file of the unmanaged function that is to be called.</span></span>  
  
 `pbCallNeedsHostHook`  
 <span data-ttu-id="cb0dd-108">enuncia Un puntero a un valor booleano que indica si el host requiere que se enlace la llamada.</span><span class="sxs-lookup"><span data-stu-id="cb0dd-108">[out] A pointer to a Boolean value that indicates whether the host requires the call to be hooked.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cb0dd-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="cb0dd-109">Return Value</span></span>  
  
|<span data-ttu-id="cb0dd-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cb0dd-110">HRESULT</span></span>|<span data-ttu-id="cb0dd-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="cb0dd-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cb0dd-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="cb0dd-112">S_OK</span></span>|<span data-ttu-id="cb0dd-113">`CallNeedsHostHook` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="cb0dd-113">`CallNeedsHostHook` returned successfully.</span></span>|  
|<span data-ttu-id="cb0dd-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="cb0dd-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="cb0dd-115">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="cb0dd-115">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="cb0dd-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="cb0dd-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="cb0dd-117">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="cb0dd-117">The call timed out.</span></span>|  
|<span data-ttu-id="cb0dd-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="cb0dd-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="cb0dd-119">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="cb0dd-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="cb0dd-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="cb0dd-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="cb0dd-121">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="cb0dd-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="cb0dd-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="cb0dd-122">E_FAIL</span></span>|<span data-ttu-id="cb0dd-123">Se ha producido un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="cb0dd-123">An unknown catastrophic failure has occurred.</span></span> <span data-ttu-id="cb0dd-124">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="cb0dd-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="cb0dd-125">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="cb0dd-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cb0dd-126">Observaciones</span><span class="sxs-lookup"><span data-stu-id="cb0dd-126">Remarks</span></span>  

 <span data-ttu-id="cb0dd-127">Para ayudar a optimizar la ejecución del código, CLR realiza un análisis de cada llamada de invocación de plataforma durante la compilación para determinar si la llamada se puede insertar.</span><span class="sxs-lookup"><span data-stu-id="cb0dd-127">To help optimize code execution, the CLR performs an analysis of each platform invoke call during compilation to determine whether the call can be inlined.</span></span> <span data-ttu-id="cb0dd-128">`CallNeedsHostHook` permite que el host invalide esa decisión solicitando que se enlace una llamada a una función no administrada.</span><span class="sxs-lookup"><span data-stu-id="cb0dd-128">`CallNeedsHostHook` enables the host to override that decision by requiring that a call to an unmanaged function be hooked.</span></span> <span data-ttu-id="cb0dd-129">Si el host requiere un enlace, el runtime no insertará la llamada.</span><span class="sxs-lookup"><span data-stu-id="cb0dd-129">If the host requires a hook, the runtime does not inline the call.</span></span>  
  
 <span data-ttu-id="cb0dd-130">Normalmente, el host requeriría un enlace donde debe ajustar un estado de punto flotante o al recibir la notificación de que una llamada está entrando en un estado en el que el host no puede realizar el seguimiento de las solicitudes de memoria en tiempo de ejecución o de los bloqueos tomados.</span><span class="sxs-lookup"><span data-stu-id="cb0dd-130">The host typically would require a hook where it must adjust a floating-point state, or upon receiving notification that a call is entering a state where the host cannot track the runtime's requests for memory or any locks taken.</span></span> <span data-ttu-id="cb0dd-131">Cuando el host requiere que se enlace la llamada, el tiempo de ejecución notifica al host de las transiciones hacia y desde el código administrado mediante llamadas a [EnterRuntime (](ihosttaskmanager-enterruntime-method.md), [LeaveRuntime (](ihosttaskmanager-leaveruntime-method.md), [ReverseEnterRuntime](ihosttaskmanager-reverseenterruntime-method.md)y [ReverseLeaveRuntime](ihosttaskmanager-reverseleaveruntime-method.md).</span><span class="sxs-lookup"><span data-stu-id="cb0dd-131">When the host requires that the call be hooked, the runtime notifies the host of transitions to and from managed code by using calls to [EnterRuntime](ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](ihosttaskmanager-leaveruntime-method.md), [ReverseEnterRuntime](ihosttaskmanager-reverseenterruntime-method.md), and [ReverseLeaveRuntime](ihosttaskmanager-reverseleaveruntime-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb0dd-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cb0dd-132">Requirements</span></span>  

 <span data-ttu-id="cb0dd-133">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cb0dd-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb0dd-134">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="cb0dd-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cb0dd-135">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cb0dd-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cb0dd-136">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb0dd-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb0dd-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="cb0dd-137">See also</span></span>

- [<span data-ttu-id="cb0dd-138">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="cb0dd-138">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="cb0dd-139">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="cb0dd-139">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="cb0dd-140">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="cb0dd-140">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="cb0dd-141">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="cb0dd-141">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
