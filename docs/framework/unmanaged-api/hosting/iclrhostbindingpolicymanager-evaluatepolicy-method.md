---
title: ICLRHostBindingPolicyManager::EvaluatePolicy (Método)
ms.date: 03/30/2017
api_name:
- ICLRHostBindingPolicyManager.EvaluatePolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostBindingPolicyManager::EvaluatePolicy
helpviewer_keywords:
- ICLRHostBindingPolicyManager::EvaluatePolicy method [.NET Framework hosting]
- EvaluatePolicy method [.NET Framework hosting]
ms.assetid: 3a3a9446-7a4e-4836-9b27-5c536c15993d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 970e57e3caee7631c8e85aef428df52ec293b9cf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54648815"
---
# <a name="iclrhostbindingpolicymanagerevaluatepolicy-method"></a><span data-ttu-id="15301-102">ICLRHostBindingPolicyManager::EvaluatePolicy (Método)</span><span class="sxs-lookup"><span data-stu-id="15301-102">ICLRHostBindingPolicyManager::EvaluatePolicy Method</span></span>
<span data-ttu-id="15301-103">Evalúa la directiva de enlace en nombre del host.</span><span class="sxs-lookup"><span data-stu-id="15301-103">Evaluates binding policy on behalf of the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15301-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="15301-104">Syntax</span></span>  
  
```  
HRESULT EvaluatePolicy (  
    [in] LPCWSTR     pwzReferenceIdentity,  
    [in] BYTE       *pbApplicationPolicy,  
    [in] DWORD       cbAppPolicySize,  
    [out, size_is(*pcchPostPolicyReferenceIdentity)] LPWSTR pwzPostPolicyReferenceIdentity,  
    [in, out] DWORD *pcchPostPolicyReferenceIdentity,  
    [out] DWORD     *pdwPoliciesApplied  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="15301-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="15301-105">Parameters</span></span>  
 `pwzReferenceIdentity`  
 <span data-ttu-id="15301-106">[in] Una referencia al ensamblado antes de la evaluación de directivas.</span><span class="sxs-lookup"><span data-stu-id="15301-106">[in] A reference to the assembly before the policy evaluation.</span></span>  
  
 `pbApplicationPolicy`  
 <span data-ttu-id="15301-107">[in] Un puntero a un búfer que contiene los datos de la directiva.</span><span class="sxs-lookup"><span data-stu-id="15301-107">[in] A pointer to a buffer that contains the policy data.</span></span>  
  
 `cbAppPolicySize`  
 <span data-ttu-id="15301-108">[in] El tamaño de la `pbApplicationPolicy` búfer.</span><span class="sxs-lookup"><span data-stu-id="15301-108">[in] The size of the `pbApplicationPolicy` buffer.</span></span>  
  
 `pwzPostPolicyReferenceIdentity`  
 <span data-ttu-id="15301-109">[out] Una referencia al ensamblado después de la evaluación de los nuevos datos de directiva.</span><span class="sxs-lookup"><span data-stu-id="15301-109">[out] A reference to the assembly after the evaluation of the new policy data.</span></span>  
  
 `pcchPostPolicyReferenceIdentity`  
 <span data-ttu-id="15301-110">[in, out] Un puntero al tamaño del búfer de referencia de identidad de ensamblado después de la evaluación de los nuevos datos de directiva.</span><span class="sxs-lookup"><span data-stu-id="15301-110">[in, out] A pointer to the size of the assembly identity reference buffer after the evaluation of the new policy data.</span></span>  
  
 `pdwPoliciesApplied`  
 <span data-ttu-id="15301-111">[out] Un puntero a una combinación OR lógico de [EBindPolicyLevels](../../../../docs/framework/unmanaged-api/hosting/ebindpolicylevels-enumeration.md) valores, que indica qué directivas se han aplicado.</span><span class="sxs-lookup"><span data-stu-id="15301-111">[out] A pointer to a logical OR combination of [EBindPolicyLevels](../../../../docs/framework/unmanaged-api/hosting/ebindpolicylevels-enumeration.md) values, indicating which policies have been applied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="15301-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="15301-112">Return Value</span></span>  
  
|<span data-ttu-id="15301-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="15301-113">HRESULT</span></span>|<span data-ttu-id="15301-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="15301-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="15301-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="15301-115">S_OK</span></span>|<span data-ttu-id="15301-116">La evaluación finalizada correctamente.</span><span class="sxs-lookup"><span data-stu-id="15301-116">The evaluation completed successfully.</span></span>|  
|<span data-ttu-id="15301-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="15301-117">E_INVALIDARG</span></span>|<span data-ttu-id="15301-118">Ya sea `pwzReferenceIdentity` o `pbApplicationPolicy` es una referencia nula.</span><span class="sxs-lookup"><span data-stu-id="15301-118">Either `pwzReferenceIdentity` or `pbApplicationPolicy` is a null reference.</span></span>|  
|<span data-ttu-id="15301-119">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="15301-119">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="15301-120">`cbAppPolicySize` es demasiado pequeño.</span><span class="sxs-lookup"><span data-stu-id="15301-120">`cbAppPolicySize` is too small.</span></span>|  
|<span data-ttu-id="15301-121">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="15301-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="15301-122">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="15301-122">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="15301-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="15301-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="15301-124">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="15301-124">The call timed out.</span></span>|  
|<span data-ttu-id="15301-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="15301-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="15301-126">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="15301-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="15301-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="15301-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="15301-128">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="15301-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="15301-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="15301-129">E_FAIL</span></span>|<span data-ttu-id="15301-130">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="15301-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="15301-131">Después de un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="15301-131">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="15301-132">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="15301-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="15301-133">Comentarios</span><span class="sxs-lookup"><span data-stu-id="15301-133">Remarks</span></span>  
 <span data-ttu-id="15301-134">El `EvaluatePolicy` método permite al host influir en la directiva de enlace para mantener el ensamblado de host específico de los requisitos de control de versiones.</span><span class="sxs-lookup"><span data-stu-id="15301-134">The `EvaluatePolicy` method allows the host to influence binding policy to maintain host-specific assembly versioning requirements.</span></span> <span data-ttu-id="15301-135">El propio motor de directiva permanece dentro del CLR.</span><span class="sxs-lookup"><span data-stu-id="15301-135">The policy engine itself remains inside the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15301-136">Requisitos</span><span class="sxs-lookup"><span data-stu-id="15301-136">Requirements</span></span>  
 <span data-ttu-id="15301-137">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15301-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15301-138">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="15301-138">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="15301-139">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="15301-139">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="15301-140">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15301-140">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15301-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="15301-141">See also</span></span>
- [<span data-ttu-id="15301-142">ICLRHostBindingPolicyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="15301-142">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
