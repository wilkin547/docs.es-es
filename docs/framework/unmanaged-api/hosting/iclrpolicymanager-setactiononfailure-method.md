---
description: 'Más información sobre: ICLRPolicyManager:: Setactiononfailure ((método)'
title: ICLRPolicyManager::SetActionOnFailure (Método)
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetActionOnFailure
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetActionOnFailure
helpviewer_keywords:
- SetActionOnFailure method [.NET Framework hosting]
- ICLRPolicyManager::SetActionOnFailure method [.NET Framework hosting]
ms.assetid: 4664033f-db97-4388-b988-2ec470796e58
topic_type:
- apiref
ms.openlocfilehash: 67d3ca5d7924caf0a768b4de53b4b24f1c72fa27
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789806"
---
# <a name="iclrpolicymanagersetactiononfailure-method"></a><span data-ttu-id="55c6a-103">ICLRPolicyManager::SetActionOnFailure (Método)</span><span class="sxs-lookup"><span data-stu-id="55c6a-103">ICLRPolicyManager::SetActionOnFailure Method</span></span>

<span data-ttu-id="55c6a-104">Especifica la acción de la Directiva que debe realizar el Common Language Runtime (CLR) cuando se produce el error especificado.</span><span class="sxs-lookup"><span data-stu-id="55c6a-104">Specifies the policy action the common language runtime (CLR) should take when the specified failure occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55c6a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="55c6a-105">Syntax</span></span>  
  
