---
description: 'Más información acerca de: ICorDebugController:: Setallthreadsdebugstate ((método)'
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
ms.openlocfilehash: 3bce5360833ae18c68bc8d7ea24f0dec7615f7a0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99710743"
---
# <a name="icordebugcontrollersetallthreadsdebugstate-method"></a><span data-ttu-id="0c760-103">ICorDebugController::SetAllThreadsDebugState (Método)</span><span class="sxs-lookup"><span data-stu-id="0c760-103">ICorDebugController::SetAllThreadsDebugState Method</span></span>

<span data-ttu-id="0c760-104">Establece el estado de depuración de todos los subprocesos administrados en el proceso.</span><span class="sxs-lookup"><span data-stu-id="0c760-104">Sets the debug state of all managed threads in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c760-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0c760-105">Syntax</span></span>  
  
```cpp  
HRESULT SetAllThreadsDebugState (  
    [in] CorDebugThreadState  state,  
    [in] ICorDebugThread      *pExceptThisThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c760-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0c760-106">Parameters</span></span>  

 `state`  
 <span data-ttu-id="0c760-107">de Un valor de la enumeración "CorDebugThreadState (" que especifica el estado del subproceso para la depuración.</span><span class="sxs-lookup"><span data-stu-id="0c760-107">[in] A value of the "CorDebugThreadState" enumeration that specifies the state of the thread for debugging.</span></span>  
  
 `pExceptThisThread`  
 <span data-ttu-id="0c760-108">de Un puntero a un objeto "ICorDebugThread" que representa un subproceso que se va a excluir de la configuración del estado de depuración.</span><span class="sxs-lookup"><span data-stu-id="0c760-108">[in] A pointer to an "ICorDebugThread" object that represents a thread to be exempted from the debug state setting.</span></span> <span data-ttu-id="0c760-109">Si este valor es null, no hay ningún subproceso exento.</span><span class="sxs-lookup"><span data-stu-id="0c760-109">If this value is null, no thread is exempted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0c760-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0c760-110">Remarks</span></span>  

 <span data-ttu-id="0c760-111">El `SetAllThreadsDebugState` método puede afectar a los subprocesos que no son visibles a través del [método enumeratethreads (](icordebugcontroller-enumeratethreads-method.md), por lo que los subprocesos que se suspendieron con el `SetAllThreadsDebugState` método deberán reanudarse con el `SetAllThreadsDebugState` método.</span><span class="sxs-lookup"><span data-stu-id="0c760-111">The `SetAllThreadsDebugState` method may affect threads that are not visible via [EnumerateThreads Method](icordebugcontroller-enumeratethreads-method.md), so threads that were suspended with the `SetAllThreadsDebugState` method will need to be resumed with the `SetAllThreadsDebugState` method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c760-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0c760-112">Requirements</span></span>  

 <span data-ttu-id="0c760-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0c760-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c760-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0c760-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0c760-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0c760-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0c760-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c760-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c760-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="0c760-117">See also</span></span>
