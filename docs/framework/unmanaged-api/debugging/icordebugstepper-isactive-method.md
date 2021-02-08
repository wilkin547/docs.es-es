---
description: 'Más información acerca de: ICorDebugStepper:: IsActive (método)'
title: ICorDebugStepper::IsActive (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.IsActive
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::IsActive
helpviewer_keywords:
- IsActive method, ICorDebugStepper interface [.NET Framework debugging]
- ICorDebugStepper::IsActive method [.NET Framework debugging]
ms.assetid: 8b35e7a9-b40e-40a9-8d8e-b82e823fc575
topic_type:
- apiref
ms.openlocfilehash: 7ef937ac3c1e6f3ad9ad83b5fa84382cac3ac9c1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803573"
---
# <a name="icordebugstepperisactive-method"></a><span data-ttu-id="e32ac-103">ICorDebugStepper::IsActive (Método)</span><span class="sxs-lookup"><span data-stu-id="e32ac-103">ICorDebugStepper::IsActive Method</span></span>

<span data-ttu-id="e32ac-104">Obtiene un valor que indica si esta ICorDebugStepper está ejecutando actualmente un paso.</span><span class="sxs-lookup"><span data-stu-id="e32ac-104">Gets a value that indicates whether this ICorDebugStepper is currently executing a step.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e32ac-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e32ac-105">Syntax</span></span>  
  
```cpp  
HRESULT IsActive (  
    [out] BOOL   *pbActive  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e32ac-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e32ac-106">Parameters</span></span>  

 `pbActive`  
 <span data-ttu-id="e32ac-107">enuncia Devuelve `true` si el stepper está ejecutando actualmente un paso; de lo contrario, devuelve `false` .</span><span class="sxs-lookup"><span data-stu-id="e32ac-107">[out] Returns `true` if the stepper is currently executing a step; otherwise, returns `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e32ac-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e32ac-108">Remarks</span></span>  

 <span data-ttu-id="e32ac-109">Cualquier acción de paso permanece activa hasta que el depurador recibe una llamada [ICorDebugManagedCallback:: StepComplete (](icordebugmanagedcallback-stepcomplete-method.md) , que desactiva automáticamente el stepper.</span><span class="sxs-lookup"><span data-stu-id="e32ac-109">Any step action remains active until the debugger receives a [ICorDebugManagedCallback::StepComplete](icordebugmanagedcallback-stepcomplete-method.md) call, which automatically deactivates the stepper.</span></span> <span data-ttu-id="e32ac-110">Un stepper también se puede desactivar prematuramente si se llama a [ICorDebugStepper::D eactivate](icordebugstepper-deactivate-method.md) antes de que se alcance la condición de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="e32ac-110">A stepper may also be deactivated prematurely by calling [ICorDebugStepper::Deactivate](icordebugstepper-deactivate-method.md) before the callback condition is reached.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e32ac-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e32ac-111">Requirements</span></span>  

 <span data-ttu-id="e32ac-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e32ac-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e32ac-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e32ac-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e32ac-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e32ac-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e32ac-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e32ac-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
