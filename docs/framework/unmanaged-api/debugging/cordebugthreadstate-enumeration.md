---
title: "CorDebugThreadState (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugThreadState
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugThreadState
helpviewer_keywords: CorDebugThreadState enumeration [.NET Framework debugging]
ms.assetid: a3ccdf18-4ec6-494d-9024-48e5c8c724f5
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: dc3555d0ecd85208688a4aae69aef7c6c88303b3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="cordebugthreadstate-enumeration"></a><span data-ttu-id="95102-102">CorDebugThreadState (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="95102-102">CorDebugThreadState Enumeration</span></span>
<span data-ttu-id="95102-103">Especifica el estado de un subproceso de depuración.</span><span class="sxs-lookup"><span data-stu-id="95102-103">Specifies the state of a thread for debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95102-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="95102-104">Syntax</span></span>  
  
```  
typedef enum CorDebugThreadState {  
    THREAD_RUN,  
    THREAD_SUSPEND  
} CorDebugThreadState;  
```  
  
## <a name="members"></a><span data-ttu-id="95102-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="95102-105">Members</span></span>  
  
|<span data-ttu-id="95102-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="95102-106">Member</span></span>|<span data-ttu-id="95102-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="95102-107">Description</span></span>|  
|------------|-----------------|  
|`THREAD_RUN`|<span data-ttu-id="95102-108">El subproceso se ejecuta libremente, a menos que se produce un evento de depuración.</span><span class="sxs-lookup"><span data-stu-id="95102-108">The thread runs freely, unless a debug event occurs.</span></span>|  
|`THREAD_SUSPEND`|<span data-ttu-id="95102-109">No se puede ejecutar el subproceso.</span><span class="sxs-lookup"><span data-stu-id="95102-109">The thread cannot run.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="95102-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="95102-110">Remarks</span></span>  
 <span data-ttu-id="95102-111">El depurador utiliza el `CorDebugThreadState` enumeración para controlar la ejecución de un subproceso.</span><span class="sxs-lookup"><span data-stu-id="95102-111">The debugger uses the `CorDebugThreadState` enumeration to control a thread's execution.</span></span> <span data-ttu-id="95102-112">El estado de un subproceso puede establecerse mediante el [SetDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md) o [ICorDebugController:: SetAllThreadsDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="95102-112">The state of a thread can be set by using the [ICorDebugThread::SetDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md) or [ICorDebugController::SetAllThreadsDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md) method.</span></span>  
  
 <span data-ttu-id="95102-113">Una devolución de llamada proporcionada para el [API de hospedaje](../../../../docs/framework/unmanaged-api/hosting/index.md) permite el suministro de mensajes, por lo que no se necesita un estado interrumpido.</span><span class="sxs-lookup"><span data-stu-id="95102-113">A callback provided to the [hosting API](../../../../docs/framework/unmanaged-api/hosting/index.md) enables message pumping, so an interrupted state is not needed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95102-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="95102-114">Requirements</span></span>  
 <span data-ttu-id="95102-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95102-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95102-116">**Encabezado:** CorDebug.idl, CorDegug.h</span><span class="sxs-lookup"><span data-stu-id="95102-116">**Header:** CorDebug.idl, CorDegug.h</span></span>  
  
 <span data-ttu-id="95102-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="95102-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="95102-118">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95102-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95102-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="95102-119">See Also</span></span>  
 [<span data-ttu-id="95102-120">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="95102-120">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
