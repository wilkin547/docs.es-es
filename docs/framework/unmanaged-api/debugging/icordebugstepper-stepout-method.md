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
ms.openlocfilehash: 6c1d7db8aacaf81d47abd4a9cd972b44f56a3bb1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137520"
---
# <a name="icordebugstepperstepout-method"></a><span data-ttu-id="b6f80-102">ICorDebugStepper::StepOut (Método)</span><span class="sxs-lookup"><span data-stu-id="b6f80-102">ICorDebugStepper::StepOut Method</span></span>
<span data-ttu-id="b6f80-103">Hace que este objeto ICorDebugStepper tenga un solo paso a través de su subproceso contenedor y que se complete cuando el fotograma actual devuelva el control al marco que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="b6f80-103">Causes this ICorDebugStepper to single-step through its containing thread, and to complete when the current frame returns control to the calling frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6f80-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b6f80-104">Syntax</span></span>  
  
```cpp  
HRESULT StepOut ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="b6f80-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b6f80-105">Remarks</span></span>  
 <span data-ttu-id="b6f80-106">Una operación de `StepOut` se completará después de devolver normalmente del marco actual al marco que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="b6f80-106">A `StepOut` operation will complete after returning normally from the current frame to the calling frame.</span></span>  
  
 <span data-ttu-id="b6f80-107">Si se llama a `StepOut` en el código no administrado, el paso se completará cuando el fotograma actual vuelva al código administrado que lo llamó.</span><span class="sxs-lookup"><span data-stu-id="b6f80-107">If `StepOut` is called when in unmanaged code, the step will complete when the current frame returns to the managed code that called it.</span></span>  
  
 <span data-ttu-id="b6f80-108">En la versión .NET Framework 2,0, no use `StepOut` con la marca STOP_UNMANAGED establecida porque se producirá un error.</span><span class="sxs-lookup"><span data-stu-id="b6f80-108">In the .NET Framework version 2.0, do not use `StepOut` with the STOP_UNMANAGED flag set because it will fail.</span></span> <span data-ttu-id="b6f80-109">(Use [ICorDebugStepper:: setunmappedstopmask (](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) para establecer marcas para la ejecución paso a paso). Los depuradores de interoperabilidad deben salir del código nativo.</span><span class="sxs-lookup"><span data-stu-id="b6f80-109">(Use [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) to set flags for stepping.) Interop debuggers must step out to native code themselves.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6f80-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b6f80-110">Requirements</span></span>  
 <span data-ttu-id="b6f80-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b6f80-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6f80-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b6f80-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b6f80-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b6f80-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b6f80-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6f80-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
