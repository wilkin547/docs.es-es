---
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
ms.openlocfilehash: 0a57dfe5bb4dfdc08a5e3f2238da6794e62bd958
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718285"
---
# <a name="icordebugstepperisactive-method"></a><span data-ttu-id="6c272-102">ICorDebugStepper::IsActive (Método)</span><span class="sxs-lookup"><span data-stu-id="6c272-102">ICorDebugStepper::IsActive Method</span></span>

<span data-ttu-id="6c272-103">Obtiene un valor que indica si esta ICorDebugStepper está ejecutando actualmente un paso.</span><span class="sxs-lookup"><span data-stu-id="6c272-103">Gets a value that indicates whether this ICorDebugStepper is currently executing a step.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c272-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6c272-104">Syntax</span></span>  
  
```cpp  
HRESULT IsActive (  
    [out] BOOL   *pbActive  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6c272-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6c272-105">Parameters</span></span>  

 `pbActive`  
 <span data-ttu-id="6c272-106">enuncia Devuelve `true` si el stepper está ejecutando actualmente un paso; de lo contrario, devuelve `false` .</span><span class="sxs-lookup"><span data-stu-id="6c272-106">[out] Returns `true` if the stepper is currently executing a step; otherwise, returns `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6c272-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6c272-107">Remarks</span></span>  

 <span data-ttu-id="6c272-108">Cualquier acción de paso permanece activa hasta que el depurador recibe una llamada [ICorDebugManagedCallback:: StepComplete (](icordebugmanagedcallback-stepcomplete-method.md) , que desactiva automáticamente el stepper.</span><span class="sxs-lookup"><span data-stu-id="6c272-108">Any step action remains active until the debugger receives a [ICorDebugManagedCallback::StepComplete](icordebugmanagedcallback-stepcomplete-method.md) call, which automatically deactivates the stepper.</span></span> <span data-ttu-id="6c272-109">Un stepper también se puede desactivar prematuramente si se llama a [ICorDebugStepper::D eactivate](icordebugstepper-deactivate-method.md) antes de que se alcance la condición de devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="6c272-109">A stepper may also be deactivated prematurely by calling [ICorDebugStepper::Deactivate](icordebugstepper-deactivate-method.md) before the callback condition is reached.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c272-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6c272-110">Requirements</span></span>  

 <span data-ttu-id="6c272-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6c272-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c272-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6c272-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6c272-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6c272-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6c272-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c272-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
