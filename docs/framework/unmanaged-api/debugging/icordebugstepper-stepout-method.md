---
title: "ICorDebugStepper::StepOut (Método)"
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
- ICorDebugStepper.StepOut
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::StepOut
helpviewer_keywords:
- ICorDebugStepper::StepOut method [.NET Framework debugging]
- StepOut method [.NET Framework debugging]
ms.assetid: aae0f48c-4ede-4256-9251-a7fc85a229dc
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1d6462f166e9c734dacc7ebee13cb82e3b12158b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugstepperstepout-method"></a><span data-ttu-id="78d60-102">ICorDebugStepper::StepOut (Método)</span><span class="sxs-lookup"><span data-stu-id="78d60-102">ICorDebugStepper::StepOut Method</span></span>
<span data-ttu-id="78d60-103">Hace que esta ICorDebugStepper paso a paso a través de un subproceso que lo contiene y que finalice cuando el marco actual devuelve el control al marco que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="78d60-103">Causes this ICorDebugStepper to single-step through its containing thread, and to complete when the current frame returns control to the calling frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78d60-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="78d60-104">Syntax</span></span>  
  
```  
HRESULT StepOut ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="78d60-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="78d60-105">Remarks</span></span>  
 <span data-ttu-id="78d60-106">Un `StepOut` operación se completará después de devolver normalmente desde el marco actual al marco que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="78d60-106">A `StepOut` operation will complete after returning normally from the current frame to the calling frame.</span></span>  
  
 <span data-ttu-id="78d60-107">Si `StepOut` se llama cuando en código no administrado, el paso finalizará cuando el marco actual devuelve el código administrado que lo llamó.</span><span class="sxs-lookup"><span data-stu-id="78d60-107">If `StepOut` is called when in unmanaged code, the step will complete when the current frame returns to the managed code that called it.</span></span>  
  
 <span data-ttu-id="78d60-108">En la versión 2.0 de .NET Framework, no use `StepOut` con el STOP_UNMANAGED marca conjunto porque se producirá un error.</span><span class="sxs-lookup"><span data-stu-id="78d60-108">In the .NET Framework version 2.0, do not use `StepOut` with the STOP_UNMANAGED flag set because it will fail.</span></span> <span data-ttu-id="78d60-109">(Use [ICorDebugStepper:: SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) para establecer marcadores para la ejecución paso a paso.) Los depuradores de interoperabilidad deben salir del código nativo por sí mismos.</span><span class="sxs-lookup"><span data-stu-id="78d60-109">(Use [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) to set flags for stepping.) Interop debuggers must step out to native code themselves.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78d60-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="78d60-110">Requirements</span></span>  
 <span data-ttu-id="78d60-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="78d60-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78d60-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="78d60-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="78d60-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="78d60-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="78d60-114">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78d60-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
