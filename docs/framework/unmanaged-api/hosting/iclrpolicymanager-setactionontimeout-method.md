---
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
ms.openlocfilehash: 3ddd78ea35d5709abb30af085b2212a09b28c2ef
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725565"
---
# <a name="iclrpolicymanagersetactionontimeout-method"></a><span data-ttu-id="024f6-102">ICLRPolicyManager::SetActionOnTimeout (Método)</span><span class="sxs-lookup"><span data-stu-id="024f6-102">ICLRPolicyManager::SetActionOnTimeout Method</span></span>

<span data-ttu-id="024f6-103">Especifica la acción de la Directiva que debe realizar el Common Language Runtime (CLR) cuando se agota el tiempo de espera de la operación especificada.</span><span class="sxs-lookup"><span data-stu-id="024f6-103">Specifies the policy action the common language runtime (CLR) should take when the specified operation times out.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="024f6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="024f6-104">Syntax</span></span>  
  
```cpp  
HRESULT SetActionOnTimeout (  
    [in] EClrOperation operation,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="024f6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="024f6-105">Parameters</span></span>  

 `operation`  
 <span data-ttu-id="024f6-106">de Uno de los valores de [EClrOperation](eclroperation-enumeration.md) , que indica la operación para la que se va a especificar la acción de tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="024f6-106">[in] One of the [EClrOperation](eclroperation-enumeration.md) values, indicating the operation for which to specify the timeout action.</span></span> <span data-ttu-id="024f6-107">Se admiten los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="024f6-107">The following values are supported:</span></span>  
  
- <span data-ttu-id="024f6-108">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="024f6-108">OPR_AppDomainUnload</span></span>  
  
- <span data-ttu-id="024f6-109">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="024f6-109">OPR_ProcessExit</span></span>  
  
- <span data-ttu-id="024f6-110">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="024f6-110">OPR_ThreadRudeAbortInCriticalRegion</span></span>  
  
- <span data-ttu-id="024f6-111">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="024f6-111">OPR_ThreadRudeAbortInNonCriticalRegion</span></span>  
  
 `action`  
 <span data-ttu-id="024f6-112">de Uno de los valores de [EPolicyAction](epolicyaction-enumeration.md) , que indica la acción de la Directiva que se debe realizar cuando se agota el tiempo de espera de la operación.</span><span class="sxs-lookup"><span data-stu-id="024f6-112">[in] One of the [EPolicyAction](epolicyaction-enumeration.md) values, indicating the policy action to be taken when the operation times out.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="024f6-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="024f6-113">Return Value</span></span>  
  
|<span data-ttu-id="024f6-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="024f6-114">HRESULT</span></span>|<span data-ttu-id="024f6-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="024f6-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="024f6-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="024f6-116">S_OK</span></span>|<span data-ttu-id="024f6-117">`SetActionOnTimeout` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="024f6-117">`SetActionOnTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="024f6-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="024f6-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="024f6-119">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="024f6-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="024f6-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="024f6-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="024f6-121">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="024f6-121">The call timed out.</span></span>|  
|<span data-ttu-id="024f6-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="024f6-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="024f6-123">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="024f6-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="024f6-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="024f6-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="024f6-125">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="024f6-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="024f6-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="024f6-126">E_FAIL</span></span>|<span data-ttu-id="024f6-127">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="024f6-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="024f6-128">Después de que un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="024f6-128">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="024f6-129">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="024f6-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="024f6-130">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="024f6-130">E_INVALIDARG</span></span>|<span data-ttu-id="024f6-131">No se puede establecer un tiempo de espera para el especificado `operation` o se proporcionó un valor no válido para `operation` .</span><span class="sxs-lookup"><span data-stu-id="024f6-131">A timeout cannot be set for the specified `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="024f6-132">Comentarios</span><span class="sxs-lookup"><span data-stu-id="024f6-132">Remarks</span></span>  

 <span data-ttu-id="024f6-133">El valor de tiempo de espera puede ser el tiempo de espera predeterminado establecido por CLR o un valor especificado por el host en una llamada al método [ICLRPolicyManager:: setTimeout](iclrpolicymanager-settimeout-method.md) .</span><span class="sxs-lookup"><span data-stu-id="024f6-133">The timeout value can be either the default timeout set by the CLR, or a value specified by the host in a call to the [ICLRPolicyManager::SetTimeout](iclrpolicymanager-settimeout-method.md) method.</span></span>  
  
 <span data-ttu-id="024f6-134">No todos los valores de acción de Directiva se pueden especificar como el comportamiento de tiempo de espera para las operaciones CLR.</span><span class="sxs-lookup"><span data-stu-id="024f6-134">Not all policy action values can be specified as the timeout behavior for CLR operations.</span></span> <span data-ttu-id="024f6-135">`SetActionOnTimeout` normalmente solo se usa para escalar el comportamiento.</span><span class="sxs-lookup"><span data-stu-id="024f6-135">`SetActionOnTimeout` is typically used only to escalate behavior.</span></span> <span data-ttu-id="024f6-136">Por ejemplo, un host puede especificar que las anulaciones de subprocesos se conviertan en anulaciones de subproceso forzada, pero no puede especificar lo contrario.</span><span class="sxs-lookup"><span data-stu-id="024f6-136">For example, a host can specify that thread aborts be turned into rude thread aborts, but cannot specify the opposite.</span></span> <span data-ttu-id="024f6-137">En la tabla siguiente se describen los valores válidos `action` para `operation` los valores válidos.</span><span class="sxs-lookup"><span data-stu-id="024f6-137">The table below describes the valid `action` values for valid `operation` values.</span></span>  
  
