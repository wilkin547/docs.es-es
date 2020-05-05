---
title: CorDebugThreadState (Enumeración)
ms.date: 03/30/2017
api_name:
- CorDebugThreadState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugThreadState
helpviewer_keywords:
- CorDebugThreadState enumeration [.NET Framework debugging]
ms.assetid: a3ccdf18-4ec6-494d-9024-48e5c8c724f5
topic_type:
- apiref
ms.openlocfilehash: 9c22ca47a606da0949529cf55655bbcde19cb5c9
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795669"
---
# <a name="cordebugthreadstate-enumeration"></a><span data-ttu-id="8fe32-102">CorDebugThreadState (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="8fe32-102">CorDebugThreadState Enumeration</span></span>
<span data-ttu-id="8fe32-103">Especifica el estado de un subproceso de depuración.</span><span class="sxs-lookup"><span data-stu-id="8fe32-103">Specifies the state of a thread for debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8fe32-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8fe32-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugThreadState {  
    THREAD_RUN,  
    THREAD_SUSPEND  
} CorDebugThreadState;  
```  
  
## <a name="members"></a><span data-ttu-id="8fe32-105">Members</span><span class="sxs-lookup"><span data-stu-id="8fe32-105">Members</span></span>  
  
|<span data-ttu-id="8fe32-106">Member</span><span class="sxs-lookup"><span data-stu-id="8fe32-106">Member</span></span>|<span data-ttu-id="8fe32-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="8fe32-107">Description</span></span>|  
|------------|-----------------|  
|`THREAD_RUN`|<span data-ttu-id="8fe32-108">El subproceso se ejecuta libremente, a menos que se produzca un evento de depuración.</span><span class="sxs-lookup"><span data-stu-id="8fe32-108">The thread runs freely, unless a debug event occurs.</span></span>|  
|`THREAD_SUSPEND`|<span data-ttu-id="8fe32-109">No se puede ejecutar el subproceso.</span><span class="sxs-lookup"><span data-stu-id="8fe32-109">The thread cannot run.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8fe32-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8fe32-110">Remarks</span></span>  
 <span data-ttu-id="8fe32-111">El depurador utiliza `CorDebugThreadState` la enumeración para controlar la ejecución de un subproceso.</span><span class="sxs-lookup"><span data-stu-id="8fe32-111">The debugger uses the `CorDebugThreadState` enumeration to control a thread's execution.</span></span> <span data-ttu-id="8fe32-112">El estado de un subproceso se puede establecer mediante el método [ICorDebugThread:: setdebugstate (](icordebugthread-setdebugstate-method.md) o [ICorDebugController:: setallthreadsdebugstate (](icordebugcontroller-setallthreadsdebugstate-method.md) .</span><span class="sxs-lookup"><span data-stu-id="8fe32-112">The state of a thread can be set by using the [ICorDebugThread::SetDebugState](icordebugthread-setdebugstate-method.md) or [ICorDebugController::SetAllThreadsDebugState](icordebugcontroller-setallthreadsdebugstate-method.md) method.</span></span>  
  
 <span data-ttu-id="8fe32-113">Una devolución de llamada proporcionada a la [API de hospedaje](../hosting/index.md) permite el suministro de mensajes, por lo que no se necesita un estado interrumpido.</span><span class="sxs-lookup"><span data-stu-id="8fe32-113">A callback provided to the [hosting API](../hosting/index.md) enables message pumping, so an interrupted state is not needed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8fe32-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8fe32-114">Requirements</span></span>  
 <span data-ttu-id="8fe32-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8fe32-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8fe32-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8fe32-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8fe32-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8fe32-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8fe32-118">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8fe32-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fe32-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="8fe32-119">See also</span></span>

- [<span data-ttu-id="8fe32-120">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="8fe32-120">Debugging Enumerations</span></span>](debugging-enumerations.md)
