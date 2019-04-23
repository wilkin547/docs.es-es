---
title: ICorDebugManagedCallback::StepComplete (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.StepComplete
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::StepComplete
helpviewer_keywords:
- StepComplete method [.NET Framework debugging]
- ICorDebugManagedCallback::StepComplete method [.NET Framework debugging]
ms.assetid: 5e1f2c47-81df-4530-826d-96489cd68719
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fd784cb3322423e9309e8a5632822831b4e44cdf
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59184800"
---
# <a name="icordebugmanagedcallbackstepcomplete-method"></a><span data-ttu-id="be718-102">ICorDebugManagedCallback::StepComplete (Método)</span><span class="sxs-lookup"><span data-stu-id="be718-102">ICorDebugManagedCallback::StepComplete Method</span></span>
<span data-ttu-id="be718-103">Notifica al depurador que se ha completado un paso.</span><span class="sxs-lookup"><span data-stu-id="be718-103">Notifies the debugger that a step has completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be718-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="be718-104">Syntax</span></span>  
  
```  
HRESULT StepComplete (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugStepper    *pStepper,  
    [in] CorDebugStepReason   reason  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="be718-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="be718-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="be718-106">[in] Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene el subproceso en el que se ha completado el paso.</span><span class="sxs-lookup"><span data-stu-id="be718-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the thread in which the step has completed.</span></span>  
  
 `pThread`  
 <span data-ttu-id="be718-107">[in] Un puntero a un objeto ICorDebugThread que representa el subproceso en el que se ha completado el paso.</span><span class="sxs-lookup"><span data-stu-id="be718-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the step has completed.</span></span>  
  
 `pStepper`  
 <span data-ttu-id="be718-108">[in] Un puntero a un objeto ICorDebugStepper que representa el paso de ejecución de código.</span><span class="sxs-lookup"><span data-stu-id="be718-108">[in] A pointer to an ICorDebugStepper object that represents the step in code execution.</span></span>  
  
 `reason`  
 <span data-ttu-id="be718-109">[in] Un valor de la enumeración CorDebugStepReason que indica el resultado de un paso individual.</span><span class="sxs-lookup"><span data-stu-id="be718-109">[in] A value of the CorDebugStepReason enumeration that indicates the outcome of an individual step.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="be718-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="be718-110">Remarks</span></span>  
 <span data-ttu-id="be718-111">El componente puede utilizarse para continuar pasando si lo desea, a menos que se termina la depuración.</span><span class="sxs-lookup"><span data-stu-id="be718-111">The stepper may be used to continue stepping if desired, unless the debugging is terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be718-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="be718-112">Requirements</span></span>  
 <span data-ttu-id="be718-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="be718-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be718-114">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="be718-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="be718-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="be718-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="be718-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be718-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be718-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="be718-117">See also</span></span>

- [<span data-ttu-id="be718-118">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="be718-118">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
