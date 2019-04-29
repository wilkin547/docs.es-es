---
title: ICorDebugController::SetAllThreadsDebugState (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugController.SetAllThreadsDebugState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::SetAllThreadsDebugState
helpviewer_keywords:
- SetAllThreadsDebugState method [.NET Framework debugging]
- ICorDebugController::SetAllThreadsDebugState method [.NET Framework debugging]
ms.assetid: bdda4bd7-4743-4d58-a22b-8067e967db95
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 280dc3f0271d7326fe4c22b813abebfd4d45c89e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61749155"
---
# <a name="icordebugcontrollersetallthreadsdebugstate-method"></a><span data-ttu-id="c377c-102">ICorDebugController::SetAllThreadsDebugState (Método)</span><span class="sxs-lookup"><span data-stu-id="c377c-102">ICorDebugController::SetAllThreadsDebugState Method</span></span>
<span data-ttu-id="c377c-103">Establece el estado de depuración de todos los subprocesos administrados en el proceso.</span><span class="sxs-lookup"><span data-stu-id="c377c-103">Sets the debug state of all managed threads in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c377c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c377c-104">Syntax</span></span>  
  
```  
HRESULT SetAllThreadsDebugState (  
    [in] CorDebugThreadState  state,  
    [in] ICorDebugThread      *pExceptThisThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c377c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c377c-105">Parameters</span></span>  
 `state`  
 <span data-ttu-id="c377c-106">[in] Un valor de la enumeración "CorDebugThreadState" que especifica el estado del subproceso para la depuración.</span><span class="sxs-lookup"><span data-stu-id="c377c-106">[in] A value of the "CorDebugThreadState" enumeration that specifies the state of the thread for debugging.</span></span>  
  
 `pExceptThisThread`  
 <span data-ttu-id="c377c-107">[in] Un puntero a un objeto "ICorDebugThread" que representa un subproceso que se va a excluir de la configuración de estado de depuración.</span><span class="sxs-lookup"><span data-stu-id="c377c-107">[in] A pointer to an "ICorDebugThread" object that represents a thread to be exempted from the debug state setting.</span></span> <span data-ttu-id="c377c-108">Si este valor es null, no se excluye ningún subproceso.</span><span class="sxs-lookup"><span data-stu-id="c377c-108">If this value is null, no thread is exempted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c377c-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c377c-109">Remarks</span></span>  
 <span data-ttu-id="c377c-110">El `SetAllThreadsDebugState` método puede afectar a los subprocesos que no son visibles a través de [EnumerateThreads (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-enumeratethreads-method.md), así que los subprocesos suspendidos con el `SetAllThreadsDebugState` necesitará el método con el `SetAllThreadsDebugState` método.</span><span class="sxs-lookup"><span data-stu-id="c377c-110">The `SetAllThreadsDebugState` method may affect threads that are not visible via [EnumerateThreads Method](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-enumeratethreads-method.md), so threads that were suspended with the `SetAllThreadsDebugState` method will need to be resumed with the `SetAllThreadsDebugState` method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c377c-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c377c-111">Requirements</span></span>  
 <span data-ttu-id="c377c-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c377c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c377c-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c377c-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c377c-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c377c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c377c-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c377c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c377c-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="c377c-116">See also</span></span>
