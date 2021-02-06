---
description: 'Más información sobre: ICorDebugManagedCallback2:: Mdanotification ((método)'
title: ICorDebugManagedCallback2::MDANotification (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.MDANotification
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::MDANotification
helpviewer_keywords:
- MDANotification method [.NET Framework debugging]
- ICorDebugManagedCallback2::MDANotification method [.NET Framework debugging]
ms.assetid: 93f79627-bd31-4f4f-b95d-46a032a52fe4
topic_type:
- apiref
ms.openlocfilehash: 3f0c69c13ec30e604e07c284adca05f86283a5cd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99650500"
---
# <a name="icordebugmanagedcallback2mdanotification-method"></a><span data-ttu-id="b1af2-103">ICorDebugManagedCallback2::MDANotification (Método)</span><span class="sxs-lookup"><span data-stu-id="b1af2-103">ICorDebugManagedCallback2::MDANotification Method</span></span>

<span data-ttu-id="b1af2-104">Proporciona una notificación de que la ejecución del código ha encontrado un asistente para la depuración administrada (MDA) en la aplicación que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="b1af2-104">Provides notification that code execution has encountered a managed debugging assistant (MDA) in the application that is being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1af2-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b1af2-105">Syntax</span></span>  
  
```cpp  
HRESULT MDANotification(  
    [in] ICorDebugController  *pController,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugMDA         *pMDA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b1af2-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b1af2-106">Parameters</span></span>  

 `pController`  
 <span data-ttu-id="b1af2-107">de Puntero a una interfaz ICorDebugController que expone el proceso o dominio de aplicación en el que se produjo el MDA.</span><span class="sxs-lookup"><span data-stu-id="b1af2-107">[in] A pointer to an ICorDebugController interface that exposes the process or application domain in which the MDA occurred.</span></span>  
  
 <span data-ttu-id="b1af2-108">Un depurador no debe hacer ninguna suposición sobre si el controlador es un proceso o un dominio de aplicación, aunque siempre puede consultar la interfaz para realizar una determinación.</span><span class="sxs-lookup"><span data-stu-id="b1af2-108">A debugger should not make any assumptions about whether the controller is a process or an application domain, although it can always query the interface to make a determination.</span></span>  
  
 `pThread`  
 <span data-ttu-id="b1af2-109">de Puntero a una interfaz ICorDebugThread que expone el subproceso administrado en el que se produjo el evento de depuración.</span><span class="sxs-lookup"><span data-stu-id="b1af2-109">[in] A pointer to an ICorDebugThread interface that exposes the managed thread on which the debug event occurred.</span></span>  
  
 <span data-ttu-id="b1af2-110">Si el MDA se produjo en un subproceso no administrado, el valor de `pThread` será null.</span><span class="sxs-lookup"><span data-stu-id="b1af2-110">If the MDA occurred on an unmanaged thread, the value of `pThread` will be null.</span></span>  
  
 <span data-ttu-id="b1af2-111">Debe obtener el identificador del subproceso del sistema operativo (SO) del propio objeto MDA.</span><span class="sxs-lookup"><span data-stu-id="b1af2-111">You must get the operating system (OS) thread ID from the MDA object itself.</span></span>  
  
 `pMDA`  
 <span data-ttu-id="b1af2-112">de Puntero a una interfaz [ICorDebugMDA](icordebugmda-interface.md) que expone la información de MDA.</span><span class="sxs-lookup"><span data-stu-id="b1af2-112">[in] A pointer to an [ICorDebugMDA](icordebugmda-interface.md) interface that exposes the MDA information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b1af2-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b1af2-113">Remarks</span></span>  

 <span data-ttu-id="b1af2-114">Un MDA es una advertencia heurística y no requiere ninguna acción explícita del depurador, salvo llamar a [ICorDebugController:: Continue](icordebugcontroller-continue-method.md) para reanudar la ejecución de la aplicación que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="b1af2-114">An MDA is a heuristic warning and does not require any explicit debugger action except for calling [ICorDebugController::Continue](icordebugcontroller-continue-method.md) to resume execution of the application that is being debugged.</span></span>  
  
 <span data-ttu-id="b1af2-115">El Common Language Runtime (CLR) puede determinar qué MDA se activan y qué datos se encuentran en cualquier MDA determinado en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="b1af2-115">The common language runtime (CLR) can determine which MDAs are fired and which data is in any given MDA at any point.</span></span> <span data-ttu-id="b1af2-116">Por lo tanto, los depuradores no deben compilar ninguna funcionalidad que requiera patrones específicos de MDA.</span><span class="sxs-lookup"><span data-stu-id="b1af2-116">Therefore, debuggers should not build any functionality requiring specific MDA patterns.</span></span>  
  
 <span data-ttu-id="b1af2-117">Los MDA se pueden poner en cola y se activan poco después de encontrar el MDA.</span><span class="sxs-lookup"><span data-stu-id="b1af2-117">MDAs may be queued and fired shortly after the MDA is encountered.</span></span> <span data-ttu-id="b1af2-118">Esto puede ocurrir si el tiempo de ejecución necesita esperar hasta que alcanza un punto seguro para activar el MDA, en lugar de activar el MDA cuando lo encuentra.</span><span class="sxs-lookup"><span data-stu-id="b1af2-118">This could happen if the runtime needs to wait until it reaches a safe point for firing the MDA, instead of firing the MDA when it encounters it.</span></span> <span data-ttu-id="b1af2-119">También significa que el tiempo de ejecución puede activar varios MDA en un único conjunto de devoluciones de llamada en cola (similar a una operación de evento "Attach").</span><span class="sxs-lookup"><span data-stu-id="b1af2-119">It also means that the runtime may fire a number of MDAs in a single set of queued callbacks (similar to an "attach" event operation).</span></span>  
  
 <span data-ttu-id="b1af2-120">Un depurador debe liberar la referencia a una `ICorDebugMDA` instancia inmediatamente después de volver de la `MDANotification` devolución de llamada, para permitir que CLR recicle la memoria consumida por un MDA.</span><span class="sxs-lookup"><span data-stu-id="b1af2-120">A debugger should release the reference to an `ICorDebugMDA` instance immediately after returning from the `MDANotification` callback, to allow the CLR to recycle the memory consumed by an MDA.</span></span> <span data-ttu-id="b1af2-121">Liberar la instancia puede mejorar el rendimiento si se activan muchos MDA.</span><span class="sxs-lookup"><span data-stu-id="b1af2-121">Releasing the instance may improve performance if many MDAs are firing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1af2-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b1af2-122">Requirements</span></span>  

 <span data-ttu-id="b1af2-123">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b1af2-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1af2-124">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b1af2-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b1af2-125">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b1af2-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b1af2-126">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1af2-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1af2-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="b1af2-127">See also</span></span>

- [<span data-ttu-id="b1af2-128">Diagnóstico de errores con asistentes de depuraciones administradas</span><span class="sxs-lookup"><span data-stu-id="b1af2-128">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="b1af2-129">ICorDebugManagedCallback2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b1af2-129">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="b1af2-130">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b1af2-130">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
