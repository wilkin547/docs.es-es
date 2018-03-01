---
title: "ICorDebugStepper::IsActive (Método)"
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: dd919852d3e7c187dff7fc4304d0a1b42f5294e0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugstepperisactive-method"></a><span data-ttu-id="0e295-102">ICorDebugStepper::IsActive (Método)</span><span class="sxs-lookup"><span data-stu-id="0e295-102">ICorDebugStepper::IsActive Method</span></span>
<span data-ttu-id="0e295-103">Obtiene un valor que indica si esta instancia de ICorDebugStepper está ejecutando actualmente un paso.</span><span class="sxs-lookup"><span data-stu-id="0e295-103">Gets a value that indicates whether this ICorDebugStepper is currently executing a step.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e295-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0e295-104">Syntax</span></span>  
  
```  
HRESULT IsActive (  
    [out] BOOL   *pbActive  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0e295-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0e295-105">Parameters</span></span>  
 `pbActive`  
 <span data-ttu-id="0e295-106">[out] Devuelve `true` si el paso a paso desencadene se está ejecutando actualmente un paso; en caso contrario, devuelve `false`.</span><span class="sxs-lookup"><span data-stu-id="0e295-106">[out] Returns `true` if the stepper is currently executing a step; otherwise, returns `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0e295-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0e295-107">Remarks</span></span>  
 <span data-ttu-id="0e295-108">Cualquier acción de paso permanece activo hasta que el depurador recibe un [ICorDebugManagedCallback:: StepComplete](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md) llamar a, que automáticamente desactiva el paso a paso desencadene.</span><span class="sxs-lookup"><span data-stu-id="0e295-108">Any step action remains active until the debugger receives a [ICorDebugManagedCallback::StepComplete](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md) call, which automatically deactivates the stepper.</span></span> <span data-ttu-id="0e295-109">Un paso a paso desencadene también se puede desactivar prematuramente mediante una llamada a [ICorDebugStepper:: Deactivate](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-deactivate-method.md) antes de la devolución de llamada se alcanza la condición.</span><span class="sxs-lookup"><span data-stu-id="0e295-109">A stepper may also be deactivated prematurely by calling [ICorDebugStepper::Deactivate](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-deactivate-method.md) before the callback condition is reached.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e295-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0e295-110">Requirements</span></span>  
 <span data-ttu-id="0e295-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e295-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e295-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0e295-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0e295-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0e295-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0e295-114">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e295-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
