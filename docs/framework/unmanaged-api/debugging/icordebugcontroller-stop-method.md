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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 724db8c5c8dbb5bf3ff8bc7202a60397180b7b38
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59183396"
---
# <a name="icordebugcontrollerstop-method"></a><span data-ttu-id="49d05-102">ICorDebugController::Stop (Método)</span><span class="sxs-lookup"><span data-stu-id="49d05-102">ICorDebugController::Stop Method</span></span>
<span data-ttu-id="49d05-103">Realiza una detención cooperativa de todos los subprocesos que ejecutan código administrado en el proceso.</span><span class="sxs-lookup"><span data-stu-id="49d05-103">Performs a cooperative stop on all threads that are running managed code in the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49d05-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="49d05-104">Syntax</span></span>  
  
```  
HRESULT Stop (  
    [in] DWORD dwTimeoutIgnored  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="49d05-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="49d05-105">Parameters</span></span>  
 `dwTimeoutIgnored`  
 <span data-ttu-id="49d05-106">No se utiliza.</span><span class="sxs-lookup"><span data-stu-id="49d05-106">Not used.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="49d05-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="49d05-107">Remarks</span></span>  
 <span data-ttu-id="49d05-108">`Stop` realiza un código de detención cooperativa en todos los subprocesos en ejecución administrada en el proceso.</span><span class="sxs-lookup"><span data-stu-id="49d05-108">`Stop` performs a cooperative stop on all threads running managed code in the process.</span></span> <span data-ttu-id="49d05-109">Durante una sesión de depuración sólo administrada, pueden continuar ejecutando los subprocesos no administrados (pero se bloqueará al intentar llamar al código administrado).</span><span class="sxs-lookup"><span data-stu-id="49d05-109">During a managed-only debugging session, unmanaged threads may continue to run (but will be blocked when trying to call managed code).</span></span> <span data-ttu-id="49d05-110">Durante una sesión de depuración de interoperabilidad, también se detendrán los subprocesos no administrados.</span><span class="sxs-lookup"><span data-stu-id="49d05-110">During an interop debugging session, unmanaged threads will also be stopped.</span></span> <span data-ttu-id="49d05-111">El `dwTimeoutIgnored` valor actualmente se omite y se tratan como infinito (-1).</span><span class="sxs-lookup"><span data-stu-id="49d05-111">The `dwTimeoutIgnored` value is currently ignored and treated as INFINITE (-1).</span></span> <span data-ttu-id="49d05-112">Si se produce un error en la detención cooperativa debido a un interbloqueo, se suspenden todos los subprocesos y se devuelve E_TIMEOUT.</span><span class="sxs-lookup"><span data-stu-id="49d05-112">If the cooperative stop fails due to a deadlock, all threads are suspended and E_TIMEOUT is returned.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="49d05-113">`Stop` es el único método sincrónico de la API de depuración.</span><span class="sxs-lookup"><span data-stu-id="49d05-113">`Stop` is the only synchronous method in the debugging API.</span></span> <span data-ttu-id="49d05-114">Cuando `Stop` devuelve S_OK, el proceso se detiene.</span><span class="sxs-lookup"><span data-stu-id="49d05-114">When `Stop` returns S_OK, the process is stopped.</span></span> <span data-ttu-id="49d05-115">No se proporciona ninguna devolución de llamada para notificar a los agentes de escucha de la detención.</span><span class="sxs-lookup"><span data-stu-id="49d05-115">No callback is given to notify listeners of the stop.</span></span> <span data-ttu-id="49d05-116">El depurador debe llamar a [ICorDebugController](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) para permitir la reanudación del proceso.</span><span class="sxs-lookup"><span data-stu-id="49d05-116">The debugger must call [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) to allow the process to resume.</span></span>  
  
 <span data-ttu-id="49d05-117">El depurador mantiene un contador de detención.</span><span class="sxs-lookup"><span data-stu-id="49d05-117">The debugger maintains a stop counter.</span></span> <span data-ttu-id="49d05-118">Cuando el contador llega a cero, se reanuda el controlador.</span><span class="sxs-lookup"><span data-stu-id="49d05-118">When the counter goes to zero, the controller is resumed.</span></span> <span data-ttu-id="49d05-119">Cada llamada a `Stop` o cada devolución de llamada enviada incrementa el contador.</span><span class="sxs-lookup"><span data-stu-id="49d05-119">Each call to `Stop` or each dispatched callback increments the counter.</span></span> <span data-ttu-id="49d05-120">Cada llamada a `ICorDebugController::Continue` disminuye el contador.</span><span class="sxs-lookup"><span data-stu-id="49d05-120">Each call to `ICorDebugController::Continue` decrements the counter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49d05-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="49d05-121">Requirements</span></span>  
 <span data-ttu-id="49d05-122">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49d05-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49d05-123">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="49d05-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="49d05-124">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="49d05-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="49d05-125">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49d05-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49d05-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="49d05-126">See also</span></span>
