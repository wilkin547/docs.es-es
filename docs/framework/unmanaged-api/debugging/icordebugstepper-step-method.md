---
title: "ICorDebugStepper::Step (Método)"
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f921725d6794f08530a537462208264ced1dc089
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugstepperstep-method"></a><span data-ttu-id="97948-102">ICorDebugStepper::Step (Método)</span><span class="sxs-lookup"><span data-stu-id="97948-102">ICorDebugStepper::Step Method</span></span>
<span data-ttu-id="97948-103">Hace que esta instancia de ICorDebugStepper paso a paso a través de un subproceso que lo contiene y, opcionalmente, para seguir paso único a través de funciones que se llaman desde el subproceso.</span><span class="sxs-lookup"><span data-stu-id="97948-103">Causes this ICorDebugStepper to single-step through its containing thread, and optionally, to continue single-stepping through functions that are called within the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97948-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="97948-104">Syntax</span></span>  
  
```  
HRESULT Step (  
    [in] BOOL   bStepIn  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="97948-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="97948-105">Parameters</span></span>  
 `bStepIn`  
 <span data-ttu-id="97948-106">[in] Establecido en `true` para ir a una función que se llama desde el subproceso.</span><span class="sxs-lookup"><span data-stu-id="97948-106">[in] Set to `true` to step into a function that is called within the thread.</span></span> <span data-ttu-id="97948-107">Establecido en `false` para pasar por alto la función.</span><span class="sxs-lookup"><span data-stu-id="97948-107">Set to `false` to step over the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="97948-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="97948-108">Remarks</span></span>  
 <span data-ttu-id="97948-109">El paso finaliza cuando common language runtime ejecuta la siguiente instrucción administrada en el marco del este paso a paso desencadene.</span><span class="sxs-lookup"><span data-stu-id="97948-109">The step completes when the common language runtime performs the next managed instruction in this stepper's frame.</span></span> <span data-ttu-id="97948-110">Si `Step` es llamar en un paso a paso desencadene, que no está en código administrado, el paso finalizará cuando se ejecuta la siguiente instrucción de código administrado en el subproceso.</span><span class="sxs-lookup"><span data-stu-id="97948-110">If `Step` is called on a stepper, which is not in managed code, the step will complete when the next managed code instruction is executed by the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97948-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="97948-111">Requirements</span></span>  
 <span data-ttu-id="97948-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="97948-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97948-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="97948-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="97948-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="97948-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="97948-115">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97948-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
