---
description: 'Más información sobre: enumeración CorDebugUserState ('
title: CorDebugUserState (Enumeración)
ms.date: 03/30/2017
api_name:
- CorDebugUserState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugUserState
helpviewer_keywords:
- CorDebugUserState enumeration [.NET Framework debugging]
ms.assetid: 5f6c2bcd-8102-4e3b-abc5-86ab0bd62def
topic_type:
- apiref
ms.openlocfilehash: c556e7943751fb8e159e3e0d0b9a71baf1f6b5b5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99661745"
---
# <a name="cordebuguserstate-enumeration"></a><span data-ttu-id="8453a-103">CorDebugUserState (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="8453a-103">CorDebugUserState Enumeration</span></span>

<span data-ttu-id="8453a-104">Indica el estado de uso de un subproceso.</span><span class="sxs-lookup"><span data-stu-id="8453a-104">Indicates the user state of a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8453a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8453a-105">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugUserState {  
    USER_STOP_REQUESTED     =  0x01,  
    USER_SUSPEND_REQUESTED  =  0x02,  
    USER_BACKGROUND         =  0x04,  
    USER_UNSTARTED          =  0x08,  
    USER_STOPPED            =  0x10,  
    USER_WAIT_SLEEP_JOIN    =  0x20,  
    USER_SUSPENDED          =  0x40,  
    USER_UNSAFE_POINT       =  0x80,  
    USER_THREADPOOL         = 0x100  
} CorDebugUserState;  
```  
  
## <a name="members"></a><span data-ttu-id="8453a-106">Members</span><span class="sxs-lookup"><span data-stu-id="8453a-106">Members</span></span>  
  
|<span data-ttu-id="8453a-107">Value</span><span class="sxs-lookup"><span data-stu-id="8453a-107">Value</span></span>|<span data-ttu-id="8453a-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="8453a-108">Description</span></span>|  
|-----------|-----------------|  
|`USER_STOP_REQUESTED`|<span data-ttu-id="8453a-109">Se ha solicitado una terminación del subproceso.</span><span class="sxs-lookup"><span data-stu-id="8453a-109">A termination of the thread has been requested.</span></span>|  
|`USER_SUSPEND_REQUESTED`|<span data-ttu-id="8453a-110">Se ha solicitado una suspensión del subproceso.</span><span class="sxs-lookup"><span data-stu-id="8453a-110">A suspension of the thread has been requested.</span></span>|  
|`USER_BACKGROUND`|<span data-ttu-id="8453a-111">El subproceso se ejecuta en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="8453a-111">The thread is running in the background.</span></span>|  
|`USER_UNSTARTED`|<span data-ttu-id="8453a-112">El subproceso no ha empezado a ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="8453a-112">The thread has not started executing.</span></span>|  
|`USER_STOPPED`|<span data-ttu-id="8453a-113">El subproceso ha finalizado.</span><span class="sxs-lookup"><span data-stu-id="8453a-113">The thread has been terminated.</span></span>|  
|`USER_WAIT_SLEEP_JOIN`|<span data-ttu-id="8453a-114">El subproceso está esperando a que otro subproceso complete una tarea.</span><span class="sxs-lookup"><span data-stu-id="8453a-114">The thread is waiting for another thread to complete a task.</span></span>|  
|`USER_SUSPENDED`|<span data-ttu-id="8453a-115">El subproceso se ha suspendido.</span><span class="sxs-lookup"><span data-stu-id="8453a-115">The thread has been suspended.</span></span>|  
|`USER_UNSAFE_POINT`|<span data-ttu-id="8453a-116">El subproceso está en un punto no seguro.</span><span class="sxs-lookup"><span data-stu-id="8453a-116">The thread is at an unsafe point.</span></span> <span data-ttu-id="8453a-117">Es decir, el subproceso está en un punto de la ejecución donde puede bloquear la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="8453a-117">That is, the thread is at a point in execution where it may block garbage collection.</span></span><br /><br /> <span data-ttu-id="8453a-118">Los eventos de depuración se pueden enviar desde puntos no seguros, pero si se suspende un subproceso en un punto no seguro, es muy probable que se produzca un interbloqueo hasta que se reanude el subproceso.</span><span class="sxs-lookup"><span data-stu-id="8453a-118">Debug events may be dispatched from unsafe points, but suspending a thread at an unsafe point  will very likely cause a deadlock until the thread is resumed.</span></span> <span data-ttu-id="8453a-119">Los puntos Safe y Unsafe se determinan mediante la implementación Just-in-Time (JIT) y la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="8453a-119">The safe and unsafe points are determined by the just-in-time (JIT) and garbage collection implementation.</span></span>|  
|`USER_THREADPOOL`|<span data-ttu-id="8453a-120">El subproceso procede del grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="8453a-120">The thread is from the thread pool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8453a-121">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8453a-121">Remarks</span></span>  

 <span data-ttu-id="8453a-122">El estado de usuario de un subproceso es el estado que tiene el subproceso cuando el depurador lo examina.</span><span class="sxs-lookup"><span data-stu-id="8453a-122">The user state of a thread is the state that the thread has when the debugger examines it.</span></span> <span data-ttu-id="8453a-123">Un subproceso puede tener una combinación de Estados de usuario.</span><span class="sxs-lookup"><span data-stu-id="8453a-123">A thread may have a combination of user states.</span></span>  
  
 <span data-ttu-id="8453a-124">Use el método [ICorDebugThread:: getuserstate (](icordebugthread-getuserstate-method.md) para recuperar el estado de usuario de un subproceso.</span><span class="sxs-lookup"><span data-stu-id="8453a-124">Use the [ICorDebugThread::GetUserState](icordebugthread-getuserstate-method.md) method to retrieve a thread's user state.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8453a-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8453a-125">Requirements</span></span>  

 <span data-ttu-id="8453a-126">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8453a-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8453a-127">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8453a-127">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8453a-128">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8453a-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8453a-129">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8453a-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8453a-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="8453a-130">See also</span></span>

- [<span data-ttu-id="8453a-131">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="8453a-131">Debugging Enumerations</span></span>](debugging-enumerations.md)
