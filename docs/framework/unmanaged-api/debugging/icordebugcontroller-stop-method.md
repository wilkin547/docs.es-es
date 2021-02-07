---
description: 'Más información acerca de: ICorDebugController:: STOP (método)'
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
ms.openlocfilehash: 613fd81a03114580ae3d826a94d855023895b694
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99764611"
---
# <a name="icordebugcontrollerstop-method"></a><span data-ttu-id="d0974-103">ICorDebugController::Stop (Método)</span><span class="sxs-lookup"><span data-stu-id="d0974-103">ICorDebugController::Stop Method</span></span>

<span data-ttu-id="d0974-104">Realiza una detención cooperativa en todos los subprocesos que ejecutan código administrado en el proceso.</span><span class="sxs-lookup"><span data-stu-id="d0974-104">Performs a cooperative stop on all threads that are running managed code in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0974-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d0974-105">Syntax</span></span>  
  
```cpp  
HRESULT Stop (  
    [in] DWORD dwTimeoutIgnored  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d0974-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d0974-106">Parameters</span></span>  

 `dwTimeoutIgnored`  
 <span data-ttu-id="d0974-107">No se usa.</span><span class="sxs-lookup"><span data-stu-id="d0974-107">Not used.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d0974-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d0974-108">Remarks</span></span>  

 <span data-ttu-id="d0974-109">`Stop` realiza una detención cooperativa en todos los subprocesos que ejecutan código administrado en el proceso.</span><span class="sxs-lookup"><span data-stu-id="d0974-109">`Stop` performs a cooperative stop on all threads running managed code in the process.</span></span> <span data-ttu-id="d0974-110">Durante una sesión de depuración solo administrada, los subprocesos no administrados pueden continuar ejecutándose (pero se bloquearán al intentar llamar al código administrado).</span><span class="sxs-lookup"><span data-stu-id="d0974-110">During a managed-only debugging session, unmanaged threads may continue to run (but will be blocked when trying to call managed code).</span></span> <span data-ttu-id="d0974-111">Durante una sesión de depuración de interoperabilidad, los subprocesos no administrados también se detendrán.</span><span class="sxs-lookup"><span data-stu-id="d0974-111">During an interop debugging session, unmanaged threads will also be stopped.</span></span> <span data-ttu-id="d0974-112">El `dwTimeoutIgnored` valor se omite actualmente y se trata como infinito (-1).</span><span class="sxs-lookup"><span data-stu-id="d0974-112">The `dwTimeoutIgnored` value is currently ignored and treated as INFINITE (-1).</span></span> <span data-ttu-id="d0974-113">Si se produce un error en la detención cooperativa debido a un interbloqueo, se suspenden todos los subprocesos y se devuelve E_TIMEOUT.</span><span class="sxs-lookup"><span data-stu-id="d0974-113">If the cooperative stop fails due to a deadlock, all threads are suspended and E_TIMEOUT is returned.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d0974-114">`Stop` es el único método sincrónico de la API de depuración.</span><span class="sxs-lookup"><span data-stu-id="d0974-114">`Stop` is the only synchronous method in the debugging API.</span></span> <span data-ttu-id="d0974-115">Cuando `Stop` devuelve S_OK, el proceso se detiene.</span><span class="sxs-lookup"><span data-stu-id="d0974-115">When `Stop` returns S_OK, the process is stopped.</span></span> <span data-ttu-id="d0974-116">No se proporciona ninguna devolución de llamada para notificar a los agentes de escucha de la detención.</span><span class="sxs-lookup"><span data-stu-id="d0974-116">No callback is given to notify listeners of the stop.</span></span> <span data-ttu-id="d0974-117">El depurador debe llamar a [ICorDebugController:: Continue](icordebugcontroller-continue-method.md) para permitir que se reanude el proceso.</span><span class="sxs-lookup"><span data-stu-id="d0974-117">The debugger must call [ICorDebugController::Continue](icordebugcontroller-continue-method.md) to allow the process to resume.</span></span>  
  
 <span data-ttu-id="d0974-118">El depurador mantiene un contador de detención.</span><span class="sxs-lookup"><span data-stu-id="d0974-118">The debugger maintains a stop counter.</span></span> <span data-ttu-id="d0974-119">Cuando el contador llega a cero, se reanuda el controlador.</span><span class="sxs-lookup"><span data-stu-id="d0974-119">When the counter goes to zero, the controller is resumed.</span></span> <span data-ttu-id="d0974-120">Cada llamada a `Stop` o a cada devolución de llamada enviada incrementa el contador.</span><span class="sxs-lookup"><span data-stu-id="d0974-120">Each call to `Stop` or each dispatched callback increments the counter.</span></span> <span data-ttu-id="d0974-121">Cada llamada a `ICorDebugController::Continue` disminuye el contador.</span><span class="sxs-lookup"><span data-stu-id="d0974-121">Each call to `ICorDebugController::Continue` decrements the counter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0974-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d0974-122">Requirements</span></span>  

 <span data-ttu-id="d0974-123">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d0974-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0974-124">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d0974-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d0974-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d0974-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d0974-126">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0974-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0974-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="d0974-127">See also</span></span>
