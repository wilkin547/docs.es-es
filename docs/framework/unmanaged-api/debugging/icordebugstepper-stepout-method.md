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
ms.openlocfilehash: 08cf2d0bb09080296fc1fcc69b5817f4d6118765
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791727"
---
# <a name="icordebugstepperstepout-method"></a><span data-ttu-id="e54e6-102">ICorDebugStepper::StepOut (Método)</span><span class="sxs-lookup"><span data-stu-id="e54e6-102">ICorDebugStepper::StepOut Method</span></span>
<span data-ttu-id="e54e6-103">Hace que este objeto ICorDebugStepper tenga un solo paso a través de su subproceso contenedor y que se complete cuando el fotograma actual devuelva el control al marco que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="e54e6-103">Causes this ICorDebugStepper to single-step through its containing thread, and to complete when the current frame returns control to the calling frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e54e6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e54e6-104">Syntax</span></span>  
  
```cpp  
HRESULT StepOut ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="e54e6-105">Notas</span><span class="sxs-lookup"><span data-stu-id="e54e6-105">Remarks</span></span>  
 <span data-ttu-id="e54e6-106">Una operación de `StepOut` se completará después de devolver normalmente del marco actual al marco que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="e54e6-106">A `StepOut` operation will complete after returning normally from the current frame to the calling frame.</span></span>  
  
 <span data-ttu-id="e54e6-107">Si se llama a `StepOut` en el código no administrado, el paso se completará cuando el fotograma actual vuelva al código administrado que lo llamó.</span><span class="sxs-lookup"><span data-stu-id="e54e6-107">If `StepOut` is called when in unmanaged code, the step will complete when the current frame returns to the managed code that called it.</span></span>  
  
 <span data-ttu-id="e54e6-108">En la versión .NET Framework 2,0, no use `StepOut` con la marca STOP_UNMANAGED establecida porque se producirá un error.</span><span class="sxs-lookup"><span data-stu-id="e54e6-108">In the .NET Framework version 2.0, do not use `StepOut` with the STOP_UNMANAGED flag set because it will fail.</span></span> <span data-ttu-id="e54e6-109">(Use [ICorDebugStepper:: setunmappedstopmask (](icordebugstepper-setunmappedstopmask-method.md) para establecer marcas para la ejecución paso a paso). Los depuradores de interoperabilidad deben salir del código nativo.</span><span class="sxs-lookup"><span data-stu-id="e54e6-109">(Use [ICorDebugStepper::SetUnmappedStopMask](icordebugstepper-setunmappedstopmask-method.md) to set flags for stepping.) Interop debuggers must step out to native code themselves.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e54e6-110">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="e54e6-110">Requirements</span></span>  
 <span data-ttu-id="e54e6-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e54e6-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e54e6-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e54e6-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e54e6-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e54e6-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e54e6-114">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e54e6-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
