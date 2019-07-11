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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9dde27f74ac59d033b6e25fba1dbb8e52c4b91af
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760680"
---
# <a name="icordebugstepperisactive-method"></a><span data-ttu-id="e68c2-102">ICorDebugStepper::IsActive (Método)</span><span class="sxs-lookup"><span data-stu-id="e68c2-102">ICorDebugStepper::IsActive Method</span></span>
<span data-ttu-id="e68c2-103">Obtiene un valor que indica si esta instancia de ICorDebugStepper está ejecutando actualmente un paso.</span><span class="sxs-lookup"><span data-stu-id="e68c2-103">Gets a value that indicates whether this ICorDebugStepper is currently executing a step.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e68c2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e68c2-104">Syntax</span></span>  
  
```cpp  
HRESULT IsActive (  
    [out] BOOL   *pbActive  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e68c2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e68c2-105">Parameters</span></span>  
 `pbActive`  
 <span data-ttu-id="e68c2-106">[out] Devuelve `true` si el componente se está ejecutando actualmente un paso; de lo contrario, devuelve `false`.</span><span class="sxs-lookup"><span data-stu-id="e68c2-106">[out] Returns `true` if the stepper is currently executing a step; otherwise, returns `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e68c2-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e68c2-107">Remarks</span></span>  
 <span data-ttu-id="e68c2-108">Cualquier acción paso permanece activa hasta que el depurador recibe un [StepComplete](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md) llamar, que desactiva automáticamente el motor paso a paso.</span><span class="sxs-lookup"><span data-stu-id="e68c2-108">Any step action remains active until the debugger receives a [ICorDebugManagedCallback::StepComplete](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md) call, which automatically deactivates the stepper.</span></span> <span data-ttu-id="e68c2-109">Un motor paso a paso también se puede desactivar prematuramente mediante una llamada a [ICorDebugStepper](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-deactivate-method.md) antes de la devolución de llamada se alcanza la condición.</span><span class="sxs-lookup"><span data-stu-id="e68c2-109">A stepper may also be deactivated prematurely by calling [ICorDebugStepper::Deactivate](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-deactivate-method.md) before the callback condition is reached.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e68c2-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e68c2-110">Requirements</span></span>  
 <span data-ttu-id="e68c2-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e68c2-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e68c2-112">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e68c2-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e68c2-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e68c2-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e68c2-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e68c2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
