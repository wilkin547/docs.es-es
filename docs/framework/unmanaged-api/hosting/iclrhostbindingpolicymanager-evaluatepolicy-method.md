---
description: 'Más información sobre: ICLRHostBindingPolicyManager:: Evaluatepolicy ((método)'
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
ms.openlocfilehash: e92126a8c12d03ee21e4867754b1a418ef11d463
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789975"
---
# <a name="iclrhostbindingpolicymanagerevaluatepolicy-method"></a><span data-ttu-id="ad388-103">ICLRHostBindingPolicyManager::EvaluatePolicy (Método)</span><span class="sxs-lookup"><span data-stu-id="ad388-103">ICLRHostBindingPolicyManager::EvaluatePolicy Method</span></span>

<span data-ttu-id="ad388-104">Evalúa la Directiva de enlace en nombre del host.</span><span class="sxs-lookup"><span data-stu-id="ad388-104">Evaluates binding policy on behalf of the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad388-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ad388-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="ad388-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ad388-106">Parameters</span></span>  

 `pwzReferenceIdentity`  
 <span data-ttu-id="ad388-107">de Referencia al ensamblado antes de la evaluación de la Directiva.</span><span class="sxs-lookup"><span data-stu-id="ad388-107">[in] A reference to the assembly before the policy evaluation.</span></span>  
  
 `pbApplicationPolicy`  
 <span data-ttu-id="ad388-108">de Un puntero a un búfer que contiene los datos de la Directiva.</span><span class="sxs-lookup"><span data-stu-id="ad388-108">[in] A pointer to a buffer that contains the policy data.</span></span>  
  
 `cbAppPolicySize`  
 <span data-ttu-id="ad388-109">de Tamaño del `pbApplicationPolicy` búfer.</span><span class="sxs-lookup"><span data-stu-id="ad388-109">[in] The size of the `pbApplicationPolicy` buffer.</span></span>  
  
 `pwzPostPolicyReferenceIdentity`  
 <span data-ttu-id="ad388-110">enuncia Referencia al ensamblado después de la evaluación de los nuevos datos de la Directiva.</span><span class="sxs-lookup"><span data-stu-id="ad388-110">[out] A reference to the assembly after the evaluation of the new policy data.</span></span>  
  
 `pcchPostPolicyReferenceIdentity`  
 <span data-ttu-id="ad388-111">[in, out] Puntero al tamaño del búfer de referencia de identidad del ensamblado después de la evaluación de los datos de la nueva Directiva.</span><span class="sxs-lookup"><span data-stu-id="ad388-111">[in, out] A pointer to the size of the assembly identity reference buffer after the evaluation of the new policy data.</span></span>  
  
 `pdwPoliciesApplied`  
 <span data-ttu-id="ad388-112">enuncia Puntero a una combinación lógica o de valores de [ebindpolicylevels (](ebindpolicylevels-enumeration.md) , que indica qué directivas se han aplicado.</span><span class="sxs-lookup"><span data-stu-id="ad388-112">[out] A pointer to a logical OR combination of [EBindPolicyLevels](ebindpolicylevels-enumeration.md) values, indicating which policies have been applied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ad388-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ad388-113">Return Value</span></span>  
  
|<span data-ttu-id="ad388-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ad388-114">HRESULT</span></span>|<span data-ttu-id="ad388-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="ad388-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ad388-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="ad388-116">S_OK</span></span>|<span data-ttu-id="ad388-117">La evaluación se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="ad388-117">The evaluation completed successfully.</span></span>|  
|<span data-ttu-id="ad388-118">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="ad388-118">E_INVALIDARG</span></span>|<span data-ttu-id="ad388-119">`pwzReferenceIdentity`O `pbApplicationPolicy` es una referencia nula.</span><span class="sxs-lookup"><span data-stu-id="ad388-119">Either `pwzReferenceIdentity` or `pbApplicationPolicy` is a null reference.</span></span>|  
|<span data-ttu-id="ad388-120">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="ad388-120">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="ad388-121">`cbAppPolicySize` es demasiado pequeño.</span><span class="sxs-lookup"><span data-stu-id="ad388-121">`cbAppPolicySize` is too small.</span></span>|  
|<span data-ttu-id="ad388-122">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ad388-122">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ad388-123">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="ad388-123">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ad388-124">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ad388-124">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ad388-125">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="ad388-125">The call timed out.</span></span>|  
|<span data-ttu-id="ad388-126">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ad388-126">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ad388-127">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="ad388-127">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ad388-128">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ad388-128">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ad388-129">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="ad388-129">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ad388-130">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ad388-130">E_FAIL</span></span>|<span data-ttu-id="ad388-131">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="ad388-131">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ad388-132">Después de que un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="ad388-132">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ad388-133">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ad388-133">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ad388-134">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ad388-134">Remarks</span></span>  

 <span data-ttu-id="ad388-135">El `EvaluatePolicy` método permite al host influir en la Directiva de enlace para mantener los requisitos de control de versiones de ensamblado específicos del host.</span><span class="sxs-lookup"><span data-stu-id="ad388-135">The `EvaluatePolicy` method allows the host to influence binding policy to maintain host-specific assembly versioning requirements.</span></span> <span data-ttu-id="ad388-136">El propio motor de directivas permanece dentro de CLR.</span><span class="sxs-lookup"><span data-stu-id="ad388-136">The policy engine itself remains inside the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad388-137">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ad388-137">Requirements</span></span>  

 <span data-ttu-id="ad388-138">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ad388-138">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad388-139">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ad388-139">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ad388-140">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ad388-140">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ad388-141">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad388-141">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad388-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="ad388-142">See also</span></span>

- [<span data-ttu-id="ad388-143">ICLRHostBindingPolicyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ad388-143">ICLRHostBindingPolicyManager Interface</span></span>](iclrhostbindingpolicymanager-interface.md)
