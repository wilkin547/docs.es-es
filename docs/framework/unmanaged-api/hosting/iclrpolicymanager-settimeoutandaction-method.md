---
description: 'Más información sobre: ICLRPolicyManager:: SetTimeoutAndAction ((método)'
title: ICLRPolicyManager::SetTimeoutAndAction (Método)
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetTimeoutAndAction
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetTimeoutAndAction
helpviewer_keywords:
- ICLRPolicyManager::SetTimeoutAndAction method [.NET Framework hosting]
- SetTimeoutAndAction method [.NET Framework hosting]
ms.assetid: 60454f91-d855-4ddf-bb6d-60a02f5eabab
topic_type:
- apiref
ms.openlocfilehash: c91d43cce381bef804b30e9e1dcb50574ddcd1b4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99716580"
---
# <a name="iclrpolicymanagersettimeoutandaction-method"></a><span data-ttu-id="f63fd-103">ICLRPolicyManager::SetTimeoutAndAction (Método)</span><span class="sxs-lookup"><span data-stu-id="f63fd-103">ICLRPolicyManager::SetTimeoutAndAction Method</span></span>

<span data-ttu-id="f63fd-104">Establece un valor de tiempo de espera para la operación especificada y especifica la acción de la Directiva que debe realizar el Common Language Runtime (CLR) cuando se produce la operación.</span><span class="sxs-lookup"><span data-stu-id="f63fd-104">Sets a timeout value for the specified operation, and specifies the policy action the common language runtime (CLR) should take when the operation occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f63fd-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f63fd-105">Syntax</span></span>  
  
```cpp  
HRESULT SetTimeoutAndAction (  
    [in] EClrOperation operation,  
    [in] DWORD dwMilliseconds,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f63fd-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f63fd-106">Parameters</span></span>  

 `operation`  
 <span data-ttu-id="f63fd-107">de Uno de los valores de [EClrOperation](eclroperation-enumeration.md) , que indica la operación para la que se va a establecer el tiempo de espera y la directiva `action` .</span><span class="sxs-lookup"><span data-stu-id="f63fd-107">[in] One of the [EClrOperation](eclroperation-enumeration.md) values, indicating the operation for which to set the timeout and policy `action`.</span></span> <span data-ttu-id="f63fd-108">Se admiten los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="f63fd-108">The following values are supported:</span></span>  
  
- <span data-ttu-id="f63fd-109">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="f63fd-109">OPR_AppDomainUnload</span></span>  
  
- <span data-ttu-id="f63fd-110">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="f63fd-110">OPR_ProcessExit</span></span>  
  
- <span data-ttu-id="f63fd-111">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="f63fd-111">OPR_ThreadRudeAbortInCriticalRegion</span></span>  
  
- <span data-ttu-id="f63fd-112">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="f63fd-112">OPR_ThreadRudeAbortInNonCriticalRegion</span></span>  
  
 `dwMilliseconds`  
 <span data-ttu-id="f63fd-113">de Nuevo valor de tiempo de espera, en milisegundos.</span><span class="sxs-lookup"><span data-stu-id="f63fd-113">[in] The new timeout value, in milliseconds.</span></span> <span data-ttu-id="f63fd-114">Un valor de infinito hace que `operation` nunca agote el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="f63fd-114">A value of INFINITE causes `operation` never to time out.</span></span>  
  
 `action`  
 <span data-ttu-id="f63fd-115">de Uno de los valores de [EPolicyAction](epolicyaction-enumeration.md) , que indica la acción de la Directiva que el CLR debe realizar cuando `operation` se produce.</span><span class="sxs-lookup"><span data-stu-id="f63fd-115">[in] One of the [EPolicyAction](epolicyaction-enumeration.md) values, indicating the policy action that the CLR should take when `operation` occurs.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f63fd-116">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f63fd-116">Return Value</span></span>  
  
|<span data-ttu-id="f63fd-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f63fd-117">HRESULT</span></span>|<span data-ttu-id="f63fd-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="f63fd-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f63fd-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="f63fd-119">S_OK</span></span>|<span data-ttu-id="f63fd-120">`SetTimeoutAndAction` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="f63fd-120">`SetTimeoutAndAction` returned successfully.</span></span>|  
|<span data-ttu-id="f63fd-121">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f63fd-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f63fd-122">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="f63fd-122">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f63fd-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f63fd-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f63fd-124">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="f63fd-124">The call timed out.</span></span>|  
|<span data-ttu-id="f63fd-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f63fd-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f63fd-126">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="f63fd-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f63fd-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f63fd-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f63fd-128">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="f63fd-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f63fd-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f63fd-129">E_FAIL</span></span>|<span data-ttu-id="f63fd-130">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="f63fd-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f63fd-131">Después de que un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="f63fd-131">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f63fd-132">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f63fd-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="f63fd-133">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="f63fd-133">E_INVALIDARG</span></span>|<span data-ttu-id="f63fd-134">No se puede establecer un tiempo de espera para el especificado `operation` o se proporcionó un valor no válido para `action` .</span><span class="sxs-lookup"><span data-stu-id="f63fd-134">A timeout cannot be set for the specified `operation`, or an invalid value was supplied for `action`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f63fd-135">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f63fd-135">Remarks</span></span>  

 <span data-ttu-id="f63fd-136">`SetTimeoutAndAction` encapsula las capacidades de los métodos [ICLRPolicyManager:: setTimeout](iclrpolicymanager-settimeout-method.md) y [ICLRPolicyManager:: SetActionOnTimeout (](iclrpolicymanager-setactionontimeout-method.md) , y se puede llamar en lugar de llamadas secuenciales a estos dos métodos.</span><span class="sxs-lookup"><span data-stu-id="f63fd-136">`SetTimeoutAndAction` encapsulates the capabilities of the [ICLRPolicyManager::SetTimeout](iclrpolicymanager-settimeout-method.md) and [ICLRPolicyManager::SetActionOnTimeout](iclrpolicymanager-setactionontimeout-method.md) methods, and can be called in place of sequential calls to these two methods.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="f63fd-137">No todos los valores de acción de Directiva se pueden especificar como el comportamiento de tiempo de espera para las operaciones CLR.</span><span class="sxs-lookup"><span data-stu-id="f63fd-137">Not all policy action values can be specified as the timeout behavior for CLR operations.</span></span> <span data-ttu-id="f63fd-138">Vea las secciones comentarios de los temas de estos dos métodos para ver los valores válidos.</span><span class="sxs-lookup"><span data-stu-id="f63fd-138">See the Remarks sections of the topics for these two methods for valid values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f63fd-139">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f63fd-139">Requirements</span></span>  

 <span data-ttu-id="f63fd-140">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f63fd-140">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f63fd-141">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f63fd-141">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f63fd-142">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f63fd-142">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f63fd-143">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f63fd-143">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f63fd-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="f63fd-144">See also</span></span>

- [<span data-ttu-id="f63fd-145">EClrOperation (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="f63fd-145">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="f63fd-146">EPolicyAction (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="f63fd-146">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="f63fd-147">ICLRPolicyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f63fd-147">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="f63fd-148">Método SetActionOnTimeout</span><span class="sxs-lookup"><span data-stu-id="f63fd-148">SetActionOnTimeout Method</span></span>](iclrpolicymanager-setactionontimeout-method.md)
- [<span data-ttu-id="f63fd-149">ICLRPolicyManager:: SetTimeoutAndAction (</span><span class="sxs-lookup"><span data-stu-id="f63fd-149">ICLRPolicyManager::SetTimeoutAndAction</span></span>](iclrpolicymanager-settimeoutandaction-method.md)
