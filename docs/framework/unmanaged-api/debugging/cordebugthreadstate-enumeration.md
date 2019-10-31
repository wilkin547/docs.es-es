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
ms.openlocfilehash: 1ff36e8ef6b7c02eea5b02bc22587bc3889df093
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133689"
---
# <a name="cordebugthreadstate-enumeration"></a><span data-ttu-id="8e134-102">CorDebugThreadState (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="8e134-102">CorDebugThreadState Enumeration</span></span>
<span data-ttu-id="8e134-103">Especifica el estado de un subproceso de depuración.</span><span class="sxs-lookup"><span data-stu-id="8e134-103">Specifies the state of a thread for debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e134-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8e134-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugThreadState {  
    THREAD_RUN,  
    THREAD_SUSPEND  
} CorDebugThreadState;  
```  
  
## <a name="members"></a><span data-ttu-id="8e134-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="8e134-105">Members</span></span>  
  
|<span data-ttu-id="8e134-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="8e134-106">Member</span></span>|<span data-ttu-id="8e134-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="8e134-107">Description</span></span>|  
|------------|-----------------|  
|`THREAD_RUN`|<span data-ttu-id="8e134-108">El subproceso se ejecuta libremente, a menos que se produzca un evento de depuración.</span><span class="sxs-lookup"><span data-stu-id="8e134-108">The thread runs freely, unless a debug event occurs.</span></span>|  
|`THREAD_SUSPEND`|<span data-ttu-id="8e134-109">No se puede ejecutar el subproceso.</span><span class="sxs-lookup"><span data-stu-id="8e134-109">The thread cannot run.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8e134-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8e134-110">Remarks</span></span>  
 <span data-ttu-id="8e134-111">El depurador utiliza la enumeración `CorDebugThreadState` para controlar la ejecución de un subproceso.</span><span class="sxs-lookup"><span data-stu-id="8e134-111">The debugger uses the `CorDebugThreadState` enumeration to control a thread's execution.</span></span> <span data-ttu-id="8e134-112">El estado de un subproceso se puede establecer mediante el método [ICorDebugThread:: setdebugstate (](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md) o [ICorDebugController:: setallthreadsdebugstate (](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md) .</span><span class="sxs-lookup"><span data-stu-id="8e134-112">The state of a thread can be set by using the [ICorDebugThread::SetDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md) or [ICorDebugController::SetAllThreadsDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md) method.</span></span>  
  
 <span data-ttu-id="8e134-113">Una devolución de llamada proporcionada a la [API de hospedaje](../../../../docs/framework/unmanaged-api/hosting/index.md) permite el suministro de mensajes, por lo que no se necesita un estado interrumpido.</span><span class="sxs-lookup"><span data-stu-id="8e134-113">A callback provided to the [hosting API](../../../../docs/framework/unmanaged-api/hosting/index.md) enables message pumping, so an interrupted state is not needed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e134-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8e134-114">Requirements</span></span>  
 <span data-ttu-id="8e134-115">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8e134-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e134-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8e134-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8e134-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8e134-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8e134-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e134-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e134-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="8e134-119">See also</span></span>

- [<span data-ttu-id="8e134-120">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="8e134-120">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
