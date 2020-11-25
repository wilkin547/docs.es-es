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
ms.openlocfilehash: 8de0858abe7db9ae1225f449083e417e13507b3d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703062"
---
# <a name="icordebugmanagedcallbackstepcomplete-method"></a><span data-ttu-id="7ae14-102">ICorDebugManagedCallback::StepComplete (Método)</span><span class="sxs-lookup"><span data-stu-id="7ae14-102">ICorDebugManagedCallback::StepComplete Method</span></span>

<span data-ttu-id="7ae14-103">Notifica al depurador que se ha completado un paso.</span><span class="sxs-lookup"><span data-stu-id="7ae14-103">Notifies the debugger that a step has completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ae14-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7ae14-104">Syntax</span></span>  
  
```cpp  
HRESULT StepComplete (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugStepper    *pStepper,  
    [in] CorDebugStepReason   reason  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7ae14-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7ae14-105">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="7ae14-106">de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene el subproceso en el que se ha completado el paso.</span><span class="sxs-lookup"><span data-stu-id="7ae14-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the thread in which the step has completed.</span></span>  
  
 `pThread`  
 <span data-ttu-id="7ae14-107">de Un puntero a un objeto ICorDebugThread que representa el subproceso en el que se ha completado el paso.</span><span class="sxs-lookup"><span data-stu-id="7ae14-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the step has completed.</span></span>  
  
 `pStepper`  
 <span data-ttu-id="7ae14-108">de Un puntero a un objeto ICorDebugStepper que representa el paso en la ejecución del código.</span><span class="sxs-lookup"><span data-stu-id="7ae14-108">[in] A pointer to an ICorDebugStepper object that represents the step in code execution.</span></span>  
  
 `reason`  
 <span data-ttu-id="7ae14-109">de Un valor de la enumeración CorDebugStepReason (que indica el resultado de un paso individual.</span><span class="sxs-lookup"><span data-stu-id="7ae14-109">[in] A value of the CorDebugStepReason enumeration that indicates the outcome of an individual step.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7ae14-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7ae14-110">Remarks</span></span>  

 <span data-ttu-id="7ae14-111">Se puede usar el stepper para continuar con la ejecución paso a paso, a menos que se termine la depuración.</span><span class="sxs-lookup"><span data-stu-id="7ae14-111">The stepper may be used to continue stepping if desired, unless the debugging is terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ae14-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7ae14-112">Requirements</span></span>  

 <span data-ttu-id="7ae14-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ae14-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ae14-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7ae14-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7ae14-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7ae14-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7ae14-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ae14-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ae14-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7ae14-117">See also</span></span>

- [<span data-ttu-id="7ae14-118">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7ae14-118">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