```cpp  
HRESULT SetActionOnFailure (  
    [in] EClrFailure   failure,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="55c6a-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="55c6a-106">Parameters</span></span>  

 `failure`  
 <span data-ttu-id="55c6a-107">de Uno de los valores de [eclrfailure (](eclrfailure-enumeration.md) , que indica el tipo de error para el que se realizará la acción.</span><span class="sxs-lookup"><span data-stu-id="55c6a-107">[in] One of the [EClrFailure](eclrfailure-enumeration.md) values, indicating the type of failure for which to take action.</span></span>  
  
 `action`  
 <span data-ttu-id="55c6a-108">de Uno de los valores de [EPolicyAction](epolicyaction-enumeration.md) , que indica la acción que se debe realizar cuando se produce un error.</span><span class="sxs-lookup"><span data-stu-id="55c6a-108">[in] One of the [EPolicyAction](epolicyaction-enumeration.md) values, indicating the action to be taken when a failure occurs.</span></span> <span data-ttu-id="55c6a-109">Para obtener una lista de valores admitidos, vea la sección Comentarios.</span><span class="sxs-lookup"><span data-stu-id="55c6a-109">For a list of supported values, see the Remarks section.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="55c6a-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="55c6a-110">Return Value</span></span>  
  
|<span data-ttu-id="55c6a-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="55c6a-111">HRESULT</span></span>|<span data-ttu-id="55c6a-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="55c6a-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="55c6a-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="55c6a-113">S_OK</span></span>|<span data-ttu-id="55c6a-114">`SetActionOnFailure` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="55c6a-114">`SetActionOnFailure` returned successfully.</span></span>|  
|<span data-ttu-id="55c6a-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="55c6a-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="55c6a-116">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="55c6a-116">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="55c6a-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="55c6a-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="55c6a-118">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="55c6a-118">The call timed out.</span></span>|  
|<span data-ttu-id="55c6a-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="55c6a-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="55c6a-120">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="55c6a-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="55c6a-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="55c6a-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="55c6a-122">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="55c6a-122">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="55c6a-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="55c6a-123">E_FAIL</span></span>|<span data-ttu-id="55c6a-124">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="55c6a-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="55c6a-125">Después de que un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="55c6a-125">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="55c6a-126">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="55c6a-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="55c6a-127">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="55c6a-127">E_INVALIDARG</span></span>|<span data-ttu-id="55c6a-128">No se puede establecer una acción de directiva para la operación especificada o se especificó una acción de Directiva no válida para la operación.</span><span class="sxs-lookup"><span data-stu-id="55c6a-128">A policy action cannot be set for the specified operation, or an invalid policy action was specified for the operation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="55c6a-129">Observaciones</span><span class="sxs-lookup"><span data-stu-id="55c6a-129">Remarks</span></span>  

 <span data-ttu-id="55c6a-130">De forma predeterminada, CLR produce una excepción cuando no puede asignar un recurso como memoria.</span><span class="sxs-lookup"><span data-stu-id="55c6a-130">By default, the CLR throws an exception when it fails to allocate a resource such as memory.</span></span> <span data-ttu-id="55c6a-131">`SetActionOnFailure` permite que el host Invalide este comportamiento especificando la acción de la Directiva que se realizará en caso de error.</span><span class="sxs-lookup"><span data-stu-id="55c6a-131">`SetActionOnFailure` allows the host to override this behavior by specifying the policy action to take upon failure.</span></span> <span data-ttu-id="55c6a-132">En la tabla siguiente se muestran las combinaciones de los valores [eclrfailure (](eclrfailure-enumeration.md) y [EPolicyAction](epolicyaction-enumeration.md) que se admiten.</span><span class="sxs-lookup"><span data-stu-id="55c6a-132">The following table shows the combinations of [EClrFailure](eclrfailure-enumeration.md) and [EPolicyAction](epolicyaction-enumeration.md) values that are supported.</span></span> <span data-ttu-id="55c6a-133">(El prefijo FAIL_ se omite de los valores de [eclrfailure (](eclrfailure-enumeration.md) ).</span><span class="sxs-lookup"><span data-stu-id="55c6a-133">(The FAIL_ prefix is omitted from [EClrFailure](eclrfailure-enumeration.md) values.)</span></span>  
  
||<span data-ttu-id="55c6a-134">NonCriticalResource</span><span class="sxs-lookup"><span data-stu-id="55c6a-134">NonCriticalResource</span></span>|<span data-ttu-id="55c6a-135">CriticalResource</span><span class="sxs-lookup"><span data-stu-id="55c6a-135">CriticalResource</span></span>|<span data-ttu-id="55c6a-136">FatalRuntime</span><span class="sxs-lookup"><span data-stu-id="55c6a-136">FatalRuntime</span></span>|<span data-ttu-id="55c6a-137">OrphanedLock</span><span class="sxs-lookup"><span data-stu-id="55c6a-137">OrphanedLock</span></span>|<span data-ttu-id="55c6a-138">StackOverflow</span><span class="sxs-lookup"><span data-stu-id="55c6a-138">StackOverflow</span></span>|<span data-ttu-id="55c6a-139">AccessViolation</span><span class="sxs-lookup"><span data-stu-id="55c6a-139">AccessViolation</span></span>|<span data-ttu-id="55c6a-140">CodeContract</span><span class="sxs-lookup"><span data-stu-id="55c6a-140">CodeContract</span></span>|  
|-|-------------------------|----------------------|------------------|------------------|-------------------|---------------------|------------------|  
|`eNoAction`|<span data-ttu-id="55c6a-141">X</span><span class="sxs-lookup"><span data-stu-id="55c6a-141">X</span></span>|<span data-ttu-id="55c6a-142">X</span><span class="sxs-lookup"><span data-stu-id="55c6a-142">X</span></span>||||<span data-ttu-id="55c6a-143">N/D</span><span class="sxs-lookup"><span data-stu-id="55c6a-143">N/A</span></span>||  
|<span data-ttu-id="55c6a-144">eThrowException</span><span class="sxs-lookup"><span data-stu-id="55c6a-144">eThrowException</span></span>|<span data-ttu-id="55c6a-145">X</span><span class="sxs-lookup"><span data-stu-id="55c6a-145">X</span></span>|<span data-ttu-id="55c6a-146">X</span><span class="sxs-lookup"><span data-stu-id="55c6a-146">X</span></span>||||<span data-ttu-id="55c6a-147">N/D</span><span class="sxs-lookup"><span data-stu-id="55c6a-147">N/A</span></span>||  
|`eAbortThread`|<span data-ttu-id="55c6a-148">X</span><span class="sxs-lookup"><span data-stu-id="55c6a-148">X</span></span>|<span data-ttu-id="55c6a-149">X</span><span class="sxs-lookup"><span data-stu-id="55c6a-149">X</span></span>||||<span data-ttu-id="55c6a-150">N/D</span><span class="sxs-lookup"><span data-stu-id="55c6a-150">N/A</span></span>|<span data-ttu-id="55c6a-151">X</span><span class="sxs-lookup"><span data-stu-id="55c6a-151">X</span></span>|  
|`eRudeAbortThread`|<span data-ttu-id="55c6a-152">X</span><span class="sxs-lookup"><span data-stu-id="55c6a-152">X</span></span>|<span data-ttu-id="55c6a-153">X</span><span class="sxs-lookup"><span data-stu-id="55c6a-153">X</span></span>||||<span data-ttu-id="55c6a-154">N/D</span><span class="sxs-lookup"><span data-stu-id="55c6a-154">N/A</span></span>|<span data-ttu-id="55c6a-155">X</span><span class="sxs-lookup"><span data-stu-id="55c6a-155">X</span></span>|  
|`eUnloadAppDomain`|<span data-ttu-id="55c6a-156">X</span><span class="sxs-lookup"><span data-stu-id="55c6a-156">X</span></span>|<span data-ttu-id="55c6a-157">X</span><span class="sxs-lookup"><span data-stu-id="55c6a-157">X</span></span>||<span data-ttu-id="55c6a-158">X</span><span class="sxs-lookup"><span data-stu-id="55c6a-158">X</span></span>||<span data-ttu-id="55c6a-159">N/D</span><span class="sxs-lookup"><span data-stu-id="55c6a-159">N/A</span></span>|<span data-ttu-id="55c6a-160">X</span><span class="sxs-lookup"><span data-stu-id="55c6a-160">X</span></span>|  
|`eRudeUnloadAppDomain`|<span data-ttu-id="55c6a-161">X</span><span class="sxs-lookup"><span data-stu-id="55c6a-161">X</span></span>|<span data-ttu-id="55c6a-162">X</span><span class="sxs-lookup"><span data-stu-id="55c6a-162">X</span></span>||<span data-ttu-id="55c6a-163">X</span><span class="sxs-lookup"><span data-stu-id="55c6a-163">X</span></span>|<span data-ttu-id="55c6a-164">X</span><span class="sxs-lookup"><span data-stu-id="55c6a-164">X</span></span>|<span data-ttu-id="55c6a-165">N/D</span><span class="sxs-lookup"><span data-stu-id="55c6a-165">N/A</span></span>|<span data-ttu-id="55c6a-166">X</span><span class="sxs-lookup"><span data-stu-id="55c6a-166">X</span></span>|  
|`eExitProcess`|<span data-ttu-id="55c6a-167">X</span><span class="sxs-lookup"><span data-stu-id="55c6a-167">X</span></span>|<span data-ttu-id="55c6a-168">X</span><span class="sxs-lookup"><span data-stu-id="55c6a-168">X</span></span>||<span data-ttu-id="55c6a-169">X</span><span class="sxs-lookup"><span data-stu-id="55c6a-169">X</span></span>|<span data-ttu-id="55c6a-170">X</span><span class="sxs-lookup"><span data-stu-id="55c6a-170">X</span></span>|<span data-ttu-id="55c6a-171">N/D</span><span class="sxs-lookup"><span data-stu-id="55c6a-171">N/A</span></span>|<span data-ttu-id="55c6a-172">X</span><span class="sxs-lookup"><span data-stu-id="55c6a-172">X</span></span>|  
|<span data-ttu-id="55c6a-173">eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="55c6a-173">eFastExitProcess</span></span>|<span data-ttu-id="55c6a-174">X</span><span class="sxs-lookup"><span data-stu-id="55c6a-174">X</span></span>|<span data-ttu-id="55c6a-175">X</span><span class="sxs-lookup"><span data-stu-id="55c6a-175">X</span></span>||<span data-ttu-id="55c6a-176">X</span><span class="sxs-lookup"><span data-stu-id="55c6a-176">X</span></span>|<span data-ttu-id="55c6a-177">X</span><span class="sxs-lookup"><span data-stu-id="55c6a-177">X</span></span>|<span data-ttu-id="55c6a-178">N/D</span><span class="sxs-lookup"><span data-stu-id="55c6a-178">N/A</span></span>||  
|`eRudeExitProcess`|<span data-ttu-id="55c6a-179">X</span><span class="sxs-lookup"><span data-stu-id="55c6a-179">X</span></span>|<span data-ttu-id="55c6a-180">X</span><span class="sxs-lookup"><span data-stu-id="55c6a-180">X</span></span>|<span data-ttu-id="55c6a-181">X</span><span class="sxs-lookup"><span data-stu-id="55c6a-181">X</span></span>|<span data-ttu-id="55c6a-182">X</span><span class="sxs-lookup"><span data-stu-id="55c6a-182">X</span></span>|<span data-ttu-id="55c6a-183">X</span><span class="sxs-lookup"><span data-stu-id="55c6a-183">X</span></span>|<span data-ttu-id="55c6a-184">N/D</span><span class="sxs-lookup"><span data-stu-id="55c6a-184">N/A</span></span>||  
|`eDisableRuntime`|<span data-ttu-id="55c6a-185">X</span><span class="sxs-lookup"><span data-stu-id="55c6a-185">X</span></span>|<span data-ttu-id="55c6a-186">X</span><span class="sxs-lookup"><span data-stu-id="55c6a-186">X</span></span>|<span data-ttu-id="55c6a-187">X</span><span class="sxs-lookup"><span data-stu-id="55c6a-187">X</span></span>|<span data-ttu-id="55c6a-188">X</span><span class="sxs-lookup"><span data-stu-id="55c6a-188">X</span></span>|<span data-ttu-id="55c6a-189">X</span><span class="sxs-lookup"><span data-stu-id="55c6a-189">X</span></span>|<span data-ttu-id="55c6a-190">N/D</span><span class="sxs-lookup"><span data-stu-id="55c6a-190">N/A</span></span>||  
  
## <a name="requirements"></a><span data-ttu-id="55c6a-191">Requisitos</span><span class="sxs-lookup"><span data-stu-id="55c6a-191">Requirements</span></span>  

 <span data-ttu-id="55c6a-192">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="55c6a-192">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55c6a-193">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="55c6a-193">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="55c6a-194">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="55c6a-194">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="55c6a-195">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55c6a-195">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55c6a-196">Vea también</span><span class="sxs-lookup"><span data-stu-id="55c6a-196">See also</span></span>

- [<span data-ttu-id="55c6a-197">EClrFailure (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="55c6a-197">EClrFailure Enumeration</span></span>](eclrfailure-enumeration.md)
- [<span data-ttu-id="55c6a-198">EPolicyAction (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="55c6a-198">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="55c6a-199">ICLRControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="55c6a-199">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="55c6a-200">ICLRPolicyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="55c6a-200">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
