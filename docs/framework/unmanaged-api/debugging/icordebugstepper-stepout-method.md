---
description: 'Más información acerca de: ICorDebugStepper:: Stepout ((método)'
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
ms.openlocfilehash: ef404c928ab711aef8032655a02cbd917416e806
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99717620"
---
# <a name="icordebugstepperstepout-method"></a><span data-ttu-id="4ba1b-103">ICorDebugStepper::StepOut (Método)</span><span class="sxs-lookup"><span data-stu-id="4ba1b-103">ICorDebugStepper::StepOut Method</span></span>

<span data-ttu-id="4ba1b-104">Hace que este objeto ICorDebugStepper tenga un solo paso a través de su subproceso contenedor y que se complete cuando el fotograma actual devuelva el control al marco que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="4ba1b-104">Causes this ICorDebugStepper to single-step through its containing thread, and to complete when the current frame returns control to the calling frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ba1b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4ba1b-105">Syntax</span></span>  
  
```cpp  
HRESULT StepOut ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="4ba1b-106">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4ba1b-106">Remarks</span></span>  

 <span data-ttu-id="4ba1b-107">Una `StepOut` operación se completará después de devolver normalmente del marco actual al marco que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="4ba1b-107">A `StepOut` operation will complete after returning normally from the current frame to the calling frame.</span></span>  
  
 <span data-ttu-id="4ba1b-108">Si `StepOut` se llama a en el código no administrado, el paso se completará cuando el fotograma actual vuelva al código administrado que lo llamó.</span><span class="sxs-lookup"><span data-stu-id="4ba1b-108">If `StepOut` is called when in unmanaged code, the step will complete when the current frame returns to the managed code that called it.</span></span>  
  
 <span data-ttu-id="4ba1b-109">En la versión .NET Framework 2,0, no use `StepOut` con la marca de STOP_UNMANAGED establecida porque se producirá un error.</span><span class="sxs-lookup"><span data-stu-id="4ba1b-109">In the .NET Framework version 2.0, do not use `StepOut` with the STOP_UNMANAGED flag set because it will fail.</span></span> <span data-ttu-id="4ba1b-110">(Use [ICorDebugStepper:: setunmappedstopmask (](icordebugstepper-setunmappedstopmask-method.md) para establecer marcas para la ejecución paso a paso). Los depuradores de interoperabilidad deben salir del código nativo.</span><span class="sxs-lookup"><span data-stu-id="4ba1b-110">(Use [ICorDebugStepper::SetUnmappedStopMask](icordebugstepper-setunmappedstopmask-method.md) to set flags for stepping.) Interop debuggers must step out to native code themselves.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ba1b-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4ba1b-111">Requirements</span></span>  

 <span data-ttu-id="4ba1b-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4ba1b-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ba1b-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4ba1b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4ba1b-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4ba1b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4ba1b-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ba1b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
