---
description: 'Más información acerca de: ICorDebugManagedCallback:: StepComplete ((método)'
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
ms.openlocfilehash: 653abee26f09ac8877be9fa4183763739845666a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99660367"
---
# <a name="icordebugmanagedcallbackstepcomplete-method"></a><span data-ttu-id="85f51-103">ICorDebugManagedCallback::StepComplete (Método)</span><span class="sxs-lookup"><span data-stu-id="85f51-103">ICorDebugManagedCallback::StepComplete Method</span></span>

<span data-ttu-id="85f51-104">Notifica al depurador que se ha completado un paso.</span><span class="sxs-lookup"><span data-stu-id="85f51-104">Notifies the debugger that a step has completed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85f51-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="85f51-105">Syntax</span></span>  
  
```cpp  
HRESULT StepComplete (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugStepper    *pStepper,  
    [in] CorDebugStepReason   reason  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="85f51-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="85f51-106">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="85f51-107">de Un puntero a un objeto ICorDebugAppDomain que representa el dominio de aplicación que contiene el subproceso en el que se ha completado el paso.</span><span class="sxs-lookup"><span data-stu-id="85f51-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the thread in which the step has completed.</span></span>  
  
 `pThread`  
 <span data-ttu-id="85f51-108">de Un puntero a un objeto ICorDebugThread que representa el subproceso en el que se ha completado el paso.</span><span class="sxs-lookup"><span data-stu-id="85f51-108">[in] A pointer to an ICorDebugThread object that represents the thread in which the step has completed.</span></span>  
  
 `pStepper`  
 <span data-ttu-id="85f51-109">de Un puntero a un objeto ICorDebugStepper que representa el paso en la ejecución del código.</span><span class="sxs-lookup"><span data-stu-id="85f51-109">[in] A pointer to an ICorDebugStepper object that represents the step in code execution.</span></span>  
  
 `reason`  
 <span data-ttu-id="85f51-110">de Un valor de la enumeración CorDebugStepReason (que indica el resultado de un paso individual.</span><span class="sxs-lookup"><span data-stu-id="85f51-110">[in] A value of the CorDebugStepReason enumeration that indicates the outcome of an individual step.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="85f51-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="85f51-111">Remarks</span></span>  

 <span data-ttu-id="85f51-112">Se puede usar el stepper para continuar con la ejecución paso a paso, a menos que se termine la depuración.</span><span class="sxs-lookup"><span data-stu-id="85f51-112">The stepper may be used to continue stepping if desired, unless the debugging is terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85f51-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="85f51-113">Requirements</span></span>  

 <span data-ttu-id="85f51-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="85f51-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85f51-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="85f51-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="85f51-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="85f51-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="85f51-117">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85f51-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85f51-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="85f51-118">See also</span></span>

- [<span data-ttu-id="85f51-119">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="85f51-119">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
