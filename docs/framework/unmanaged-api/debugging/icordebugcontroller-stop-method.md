---
title: ICorDebugController::Stop (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugController.Stop
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Stop
helpviewer_keywords:
- Stop method, ICorDebugController interface [.NET Framework debugging]
- ICorDebugController::Stop method [.NET Framework debugging]
ms.assetid: c34e79be-a7fb-479e-8dec-d126a4c330e5
topic_type:
- apiref
ms.openlocfilehash: 3a107176e48a88a0a04534f7044c1e416caf4091
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788890"
---
# <a name="icordebugcontrollerstop-method"></a><span data-ttu-id="f7eef-102">ICorDebugController::Stop (Método)</span><span class="sxs-lookup"><span data-stu-id="f7eef-102">ICorDebugController::Stop Method</span></span>
<span data-ttu-id="f7eef-103">Realiza una detención cooperativa en todos los subprocesos que ejecutan código administrado en el proceso.</span><span class="sxs-lookup"><span data-stu-id="f7eef-103">Performs a cooperative stop on all threads that are running managed code in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7eef-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f7eef-104">Syntax</span></span>  
  
```cpp  
HRESULT Stop (  
    [in] DWORD dwTimeoutIgnored  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f7eef-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="f7eef-105">Parameters</span></span>  
 `dwTimeoutIgnored`  
 <span data-ttu-id="f7eef-106">No usado.</span><span class="sxs-lookup"><span data-stu-id="f7eef-106">Not used.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f7eef-107">Notas</span><span class="sxs-lookup"><span data-stu-id="f7eef-107">Remarks</span></span>  
 <span data-ttu-id="f7eef-108">`Stop` realiza una detención cooperativa en todos los subprocesos que ejecutan código administrado en el proceso.</span><span class="sxs-lookup"><span data-stu-id="f7eef-108">`Stop` performs a cooperative stop on all threads running managed code in the process.</span></span> <span data-ttu-id="f7eef-109">Durante una sesión de depuración solo administrada, los subprocesos no administrados pueden continuar ejecutándose (pero se bloquearán al intentar llamar al código administrado).</span><span class="sxs-lookup"><span data-stu-id="f7eef-109">During a managed-only debugging session, unmanaged threads may continue to run (but will be blocked when trying to call managed code).</span></span> <span data-ttu-id="f7eef-110">Durante una sesión de depuración de interoperabilidad, los subprocesos no administrados también se detendrán.</span><span class="sxs-lookup"><span data-stu-id="f7eef-110">During an interop debugging session, unmanaged threads will also be stopped.</span></span> <span data-ttu-id="f7eef-111">Actualmente, el valor `dwTimeoutIgnored` se omite y se trata como infinito (-1).</span><span class="sxs-lookup"><span data-stu-id="f7eef-111">The `dwTimeoutIgnored` value is currently ignored and treated as INFINITE (-1).</span></span> <span data-ttu-id="f7eef-112">Si se produce un error en la detención cooperativa debido a un interbloqueo, se suspenden todos los subprocesos y se devuelve E_TIMEOUT.</span><span class="sxs-lookup"><span data-stu-id="f7eef-112">If the cooperative stop fails due to a deadlock, all threads are suspended and E_TIMEOUT is returned.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f7eef-113">`Stop` es el único método sincrónico de la API de depuración.</span><span class="sxs-lookup"><span data-stu-id="f7eef-113">`Stop` is the only synchronous method in the debugging API.</span></span> <span data-ttu-id="f7eef-114">Cuando `Stop` Devuelve S_OK, el proceso se detiene.</span><span class="sxs-lookup"><span data-stu-id="f7eef-114">When `Stop` returns S_OK, the process is stopped.</span></span> <span data-ttu-id="f7eef-115">No se proporciona ninguna devolución de llamada para notificar a los agentes de escucha de la detención.</span><span class="sxs-lookup"><span data-stu-id="f7eef-115">No callback is given to notify listeners of the stop.</span></span> <span data-ttu-id="f7eef-116">El depurador debe llamar a [ICorDebugController:: Continue](icordebugcontroller-continue-method.md) para permitir que se reanude el proceso.</span><span class="sxs-lookup"><span data-stu-id="f7eef-116">The debugger must call [ICorDebugController::Continue](icordebugcontroller-continue-method.md) to allow the process to resume.</span></span>  
  
 <span data-ttu-id="f7eef-117">El depurador mantiene un contador de detención.</span><span class="sxs-lookup"><span data-stu-id="f7eef-117">The debugger maintains a stop counter.</span></span> <span data-ttu-id="f7eef-118">Cuando el contador llega a cero, se reanuda el controlador.</span><span class="sxs-lookup"><span data-stu-id="f7eef-118">When the counter goes to zero, the controller is resumed.</span></span> <span data-ttu-id="f7eef-119">Cada llamada a `Stop` o cada devolución de llamada enviada incrementa el contador.</span><span class="sxs-lookup"><span data-stu-id="f7eef-119">Each call to `Stop` or each dispatched callback increments the counter.</span></span> <span data-ttu-id="f7eef-120">Cada llamada a `ICorDebugController::Continue` disminuye el contador.</span><span class="sxs-lookup"><span data-stu-id="f7eef-120">Each call to `ICorDebugController::Continue` decrements the counter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7eef-121">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="f7eef-121">Requirements</span></span>  
 <span data-ttu-id="f7eef-122">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f7eef-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7eef-123">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f7eef-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f7eef-124">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f7eef-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f7eef-125">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7eef-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7eef-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="f7eef-126">See also</span></span>
