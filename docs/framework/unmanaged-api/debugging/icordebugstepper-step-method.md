---
description: 'Más información acerca de: ICorDebugStepper:: Step (método)'
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
ms.openlocfilehash: cb45575f7818784addf67eacda35442764e706af
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99717633"
---
# <a name="icordebugstepperstep-method"></a><span data-ttu-id="10a6b-103">ICorDebugStepper::Step (Método)</span><span class="sxs-lookup"><span data-stu-id="10a6b-103">ICorDebugStepper::Step Method</span></span>

<span data-ttu-id="10a6b-104">Hace que este objeto ICorDebugStepper tenga un solo paso a través de su subproceso contenedor y, opcionalmente, continúe con el paso a través de las funciones a las que se llama en el subproceso.</span><span class="sxs-lookup"><span data-stu-id="10a6b-104">Causes this ICorDebugStepper to single-step through its containing thread, and optionally, to continue single-stepping through functions that are called within the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10a6b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="10a6b-105">Syntax</span></span>  
  
```cpp  
HRESULT Step (  
    [in] BOOL   bStepIn  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="10a6b-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="10a6b-106">Parameters</span></span>  

 `bStepIn`  
 <span data-ttu-id="10a6b-107">de Establezca en `true` para entrar en una función a la que se llama en el subproceso.</span><span class="sxs-lookup"><span data-stu-id="10a6b-107">[in] Set to `true` to step into a function that is called within the thread.</span></span> <span data-ttu-id="10a6b-108">Establezca en `false` para recorrer la función.</span><span class="sxs-lookup"><span data-stu-id="10a6b-108">Set to `false` to step over the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="10a6b-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="10a6b-109">Remarks</span></span>  

 <span data-ttu-id="10a6b-110">El paso se completa cuando el Common Language Runtime realiza la siguiente instrucción administrada en el marco de este stepper.</span><span class="sxs-lookup"><span data-stu-id="10a6b-110">The step completes when the common language runtime performs the next managed instruction in this stepper's frame.</span></span> <span data-ttu-id="10a6b-111">Si `Step` se llama a en un stepper, que no está en el código administrado, el paso se completará cuando el subproceso ejecute la siguiente instrucción de código administrado.</span><span class="sxs-lookup"><span data-stu-id="10a6b-111">If `Step` is called on a stepper, which is not in managed code, the step will complete when the next managed code instruction is executed by the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10a6b-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="10a6b-112">Requirements</span></span>  

 <span data-ttu-id="10a6b-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10a6b-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10a6b-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="10a6b-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="10a6b-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="10a6b-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="10a6b-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10a6b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
