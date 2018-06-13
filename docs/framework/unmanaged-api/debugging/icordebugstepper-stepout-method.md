---
title: ICorDebugStepper::StepOut (Método)
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f663f5134cf34bf9beb66da20bbb5886baff5415
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419171"
---
# <a name="icordebugstepperstepout-method"></a><span data-ttu-id="a6113-102">ICorDebugStepper::StepOut (Método)</span><span class="sxs-lookup"><span data-stu-id="a6113-102">ICorDebugStepper::StepOut Method</span></span>
<span data-ttu-id="a6113-103">Hace que esta ICorDebugStepper paso a paso a través de un subproceso que lo contiene y que finalice cuando el marco actual devuelve el control al marco que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="a6113-103">Causes this ICorDebugStepper to single-step through its containing thread, and to complete when the current frame returns control to the calling frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6113-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a6113-104">Syntax</span></span>  
  
```  
HRESULT StepOut ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="a6113-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a6113-105">Remarks</span></span>  
 <span data-ttu-id="a6113-106">Un `StepOut` operación se completará después de devolver normalmente desde el marco actual al marco que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="a6113-106">A `StepOut` operation will complete after returning normally from the current frame to the calling frame.</span></span>  
  
 <span data-ttu-id="a6113-107">Si `StepOut` se llama cuando en código no administrado, el paso finalizará cuando el marco actual devuelve el código administrado que lo llamó.</span><span class="sxs-lookup"><span data-stu-id="a6113-107">If `StepOut` is called when in unmanaged code, the step will complete when the current frame returns to the managed code that called it.</span></span>  
  
 <span data-ttu-id="a6113-108">En la versión 2.0 de .NET Framework, no use `StepOut` con el STOP_UNMANAGED marca conjunto porque se producirá un error.</span><span class="sxs-lookup"><span data-stu-id="a6113-108">In the .NET Framework version 2.0, do not use `StepOut` with the STOP_UNMANAGED flag set because it will fail.</span></span> <span data-ttu-id="a6113-109">(Use [ICorDebugStepper:: SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) para establecer marcadores para la ejecución paso a paso.) Los depuradores de interoperabilidad deben salir del código nativo por sí mismos.</span><span class="sxs-lookup"><span data-stu-id="a6113-109">(Use [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) to set flags for stepping.) Interop debuggers must step out to native code themselves.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6113-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a6113-110">Requirements</span></span>  
 <span data-ttu-id="a6113-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6113-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6113-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a6113-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a6113-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a6113-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a6113-114">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6113-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
