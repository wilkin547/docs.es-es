---
title: ICorDebugStepper::Step (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.Step
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::Step
helpviewer_keywords:
- Step method, ICorDebugStepper interface [.NET Framework debugging]
- ICorDebugStepper::Step method [.NET Framework debugging]
ms.assetid: 38c1940b-ada1-40ba-8295-4c0833744e1e
topic_type:
- apiref
ms.openlocfilehash: 39d2fd0163b0e61295187461d5dbdf5742450306
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379517"
---
# <a name="icordebugstepperstep-method"></a><span data-ttu-id="57186-102">ICorDebugStepper::Step (Método)</span><span class="sxs-lookup"><span data-stu-id="57186-102">ICorDebugStepper::Step Method</span></span>
<span data-ttu-id="57186-103">Hace que este objeto ICorDebugStepper tenga un solo paso a través de su subproceso contenedor y, opcionalmente, continúe con el paso a través de las funciones a las que se llama en el subproceso.</span><span class="sxs-lookup"><span data-stu-id="57186-103">Causes this ICorDebugStepper to single-step through its containing thread, and optionally, to continue single-stepping through functions that are called within the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57186-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="57186-104">Syntax</span></span>  
  
```cpp  
HRESULT Step (  
    [in] BOOL   bStepIn  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="57186-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="57186-105">Parameters</span></span>  
 `bStepIn`  
 <span data-ttu-id="57186-106">de Establezca en `true` para entrar en una función a la que se llama en el subproceso.</span><span class="sxs-lookup"><span data-stu-id="57186-106">[in] Set to `true` to step into a function that is called within the thread.</span></span> <span data-ttu-id="57186-107">Establezca en `false` para recorrer la función.</span><span class="sxs-lookup"><span data-stu-id="57186-107">Set to `false` to step over the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="57186-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="57186-108">Remarks</span></span>  
 <span data-ttu-id="57186-109">El paso se completa cuando el Common Language Runtime realiza la siguiente instrucción administrada en el marco de este stepper.</span><span class="sxs-lookup"><span data-stu-id="57186-109">The step completes when the common language runtime performs the next managed instruction in this stepper's frame.</span></span> <span data-ttu-id="57186-110">Si `Step` se llama a en un stepper, que no está en el código administrado, el paso se completará cuando el subproceso ejecute la siguiente instrucción de código administrado.</span><span class="sxs-lookup"><span data-stu-id="57186-110">If `Step` is called on a stepper, which is not in managed code, the step will complete when the next managed code instruction is executed by the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="57186-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="57186-111">Requirements</span></span>  
 <span data-ttu-id="57186-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="57186-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57186-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="57186-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="57186-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="57186-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="57186-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57186-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
