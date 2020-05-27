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
ms.openlocfilehash: 5bc5752d4d2b772b1d18f438c4daaa1b8938da9e
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842353"
---
# <a name="ihosttaskmanagercallneedshosthook-method"></a><span data-ttu-id="c513f-102">IHostTaskManager::CallNeedsHostHook (Método)</span><span class="sxs-lookup"><span data-stu-id="c513f-102">IHostTaskManager::CallNeedsHostHook Method</span></span>
<span data-ttu-id="c513f-103">Permite al host especificar si el Common Language Runtime (CLR) puede alinear la llamada especificada a una función no administrada.</span><span class="sxs-lookup"><span data-stu-id="c513f-103">Enables the host to specify whether the common language runtime (CLR) can inline the specified call to an unmanaged function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c513f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c513f-104">Syntax</span></span>  
  
```cpp  
HRESULT CallNeedsHostHook (  
    [in]  SIZE_T target,
    [out] BOOL   *pbCallNeedsHostHook  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c513f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c513f-105">Parameters</span></span>  
 `target`  
 <span data-ttu-id="c513f-106">de Dirección dentro del archivo portable ejecutable (PE) asignado de la función no administrada a la que se va a llamar.</span><span class="sxs-lookup"><span data-stu-id="c513f-106">[in] The address within the mapped portable executable (PE) file of the unmanaged function that is to be called.</span></span>  
  
 `pbCallNeedsHostHook`  
 <span data-ttu-id="c513f-107">enuncia Un puntero a un valor booleano que indica si el host requiere que se enlace la llamada.</span><span class="sxs-lookup"><span data-stu-id="c513f-107">[out] A pointer to a Boolean value that indicates whether the host requires the call to be hooked.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c513f-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c513f-108">Return Value</span></span>  
  
|<span data-ttu-id="c513f-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c513f-109">HRESULT</span></span>|<span data-ttu-id="c513f-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="c513f-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c513f-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="c513f-111">S_OK</span></span>|<span data-ttu-id="c513f-112">`CallNeedsHostHook`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="c513f-112">`CallNeedsHostHook` returned successfully.</span></span>|  
|<span data-ttu-id="c513f-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c513f-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c513f-114">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="c513f-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c513f-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c513f-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c513f-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="c513f-116">The call timed out.</span></span>|  
|<span data-ttu-id="c513f-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c513f-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c513f-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="c513f-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c513f-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c513f-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c513f-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="c513f-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c513f-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c513f-121">E_FAIL</span></span>|<span data-ttu-id="c513f-122">Se ha producido un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="c513f-122">An unknown catastrophic failure has occurred.</span></span> <span data-ttu-id="c513f-123">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="c513f-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c513f-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c513f-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c513f-125">Notas</span><span class="sxs-lookup"><span data-stu-id="c513f-125">Remarks</span></span>  
 <span data-ttu-id="c513f-126">Para ayudar a optimizar la ejecución del código, CLR realiza un análisis de cada llamada de invocación de plataforma durante la compilación para determinar si la llamada se puede insertar.</span><span class="sxs-lookup"><span data-stu-id="c513f-126">To help optimize code execution, the CLR performs an analysis of each platform invoke call during compilation to determine whether the call can be inlined.</span></span> <span data-ttu-id="c513f-127">`CallNeedsHostHook`permite que el host invalide esa decisión solicitando que se enlace una llamada a una función no administrada.</span><span class="sxs-lookup"><span data-stu-id="c513f-127">`CallNeedsHostHook` enables the host to override that decision by requiring that a call to an unmanaged function be hooked.</span></span> <span data-ttu-id="c513f-128">Si el host requiere un enlace, el runtime no insertará la llamada.</span><span class="sxs-lookup"><span data-stu-id="c513f-128">If the host requires a hook, the runtime does not inline the call.</span></span>  
  
 <span data-ttu-id="c513f-129">Normalmente, el host requeriría un enlace donde debe ajustar un estado de punto flotante o al recibir la notificación de que una llamada está entrando en un estado en el que el host no puede realizar el seguimiento de las solicitudes de memoria en tiempo de ejecución o de los bloqueos tomados.</span><span class="sxs-lookup"><span data-stu-id="c513f-129">The host typically would require a hook where it must adjust a floating-point state, or upon receiving notification that a call is entering a state where the host cannot track the runtime's requests for memory or any locks taken.</span></span> <span data-ttu-id="c513f-130">Cuando el host requiere que se enlace la llamada, el tiempo de ejecución notifica al host de las transiciones hacia y desde el código administrado mediante llamadas a [EnterRuntime (](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md), [LeaveRuntime (](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md), [ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md)y [ReverseLeaveRuntime](ihosttaskmanager-reverseleaveruntime-method.md).</span><span class="sxs-lookup"><span data-stu-id="c513f-130">When the host requires that the call be hooked, the runtime notifies the host of transitions to and from managed code by using calls to [EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md), [ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), and [ReverseLeaveRuntime](ihosttaskmanager-reverseleaveruntime-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c513f-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c513f-131">Requirements</span></span>  
 <span data-ttu-id="c513f-132">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c513f-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c513f-133">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c513f-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c513f-134">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c513f-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c513f-135">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c513f-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c513f-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="c513f-136">See also</span></span>

- [<span data-ttu-id="c513f-137">ICLRTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c513f-137">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="c513f-138">ICLRTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c513f-138">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="c513f-139">IHostTask (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c513f-139">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="c513f-140">IHostTaskManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c513f-140">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
