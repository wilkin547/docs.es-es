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
ms.openlocfilehash: f72a66354bfc907dab7ebc24de515bdfb20ddfb2
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703602"
---
# <a name="iclrhostbindingpolicymanagerevaluatepolicy-method"></a><span data-ttu-id="89df9-102">ICLRHostBindingPolicyManager::EvaluatePolicy (Método)</span><span class="sxs-lookup"><span data-stu-id="89df9-102">ICLRHostBindingPolicyManager::EvaluatePolicy Method</span></span>
<span data-ttu-id="89df9-103">Evalúa la Directiva de enlace en nombre del host.</span><span class="sxs-lookup"><span data-stu-id="89df9-103">Evaluates binding policy on behalf of the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89df9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="89df9-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="89df9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="89df9-105">Parameters</span></span>  
 `pwzReferenceIdentity`  
 <span data-ttu-id="89df9-106">de Referencia al ensamblado antes de la evaluación de la Directiva.</span><span class="sxs-lookup"><span data-stu-id="89df9-106">[in] A reference to the assembly before the policy evaluation.</span></span>  
  
 `pbApplicationPolicy`  
 <span data-ttu-id="89df9-107">de Un puntero a un búfer que contiene los datos de la Directiva.</span><span class="sxs-lookup"><span data-stu-id="89df9-107">[in] A pointer to a buffer that contains the policy data.</span></span>  
  
 `cbAppPolicySize`  
 <span data-ttu-id="89df9-108">de Tamaño del `pbApplicationPolicy` búfer.</span><span class="sxs-lookup"><span data-stu-id="89df9-108">[in] The size of the `pbApplicationPolicy` buffer.</span></span>  
  
 `pwzPostPolicyReferenceIdentity`  
 <span data-ttu-id="89df9-109">enuncia Referencia al ensamblado después de la evaluación de los nuevos datos de la Directiva.</span><span class="sxs-lookup"><span data-stu-id="89df9-109">[out] A reference to the assembly after the evaluation of the new policy data.</span></span>  
  
 `pcchPostPolicyReferenceIdentity`  
 <span data-ttu-id="89df9-110">[in, out] Puntero al tamaño del búfer de referencia de identidad del ensamblado después de la evaluación de los datos de la nueva Directiva.</span><span class="sxs-lookup"><span data-stu-id="89df9-110">[in, out] A pointer to the size of the assembly identity reference buffer after the evaluation of the new policy data.</span></span>  
  
 `pdwPoliciesApplied`  
 <span data-ttu-id="89df9-111">enuncia Puntero a una combinación lógica o de valores de [ebindpolicylevels (](ebindpolicylevels-enumeration.md) , que indica qué directivas se han aplicado.</span><span class="sxs-lookup"><span data-stu-id="89df9-111">[out] A pointer to a logical OR combination of [EBindPolicyLevels](ebindpolicylevels-enumeration.md) values, indicating which policies have been applied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="89df9-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="89df9-112">Return Value</span></span>  
  
|<span data-ttu-id="89df9-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="89df9-113">HRESULT</span></span>|<span data-ttu-id="89df9-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="89df9-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="89df9-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="89df9-115">S_OK</span></span>|<span data-ttu-id="89df9-116">La evaluación se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="89df9-116">The evaluation completed successfully.</span></span>|  
|<span data-ttu-id="89df9-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="89df9-117">E_INVALIDARG</span></span>|<span data-ttu-id="89df9-118">`pwzReferenceIdentity`O `pbApplicationPolicy` es una referencia nula.</span><span class="sxs-lookup"><span data-stu-id="89df9-118">Either `pwzReferenceIdentity` or `pbApplicationPolicy` is a null reference.</span></span>|  
|<span data-ttu-id="89df9-119">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="89df9-119">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="89df9-120">`cbAppPolicySize` es demasiado pequeño.</span><span class="sxs-lookup"><span data-stu-id="89df9-120">`cbAppPolicySize` is too small.</span></span>|  
|<span data-ttu-id="89df9-121">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="89df9-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="89df9-122">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="89df9-122">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="89df9-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="89df9-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="89df9-124">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="89df9-124">The call timed out.</span></span>|  
|<span data-ttu-id="89df9-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="89df9-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="89df9-126">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="89df9-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="89df9-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="89df9-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="89df9-128">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="89df9-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="89df9-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="89df9-129">E_FAIL</span></span>|<span data-ttu-id="89df9-130">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="89df9-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="89df9-131">Después de que un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="89df9-131">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="89df9-132">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="89df9-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="89df9-133">Observaciones</span><span class="sxs-lookup"><span data-stu-id="89df9-133">Remarks</span></span>  
 <span data-ttu-id="89df9-134">El `EvaluatePolicy` método permite al host influir en la Directiva de enlace para mantener los requisitos de control de versiones de ensamblado específicos del host.</span><span class="sxs-lookup"><span data-stu-id="89df9-134">The `EvaluatePolicy` method allows the host to influence binding policy to maintain host-specific assembly versioning requirements.</span></span> <span data-ttu-id="89df9-135">El propio motor de directivas permanece dentro de CLR.</span><span class="sxs-lookup"><span data-stu-id="89df9-135">The policy engine itself remains inside the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89df9-136">Requisitos</span><span class="sxs-lookup"><span data-stu-id="89df9-136">Requirements</span></span>  
 <span data-ttu-id="89df9-137">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89df9-137">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89df9-138">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="89df9-138">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="89df9-139">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="89df9-139">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="89df9-140">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89df9-140">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89df9-141">Consulta también</span><span class="sxs-lookup"><span data-stu-id="89df9-141">See also</span></span>

- [<span data-ttu-id="89df9-142">ICLRHostBindingPolicyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="89df9-142">ICLRHostBindingPolicyManager Interface</span></span>](iclrhostbindingpolicymanager-interface.md)
