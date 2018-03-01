---
title: "ICorDebugStepper::StepRange (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugStepper.StepRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::StepRange
helpviewer_keywords:
- StepRange method [.NET Framework debugging]
- ICorDebugStepper::StepRange method [.NET Framework debugging]
ms.assetid: b9776112-6e6d-4708-892a-8873db02e16f
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a02efe1b701506cc3de695c5b79d5e9c84b25b8f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugsteppersteprange-method"></a><span data-ttu-id="ff566-102">ICorDebugStepper::StepRange (Método)</span><span class="sxs-lookup"><span data-stu-id="ff566-102">ICorDebugStepper::StepRange Method</span></span>
<span data-ttu-id="ff566-103">Hace que esta instancia de ICorDebugStepper paso a paso a través de un subproceso que lo contiene y que se devolverán cuando llegue al código situado más allá del último de los intervalos especificados.</span><span class="sxs-lookup"><span data-stu-id="ff566-103">Causes this ICorDebugStepper to single-step through its containing thread, and to return when it reaches code beyond the last of the specified ranges.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff566-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ff566-104">Syntax</span></span>  
  
```  
HRESULT StepRange (  
    [in] BOOL     bStepIn,  
    [in, size_is(cRangeCount)] COR_DEBUG_STEP_RANGE ranges[],  
    [in] ULONG32  cRangeCount  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ff566-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ff566-105">Parameters</span></span>  
 `bStepIn`  
 <span data-ttu-id="ff566-106">[in] Establecido en `true` para ir a una función que se llama desde el subproceso.</span><span class="sxs-lookup"><span data-stu-id="ff566-106">[in] Set to `true` to step into a function that is called within the thread.</span></span> <span data-ttu-id="ff566-107">Establecido en `false` para pasar por alto la función.</span><span class="sxs-lookup"><span data-stu-id="ff566-107">Set to `false` to step over the function.</span></span>  
  
 `ranges`  
 <span data-ttu-id="ff566-108">[in] Una matriz de estructuras COR_DEBUG_STEP_RANGE, cada uno de los cuales especifica un intervalo.</span><span class="sxs-lookup"><span data-stu-id="ff566-108">[in] An array of COR_DEBUG_STEP_RANGE structures, each of which specifies a range.</span></span>  
  
 `cRangeCount`  
 <span data-ttu-id="ff566-109">[in] Tamaño de la matriz `ranges`.</span><span class="sxs-lookup"><span data-stu-id="ff566-109">[in] The size of the `ranges` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ff566-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ff566-110">Remarks</span></span>  
 <span data-ttu-id="ff566-111">El `StepRange` método funciona como el [ICorDebugStepper:: Step](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-step-method.md) método, salvo que no se completa hasta que el código fuera del intervalo especificado se ha alcanzado.</span><span class="sxs-lookup"><span data-stu-id="ff566-111">The `StepRange` method works like the [ICorDebugStepper::Step](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-step-method.md) method, except that it does not complete until code outside the given range is reached.</span></span>  
  
 <span data-ttu-id="ff566-112">Esto puede ser más eficaz que la ejecución paso a paso una instrucción a la vez.</span><span class="sxs-lookup"><span data-stu-id="ff566-112">This can be more efficient than stepping one instruction at a time.</span></span> <span data-ttu-id="ff566-113">Los intervalos se especifican como una lista de pares de desplazamiento desde el inicio del marco del paso a paso de desencadene.</span><span class="sxs-lookup"><span data-stu-id="ff566-113">Ranges are specified as a list of offset pairs from the start of the stepper's frame.</span></span>  
  
 <span data-ttu-id="ff566-114">Los intervalos son relativos al código de lenguaje intermedio (MSIL) de Microsoft de un método.</span><span class="sxs-lookup"><span data-stu-id="ff566-114">Ranges are relative to the Microsoft intermediate language (MSIL) code of a method.</span></span> <span data-ttu-id="ff566-115">Llame a [ICorDebugStepper:: SetRangeIL](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setrangeil-method.md) con `false` para hacer que los intervalos relativos al código nativo de un método.</span><span class="sxs-lookup"><span data-stu-id="ff566-115">Call [ICorDebugStepper::SetRangeIL](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setrangeil-method.md) with `false` to make the ranges relative to the native code of a method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff566-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ff566-116">Requirements</span></span>  
 <span data-ttu-id="ff566-117">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff566-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff566-118">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ff566-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ff566-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ff566-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ff566-120">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff566-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
