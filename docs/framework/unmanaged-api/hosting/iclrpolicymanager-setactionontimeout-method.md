---
description: 'Más información sobre: ICLRPolicyManager:: SetActionOnTimeout ((método)'
title: ICLRPolicyManager::SetActionOnTimeout (Método)
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetActionOnTimeout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetActionOnTimeout
helpviewer_keywords:
- SetActionOnTimeout method [.NET Framework hosting]
- ICLRPolicyManager::SetActionOnTimeout method [.NET Framework hosting]
ms.assetid: 38439fa1-2b99-4fa8-a6ec-08afc0f83b9c
topic_type:
- apiref
ms.openlocfilehash: d682acd49bdc4fa0f8c58a1300e2215816fe2718
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99689032"
---
# <a name="iclrpolicymanagersetactionontimeout-method"></a><span data-ttu-id="3e19e-103">ICLRPolicyManager::SetActionOnTimeout (Método)</span><span class="sxs-lookup"><span data-stu-id="3e19e-103">ICLRPolicyManager::SetActionOnTimeout Method</span></span>

<span data-ttu-id="3e19e-104">Especifica la acción de la Directiva que debe realizar el Common Language Runtime (CLR) cuando se agota el tiempo de espera de la operación especificada.</span><span class="sxs-lookup"><span data-stu-id="3e19e-104">Specifies the policy action the common language runtime (CLR) should take when the specified operation times out.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e19e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3e19e-105">Syntax</span></span>  
  
```cpp  
HRESULT SetActionOnTimeout (  
    [in] EClrOperation operation,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3e19e-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3e19e-106">Parameters</span></span>  

 `operation`  
 <span data-ttu-id="3e19e-107">de Uno de los valores de [EClrOperation](eclroperation-enumeration.md) , que indica la operación para la que se va a especificar la acción de tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="3e19e-107">[in] One of the [EClrOperation](eclroperation-enumeration.md) values, indicating the operation for which to specify the timeout action.</span></span> <span data-ttu-id="3e19e-108">Se admiten los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="3e19e-108">The following values are supported:</span></span>  
  
- <span data-ttu-id="3e19e-109">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="3e19e-109">OPR_AppDomainUnload</span></span>  
  
- <span data-ttu-id="3e19e-110">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="3e19e-110">OPR_ProcessExit</span></span>  
  
- <span data-ttu-id="3e19e-111">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="3e19e-111">OPR_ThreadRudeAbortInCriticalRegion</span></span>  
  
- <span data-ttu-id="3e19e-112">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="3e19e-112">OPR_ThreadRudeAbortInNonCriticalRegion</span></span>  
  
 `action`  
 <span data-ttu-id="3e19e-113">de Uno de los valores de [EPolicyAction](epolicyaction-enumeration.md) , que indica la acción de la Directiva que se debe realizar cuando se agota el tiempo de espera de la operación.</span><span class="sxs-lookup"><span data-stu-id="3e19e-113">[in] One of the [EPolicyAction](epolicyaction-enumeration.md) values, indicating the policy action to be taken when the operation times out.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3e19e-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3e19e-114">Return Value</span></span>  
  
|<span data-ttu-id="3e19e-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3e19e-115">HRESULT</span></span>|<span data-ttu-id="3e19e-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="3e19e-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3e19e-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="3e19e-117">S_OK</span></span>|<span data-ttu-id="3e19e-118">`SetActionOnTimeout` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="3e19e-118">`SetActionOnTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="3e19e-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3e19e-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3e19e-120">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="3e19e-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3e19e-121">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3e19e-121">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3e19e-122">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="3e19e-122">The call timed out.</span></span>|  
|<span data-ttu-id="3e19e-123">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3e19e-123">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3e19e-124">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="3e19e-124">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3e19e-125">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3e19e-125">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3e19e-126">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="3e19e-126">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3e19e-127">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3e19e-127">E_FAIL</span></span>|<span data-ttu-id="3e19e-128">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="3e19e-128">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3e19e-129">Después de que un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="3e19e-129">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3e19e-130">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="3e19e-130">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="3e19e-131">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="3e19e-131">E_INVALIDARG</span></span>|<span data-ttu-id="3e19e-132">No se puede establecer un tiempo de espera para el especificado `operation` o se proporcionó un valor no válido para `operation` .</span><span class="sxs-lookup"><span data-stu-id="3e19e-132">A timeout cannot be set for the specified `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3e19e-133">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3e19e-133">Remarks</span></span>  

 <span data-ttu-id="3e19e-134">El valor de tiempo de espera puede ser el tiempo de espera predeterminado establecido por CLR o un valor especificado por el host en una llamada al método [ICLRPolicyManager:: setTimeout](iclrpolicymanager-settimeout-method.md) .</span><span class="sxs-lookup"><span data-stu-id="3e19e-134">The timeout value can be either the default timeout set by the CLR, or a value specified by the host in a call to the [ICLRPolicyManager::SetTimeout](iclrpolicymanager-settimeout-method.md) method.</span></span>  
  
 <span data-ttu-id="3e19e-135">No todos los valores de acción de Directiva se pueden especificar como el comportamiento de tiempo de espera para las operaciones CLR.</span><span class="sxs-lookup"><span data-stu-id="3e19e-135">Not all policy action values can be specified as the timeout behavior for CLR operations.</span></span> <span data-ttu-id="3e19e-136">`SetActionOnTimeout` normalmente solo se usa para escalar el comportamiento.</span><span class="sxs-lookup"><span data-stu-id="3e19e-136">`SetActionOnTimeout` is typically used only to escalate behavior.</span></span> <span data-ttu-id="3e19e-137">Por ejemplo, un host puede especificar que las anulaciones de subprocesos se conviertan en anulaciones de subproceso forzada, pero no puede especificar lo contrario.</span><span class="sxs-lookup"><span data-stu-id="3e19e-137">For example, a host can specify that thread aborts be turned into rude thread aborts, but cannot specify the opposite.</span></span> <span data-ttu-id="3e19e-138">En la tabla siguiente se describen los valores válidos `action` para `operation` los valores válidos.</span><span class="sxs-lookup"><span data-stu-id="3e19e-138">The table below describes the valid `action` values for valid `operation` values.</span></span>  
  
