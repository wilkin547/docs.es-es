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
ms.workload: dotnet
ms.openlocfilehash: a5363282f2efed003238014390f50c448c529ce2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="cordebugthreadstate-enumeration"></a><span data-ttu-id="620c5-102">CorDebugThreadState (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="620c5-102">CorDebugThreadState Enumeration</span></span>
<span data-ttu-id="620c5-103">Especifica el estado de un subproceso de depuración.</span><span class="sxs-lookup"><span data-stu-id="620c5-103">Specifies the state of a thread for debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="620c5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="620c5-104">Syntax</span></span>  
  
```  
typedef enum CorDebugThreadState {  
    THREAD_RUN,  
    THREAD_SUSPEND  
} CorDebugThreadState;  
```  
  
## <a name="members"></a><span data-ttu-id="620c5-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="620c5-105">Members</span></span>  
  
|<span data-ttu-id="620c5-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="620c5-106">Member</span></span>|<span data-ttu-id="620c5-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="620c5-107">Description</span></span>|  
|------------|-----------------|  
|`THREAD_RUN`|<span data-ttu-id="620c5-108">El subproceso se ejecuta libremente, a menos que se produce un evento de depuración.</span><span class="sxs-lookup"><span data-stu-id="620c5-108">The thread runs freely, unless a debug event occurs.</span></span>|  
|`THREAD_SUSPEND`|<span data-ttu-id="620c5-109">No se puede ejecutar el subproceso.</span><span class="sxs-lookup"><span data-stu-id="620c5-109">The thread cannot run.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="620c5-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="620c5-110">Remarks</span></span>  
 <span data-ttu-id="620c5-111">El depurador utiliza el `CorDebugThreadState` enumeración para controlar la ejecución de un subproceso.</span><span class="sxs-lookup"><span data-stu-id="620c5-111">The debugger uses the `CorDebugThreadState` enumeration to control a thread's execution.</span></span> <span data-ttu-id="620c5-112">El estado de un subproceso puede establecerse mediante el [SetDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md) o [ICorDebugController:: SetAllThreadsDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="620c5-112">The state of a thread can be set by using the [ICorDebugThread::SetDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md) or [ICorDebugController::SetAllThreadsDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md) method.</span></span>  
  
 <span data-ttu-id="620c5-113">Una devolución de llamada proporcionada para el [API de hospedaje](../../../../docs/framework/unmanaged-api/hosting/index.md) permite el suministro de mensajes, por lo que no se necesita un estado interrumpido.</span><span class="sxs-lookup"><span data-stu-id="620c5-113">A callback provided to the [hosting API](../../../../docs/framework/unmanaged-api/hosting/index.md) enables message pumping, so an interrupted state is not needed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="620c5-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="620c5-114">Requirements</span></span>  
 <span data-ttu-id="620c5-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="620c5-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="620c5-116">**Encabezado:** CorDebug.idl, CorDegug.h</span><span class="sxs-lookup"><span data-stu-id="620c5-116">**Header:** CorDebug.idl, CorDegug.h</span></span>  
  
 <span data-ttu-id="620c5-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="620c5-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="620c5-118">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="620c5-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="620c5-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="620c5-119">See Also</span></span>  
 [<span data-ttu-id="620c5-120">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="620c5-120">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
