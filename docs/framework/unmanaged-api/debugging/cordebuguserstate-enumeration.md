---
title: "CorDebugUserState (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugUserState
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugUserState
helpviewer_keywords: CorDebugUserState enumeration [.NET Framework debugging]
ms.assetid: 5f6c2bcd-8102-4e3b-abc5-86ab0bd62def
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 95240dfea92a4ebbf2c7b9c11b7376d912c40fe5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="cordebuguserstate-enumeration"></a><span data-ttu-id="da0b5-102">CorDebugUserState (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="da0b5-102">CorDebugUserState Enumeration</span></span>
<span data-ttu-id="da0b5-103">Indica el estado de uso de un subproceso.</span><span class="sxs-lookup"><span data-stu-id="da0b5-103">Indicates the user state of a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da0b5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="da0b5-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="da0b5-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="da0b5-105">Members</span></span>  
  
|<span data-ttu-id="da0b5-106">Valor</span><span class="sxs-lookup"><span data-stu-id="da0b5-106">Value</span></span>|<span data-ttu-id="da0b5-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="da0b5-107">Description</span></span>|  
|-----------|-----------------|  
|`USER_STOP_REQUESTED`|<span data-ttu-id="da0b5-108">Se ha solicitado una finalización del subproceso.</span><span class="sxs-lookup"><span data-stu-id="da0b5-108">A termination of the thread has been requested.</span></span>|  
|`USER_SUSPEND_REQUESTED`|<span data-ttu-id="da0b5-109">Se ha solicitado una suspensión del subproceso.</span><span class="sxs-lookup"><span data-stu-id="da0b5-109">A suspension of the thread has been requested.</span></span>|  
|`USER_BACKGROUND`|<span data-ttu-id="da0b5-110">Se está ejecutando el subproceso en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="da0b5-110">The thread is running in the background.</span></span>|  
|`USER_UNSTARTED`|<span data-ttu-id="da0b5-111">El subproceso no ha iniciado la ejecución.</span><span class="sxs-lookup"><span data-stu-id="da0b5-111">The thread has not started executing.</span></span>|  
|`USER_STOPPED`|<span data-ttu-id="da0b5-112">El subproceso ha terminado.</span><span class="sxs-lookup"><span data-stu-id="da0b5-112">The thread has been terminated.</span></span>|  
|`USER_WAIT_SLEEP_JOIN`|<span data-ttu-id="da0b5-113">El subproceso está esperando a otro subproceso completar una tarea.</span><span class="sxs-lookup"><span data-stu-id="da0b5-113">The thread is waiting for another thread to complete a task.</span></span>|  
|`USER_SUSPENDED`|<span data-ttu-id="da0b5-114">Se ha suspendido el subproceso.</span><span class="sxs-lookup"><span data-stu-id="da0b5-114">The thread has been suspended.</span></span>|  
|`USER_UNSAFE_POINT`|<span data-ttu-id="da0b5-115">El subproceso está en un punto no seguro.</span><span class="sxs-lookup"><span data-stu-id="da0b5-115">The thread is at an unsafe point.</span></span> <span data-ttu-id="da0b5-116">Es decir, el subproceso está en un punto de ejecución donde puede bloquear la colección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="da0b5-116">That is, the thread is at a point in execution where it may block garbage collection.</span></span><br /><br /> <span data-ttu-id="da0b5-117">Depurar eventos se pueden enviar desde puntos no seguros, pero la suspensión de un subproceso en un punto no seguro provocará muy probablemente un interbloqueo hasta que se reanuda el subproceso.</span><span class="sxs-lookup"><span data-stu-id="da0b5-117">Debug events may be dispatched from unsafe points, but suspending a thread at an unsafe point  will very likely cause a deadlock until the thread is resumed.</span></span> <span data-ttu-id="da0b5-118">Los puntos seguros y se determinan por el just-in-time (JIT) y la implementación de la colección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="da0b5-118">The safe and unsafe points are determined by the just-in-time (JIT) and garbage collection implementation.</span></span>|  
|`USER_THREADPOOL`|<span data-ttu-id="da0b5-119">Es el subproceso del grupo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="da0b5-119">The thread is from the thread pool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="da0b5-120">Comentarios</span><span class="sxs-lookup"><span data-stu-id="da0b5-120">Remarks</span></span>  
 <span data-ttu-id="da0b5-121">El estado de usuario de un subproceso es el estado que tiene el subproceso cuando lo examina el depurador.</span><span class="sxs-lookup"><span data-stu-id="da0b5-121">The user state of a thread is the state that the thread has when the debugger examines it.</span></span> <span data-ttu-id="da0b5-122">Un subproceso puede tener una combinación de Estados de usuario.</span><span class="sxs-lookup"><span data-stu-id="da0b5-122">A thread may have a combination of user states.</span></span>  
  
 <span data-ttu-id="da0b5-123">Use la [ICorDebugThread:: GetUserState](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getuserstate-method.md) método para recuperar el estado de usuario de un subproceso.</span><span class="sxs-lookup"><span data-stu-id="da0b5-123">Use the [ICorDebugThread::GetUserState](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getuserstate-method.md) method to retrieve a thread's user state.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da0b5-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="da0b5-124">Requirements</span></span>  
 <span data-ttu-id="da0b5-125">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da0b5-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da0b5-126">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="da0b5-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="da0b5-127">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="da0b5-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="da0b5-128">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da0b5-128">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da0b5-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="da0b5-129">See Also</span></span>  
 [<span data-ttu-id="da0b5-130">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="da0b5-130">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