|<span data-ttu-id="024f6-138">Valor de `operation`</span><span class="sxs-lookup"><span data-stu-id="024f6-138">Value for `operation`</span></span>|<span data-ttu-id="024f6-139">Valores válidos para `action`</span><span class="sxs-lookup"><span data-stu-id="024f6-139">Valid values for `action`</span></span>|  
|---------------------------|-------------------------------|  
|<span data-ttu-id="024f6-140">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="024f6-140">OPR_ThreadRudeAbortInNonCriticalRegion</span></span><br /><br /> <span data-ttu-id="024f6-141">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="024f6-141">OPR_ThreadRudeAbortInCriticalRegion</span></span>|<span data-ttu-id="024f6-142">- eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="024f6-142">-   eRudeAbortThread</span></span><br /><span data-ttu-id="024f6-143">- eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="024f6-143">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="024f6-144">- eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="024f6-144">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="024f6-145">- eExitProcess</span><span class="sxs-lookup"><span data-stu-id="024f6-145">-   eExitProcess</span></span><br /><span data-ttu-id="024f6-146">- eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="024f6-146">-   eFastExitProcess</span></span><br /><span data-ttu-id="024f6-147">- eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="024f6-147">-   eRudeExitProcess</span></span><br /><span data-ttu-id="024f6-148">- eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="024f6-148">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="024f6-149">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="024f6-149">OPR_AppDomainUnload</span></span>|<span data-ttu-id="024f6-150">- eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="024f6-150">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="024f6-151">- eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="024f6-151">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="024f6-152">- eExitProcess</span><span class="sxs-lookup"><span data-stu-id="024f6-152">-   eExitProcess</span></span><br /><span data-ttu-id="024f6-153">- eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="024f6-153">-   eFastExitProcess</span></span><br /><span data-ttu-id="024f6-154">- eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="024f6-154">-   eRudeExitProcess</span></span><br /><span data-ttu-id="024f6-155">- eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="024f6-155">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="024f6-156">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="024f6-156">OPR_ProcessExit</span></span>|<span data-ttu-id="024f6-157">- eExitProcess</span><span class="sxs-lookup"><span data-stu-id="024f6-157">-   eExitProcess</span></span><br /><span data-ttu-id="024f6-158">- eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="024f6-158">-   eFastExitProcess</span></span><br /><span data-ttu-id="024f6-159">- eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="024f6-159">-   eRudeExitProcess</span></span><br /><span data-ttu-id="024f6-160">- eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="024f6-160">-   eDisableRuntime</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="024f6-161">Requisitos</span><span class="sxs-lookup"><span data-stu-id="024f6-161">Requirements</span></span>  

 <span data-ttu-id="024f6-162">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="024f6-162">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="024f6-163">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="024f6-163">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="024f6-164">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="024f6-164">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="024f6-165">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="024f6-165">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="024f6-166">Consulte también</span><span class="sxs-lookup"><span data-stu-id="024f6-166">See also</span></span>

- [<span data-ttu-id="024f6-167">EClrOperation (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="024f6-167">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="024f6-168">EPolicyAction (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="024f6-168">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="024f6-169">ICLRControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="024f6-169">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="024f6-170">ICLRPolicyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="024f6-170">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
