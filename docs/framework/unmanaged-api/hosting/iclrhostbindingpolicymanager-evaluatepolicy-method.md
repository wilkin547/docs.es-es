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
ms.openlocfilehash: 9600573a0a730cee10247d5644d587e75856cdd9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141181"
---
# <a name="iclrhostbindingpolicymanagerevaluatepolicy-method"></a><span data-ttu-id="ae3f4-102">ICLRHostBindingPolicyManager::EvaluatePolicy (Método)</span><span class="sxs-lookup"><span data-stu-id="ae3f4-102">ICLRHostBindingPolicyManager::EvaluatePolicy Method</span></span>
<span data-ttu-id="ae3f4-103">Evalúa la Directiva de enlace en nombre del host.</span><span class="sxs-lookup"><span data-stu-id="ae3f4-103">Evaluates binding policy on behalf of the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae3f4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ae3f4-104">Syntax</span></span>  
  
```cpp  
HRESULT EvaluatePolicy (  
    [in] LPCWSTR     pwzReferenceIdentity,  
    [in] BYTE       *pbApplicationPolicy,  
    [in] DWORD       cbAppPolicySize,  
    [out, size_is(*pcchPostPolicyReferenceIdentity)] LPWSTR pwzPostPolicyReferenceIdentity,  
    [in, out] DWORD *pcchPostPolicyReferenceIdentity,  
    [out] DWORD     *pdwPoliciesApplied  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ae3f4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ae3f4-105">Parameters</span></span>  
 `pwzReferenceIdentity`  
 <span data-ttu-id="ae3f4-106">de Referencia al ensamblado antes de la evaluación de la Directiva.</span><span class="sxs-lookup"><span data-stu-id="ae3f4-106">[in] A reference to the assembly before the policy evaluation.</span></span>  
  
 `pbApplicationPolicy`  
 <span data-ttu-id="ae3f4-107">de Un puntero a un búfer que contiene los datos de la Directiva.</span><span class="sxs-lookup"><span data-stu-id="ae3f4-107">[in] A pointer to a buffer that contains the policy data.</span></span>  
  
 `cbAppPolicySize`  
 <span data-ttu-id="ae3f4-108">de Tamaño del búfer de `pbApplicationPolicy`.</span><span class="sxs-lookup"><span data-stu-id="ae3f4-108">[in] The size of the `pbApplicationPolicy` buffer.</span></span>  
  
 `pwzPostPolicyReferenceIdentity`  
 <span data-ttu-id="ae3f4-109">enuncia Referencia al ensamblado después de la evaluación de los nuevos datos de la Directiva.</span><span class="sxs-lookup"><span data-stu-id="ae3f4-109">[out] A reference to the assembly after the evaluation of the new policy data.</span></span>  
  
 `pcchPostPolicyReferenceIdentity`  
 <span data-ttu-id="ae3f4-110">[in, out] Puntero al tamaño del búfer de referencia de identidad del ensamblado después de la evaluación de los datos de la nueva Directiva.</span><span class="sxs-lookup"><span data-stu-id="ae3f4-110">[in, out] A pointer to the size of the assembly identity reference buffer after the evaluation of the new policy data.</span></span>  
  
 `pdwPoliciesApplied`  
 <span data-ttu-id="ae3f4-111">enuncia Puntero a una combinación lógica o de valores de [ebindpolicylevels (](../../../../docs/framework/unmanaged-api/hosting/ebindpolicylevels-enumeration.md) , que indica qué directivas se han aplicado.</span><span class="sxs-lookup"><span data-stu-id="ae3f4-111">[out] A pointer to a logical OR combination of [EBindPolicyLevels](../../../../docs/framework/unmanaged-api/hosting/ebindpolicylevels-enumeration.md) values, indicating which policies have been applied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ae3f4-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ae3f4-112">Return Value</span></span>  
  
|<span data-ttu-id="ae3f4-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ae3f4-113">HRESULT</span></span>|<span data-ttu-id="ae3f4-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="ae3f4-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ae3f4-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="ae3f4-115">S_OK</span></span>|<span data-ttu-id="ae3f4-116">La evaluación se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="ae3f4-116">The evaluation completed successfully.</span></span>|  
|<span data-ttu-id="ae3f4-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="ae3f4-117">E_INVALIDARG</span></span>|<span data-ttu-id="ae3f4-118">`pwzReferenceIdentity` o `pbApplicationPolicy` es una referencia nula.</span><span class="sxs-lookup"><span data-stu-id="ae3f4-118">Either `pwzReferenceIdentity` or `pbApplicationPolicy` is a null reference.</span></span>|  
|<span data-ttu-id="ae3f4-119">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="ae3f4-119">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="ae3f4-120">`cbAppPolicySize` es demasiado pequeño.</span><span class="sxs-lookup"><span data-stu-id="ae3f4-120">`cbAppPolicySize` is too small.</span></span>|  
|<span data-ttu-id="ae3f4-121">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ae3f4-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ae3f4-122">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="ae3f4-122">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ae3f4-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ae3f4-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ae3f4-124">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="ae3f4-124">The call timed out.</span></span>|  
|<span data-ttu-id="ae3f4-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ae3f4-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ae3f4-126">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="ae3f4-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ae3f4-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ae3f4-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ae3f4-128">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="ae3f4-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ae3f4-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ae3f4-129">E_FAIL</span></span>|<span data-ttu-id="ae3f4-130">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="ae3f4-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ae3f4-131">Una vez que un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="ae3f4-131">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ae3f4-132">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ae3f4-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ae3f4-133">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ae3f4-133">Remarks</span></span>  
 <span data-ttu-id="ae3f4-134">El método `EvaluatePolicy` permite que el host influya en la Directiva de enlace para mantener los requisitos de control de versiones de ensamblado específicos del host.</span><span class="sxs-lookup"><span data-stu-id="ae3f4-134">The `EvaluatePolicy` method allows the host to influence binding policy to maintain host-specific assembly versioning requirements.</span></span> <span data-ttu-id="ae3f4-135">El propio motor de directivas permanece dentro de CLR.</span><span class="sxs-lookup"><span data-stu-id="ae3f4-135">The policy engine itself remains inside the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae3f4-136">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ae3f4-136">Requirements</span></span>  
 <span data-ttu-id="ae3f4-137">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ae3f4-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae3f4-138">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ae3f4-138">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ae3f4-139">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ae3f4-139">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ae3f4-140">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae3f4-140">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae3f4-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="ae3f4-141">See also</span></span>

- [<span data-ttu-id="ae3f4-142">ICLRHostBindingPolicyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ae3f4-142">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