|<span data-ttu-id="3e19e-139">Valor de `operation`</span><span class="sxs-lookup"><span data-stu-id="3e19e-139">Value for `operation`</span></span>|<span data-ttu-id="3e19e-140">Valores válidos para `action`</span><span class="sxs-lookup"><span data-stu-id="3e19e-140">Valid values for `action`</span></span>|  
|---------------------------|-------------------------------|  
|<span data-ttu-id="3e19e-141">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="3e19e-141">OPR_ThreadRudeAbortInNonCriticalRegion</span></span><br /><br /> <span data-ttu-id="3e19e-142">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="3e19e-142">OPR_ThreadRudeAbortInCriticalRegion</span></span>|<span data-ttu-id="3e19e-143">- eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="3e19e-143">-   eRudeAbortThread</span></span><br /><span data-ttu-id="3e19e-144">- eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="3e19e-144">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="3e19e-145">- eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="3e19e-145">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="3e19e-146">- eExitProcess</span><span class="sxs-lookup"><span data-stu-id="3e19e-146">-   eExitProcess</span></span><br /><span data-ttu-id="3e19e-147">- eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="3e19e-147">-   eFastExitProcess</span></span><br /><span data-ttu-id="3e19e-148">- eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="3e19e-148">-   eRudeExitProcess</span></span><br /><span data-ttu-id="3e19e-149">- eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="3e19e-149">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="3e19e-150">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="3e19e-150">OPR_AppDomainUnload</span></span>|<span data-ttu-id="3e19e-151">- eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="3e19e-151">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="3e19e-152">- eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="3e19e-152">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="3e19e-153">- eExitProcess</span><span class="sxs-lookup"><span data-stu-id="3e19e-153">-   eExitProcess</span></span><br /><span data-ttu-id="3e19e-154">- eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="3e19e-154">-   eFastExitProcess</span></span><br /><span data-ttu-id="3e19e-155">- eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="3e19e-155">-   eRudeExitProcess</span></span><br /><span data-ttu-id="3e19e-156">- eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="3e19e-156">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="3e19e-157">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="3e19e-157">OPR_ProcessExit</span></span>|<span data-ttu-id="3e19e-158">- eExitProcess</span><span class="sxs-lookup"><span data-stu-id="3e19e-158">-   eExitProcess</span></span><br /><span data-ttu-id="3e19e-159">- eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="3e19e-159">-   eFastExitProcess</span></span><br /><span data-ttu-id="3e19e-160">- eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="3e19e-160">-   eRudeExitProcess</span></span><br /><span data-ttu-id="3e19e-161">- eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="3e19e-161">-   eDisableRuntime</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3e19e-162">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3e19e-162">Requirements</span></span>  

 <span data-ttu-id="3e19e-163">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3e19e-163">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e19e-164">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="3e19e-164">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3e19e-165">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3e19e-165">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3e19e-166">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e19e-166">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e19e-167">Vea también</span><span class="sxs-lookup"><span data-stu-id="3e19e-167">See also</span></span>

- [<span data-ttu-id="3e19e-168">EClrOperation (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="3e19e-168">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="3e19e-169">EPolicyAction (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="3e19e-169">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="3e19e-170">ICLRControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3e19e-170">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="3e19e-171">ICLRPolicyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3e19e-171">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
