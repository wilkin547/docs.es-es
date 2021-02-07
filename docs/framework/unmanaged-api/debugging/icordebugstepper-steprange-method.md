---
description: 'Más información acerca de: ICorDebugStepper:: Steprange ((método)'
title: ICorDebugStepper::StepRange (Método)
ms.date: 03/30/2017
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
ms.openlocfilehash: 868925ef301cca15b7887505e879f5fff02002e8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99717594"
---
# <a name="icordebugsteppersteprange-method"></a><span data-ttu-id="a5fa0-103">ICorDebugStepper::StepRange (Método)</span><span class="sxs-lookup"><span data-stu-id="a5fa0-103">ICorDebugStepper::StepRange Method</span></span>

<span data-ttu-id="a5fa0-104">Hace que este objeto ICorDebugStepper tenga un solo paso a través de su subproceso contenedor y que devuelva cuando llegue al código que se encuentra más allá del último de los intervalos especificados.</span><span class="sxs-lookup"><span data-stu-id="a5fa0-104">Causes this ICorDebugStepper to single-step through its containing thread, and to return when it reaches code beyond the last of the specified ranges.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5fa0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a5fa0-105">Syntax</span></span>  
  
```cpp  
HRESULT StepRange (  
    [in] BOOL     bStepIn,  
    [in, size_is(cRangeCount)] COR_DEBUG_STEP_RANGE ranges[],  
    [in] ULONG32  cRangeCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a5fa0-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a5fa0-106">Parameters</span></span>  

 `bStepIn`  
 <span data-ttu-id="a5fa0-107">de Establezca en `true` para entrar en una función a la que se llama en el subproceso.</span><span class="sxs-lookup"><span data-stu-id="a5fa0-107">[in] Set to `true` to step into a function that is called within the thread.</span></span> <span data-ttu-id="a5fa0-108">Establezca en `false` para recorrer la función.</span><span class="sxs-lookup"><span data-stu-id="a5fa0-108">Set to `false` to step over the function.</span></span>  
  
 `ranges`  
 <span data-ttu-id="a5fa0-109">de Matriz de estructuras de COR_DEBUG_STEP_RANGE, cada una de las cuales especifica un intervalo.</span><span class="sxs-lookup"><span data-stu-id="a5fa0-109">[in] An array of COR_DEBUG_STEP_RANGE structures, each of which specifies a range.</span></span>  
  
 `cRangeCount`  
 <span data-ttu-id="a5fa0-110">[in] Tamaño de la matriz `ranges`.</span><span class="sxs-lookup"><span data-stu-id="a5fa0-110">[in] The size of the `ranges` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a5fa0-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a5fa0-111">Remarks</span></span>  

 <span data-ttu-id="a5fa0-112">El `StepRange` método funciona como el método [ICorDebugStepper:: Step](icordebugstepper-step-method.md) , con la salvedad de que no se completa hasta que se alcanza el código fuera del intervalo especificado.</span><span class="sxs-lookup"><span data-stu-id="a5fa0-112">The `StepRange` method works like the [ICorDebugStepper::Step](icordebugstepper-step-method.md) method, except that it does not complete until code outside the given range is reached.</span></span>  
  
 <span data-ttu-id="a5fa0-113">Esto puede ser más eficaz que ejecutar una instrucción cada vez.</span><span class="sxs-lookup"><span data-stu-id="a5fa0-113">This can be more efficient than stepping one instruction at a time.</span></span> <span data-ttu-id="a5fa0-114">Los intervalos se especifican como una lista de pares de desplazamiento desde el inicio del marco del stepper.</span><span class="sxs-lookup"><span data-stu-id="a5fa0-114">Ranges are specified as a list of offset pairs from the start of the stepper's frame.</span></span>  
  
 <span data-ttu-id="a5fa0-115">Los intervalos son relativos al código del lenguaje intermedio de Microsoft (MSIL) de un método.</span><span class="sxs-lookup"><span data-stu-id="a5fa0-115">Ranges are relative to the Microsoft intermediate language (MSIL) code of a method.</span></span> <span data-ttu-id="a5fa0-116">Llame a [ICorDebugStepper:: SetRangeIL (](icordebugstepper-setrangeil-method.md) con `false` para que los intervalos sean relativos al código nativo de un método.</span><span class="sxs-lookup"><span data-stu-id="a5fa0-116">Call [ICorDebugStepper::SetRangeIL](icordebugstepper-setrangeil-method.md) with `false` to make the ranges relative to the native code of a method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5fa0-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a5fa0-117">Requirements</span></span>  

 <span data-ttu-id="a5fa0-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a5fa0-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5fa0-119">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a5fa0-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a5fa0-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a5fa0-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a5fa0-121">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5fa0-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
