---
title: ICorDebugController::Continue (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugController.Continue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Continue
helpviewer_keywords:
- Continue method [.NET Framework debugging]
- ICorDebugController::Continue method [.NET Framework debugging]
ms.assetid: 8684cd06-ad3e-48ef-832e-15320e1f43a2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4f448a0383d3ad121cbddb59e13acef46a336261
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485738"
---
# <a name="icordebugcontrollercontinue-method"></a><span data-ttu-id="de1b1-102">ICorDebugController::Continue (Método)</span><span class="sxs-lookup"><span data-stu-id="de1b1-102">ICorDebugController::Continue Method</span></span>
<span data-ttu-id="de1b1-103">Reanuda la ejecución de subprocesos administrados después de llamar a [método Stop](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md).</span><span class="sxs-lookup"><span data-stu-id="de1b1-103">Resumes execution of managed threads after a call to [Stop Method](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de1b1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="de1b1-104">Syntax</span></span>  
  
```  
HRESULT Continue (  
    [in] BOOL fIsOutOfBand  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="de1b1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="de1b1-105">Parameters</span></span>  
 `fIsOutOfBand`  
 <span data-ttu-id="de1b1-106">[in] Establecido en `true` si continuar desde un evento fuera de banda; de lo contrario, se establece en `false`.</span><span class="sxs-lookup"><span data-stu-id="de1b1-106">[in] Set to `true` if continuing from an out-of-band event; otherwise, set to `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="de1b1-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="de1b1-107">Remarks</span></span>  
 <span data-ttu-id="de1b1-108">`Continue` Continúe con el proceso después de llamar a la `ICorDebugController::Stop` método.</span><span class="sxs-lookup"><span data-stu-id="de1b1-108">`Continue` continues the process after a call to the `ICorDebugController::Stop` method.</span></span>  
  
 <span data-ttu-id="de1b1-109">Cuando se realiza la depuración en modo mixto, no llame a `Continue` en Win32 eventos de subproceso a menos que sigue a un evento fuera de banda.</span><span class="sxs-lookup"><span data-stu-id="de1b1-109">When doing mixed-mode debugging, do not call `Continue` on the Win32 event thread unless you are continuing from an out-of-band event.</span></span>  
  
 <span data-ttu-id="de1b1-110">Un *eventos en banda* es un evento administrado o un evento no administrado normal durante el cual el depurador admite la interacción con el estado administrado del proceso.</span><span class="sxs-lookup"><span data-stu-id="de1b1-110">An *in-band event* is either a managed event or a normal unmanaged event during which the debugger supports interaction with the managed state of the process.</span></span> <span data-ttu-id="de1b1-111">En este caso, el depurador recibe la [ICorDebugUnmanagedCallback:: DebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-debugevent-method.md) devolución de llamada con su `fOutOfBand` parámetro establecido en `false`.</span><span class="sxs-lookup"><span data-stu-id="de1b1-111">In this case, the debugger receives the [ICorDebugUnmanagedCallback::DebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-debugevent-method.md) callback with its `fOutOfBand` parameter set to `false`.</span></span>  
  
 <span data-ttu-id="de1b1-112">Un *eventos fuera de banda* es un evento no administrado durante el cual la interacción con el estado administrado del proceso es imposible mientras el proceso se detiene debido al evento.</span><span class="sxs-lookup"><span data-stu-id="de1b1-112">An *out-of-band event* is an unmanaged event during which interaction with the managed state of the process is impossible while the process is stopped due to the event.</span></span> <span data-ttu-id="de1b1-113">En este caso, el depurador recibe la `ICorDebugUnmanagedCallback::DebugEvent` devolución de llamada con su `fOutOfBand` parámetro establecido en `true`.</span><span class="sxs-lookup"><span data-stu-id="de1b1-113">In this case, the debugger receives the `ICorDebugUnmanagedCallback::DebugEvent` callback with its `fOutOfBand` parameter set to `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de1b1-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="de1b1-114">Requirements</span></span>  
 <span data-ttu-id="de1b1-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="de1b1-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de1b1-116">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="de1b1-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="de1b1-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="de1b1-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="de1b1-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de1b1-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de1b1-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="de1b1-119">See also</span></span>

