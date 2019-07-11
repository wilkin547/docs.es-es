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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ce252f5a4b5fbcdbbc7b70c8b1c829490f8f63e5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739529"
---
# <a name="cordebugthreadstate-enumeration"></a><span data-ttu-id="2164e-102">CorDebugThreadState (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="2164e-102">CorDebugThreadState Enumeration</span></span>
<span data-ttu-id="2164e-103">Especifica el estado de un subproceso de depuración.</span><span class="sxs-lookup"><span data-stu-id="2164e-103">Specifies the state of a thread for debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2164e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2164e-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugThreadState {  
    THREAD_RUN,  
    THREAD_SUSPEND  
} CorDebugThreadState;  
```  
  
## <a name="members"></a><span data-ttu-id="2164e-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="2164e-105">Members</span></span>  
  
|<span data-ttu-id="2164e-106">Member</span><span class="sxs-lookup"><span data-stu-id="2164e-106">Member</span></span>|<span data-ttu-id="2164e-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="2164e-107">Description</span></span>|  
|------------|-----------------|  
|`THREAD_RUN`|<span data-ttu-id="2164e-108">El subproceso se ejecuta de forma gratuita, a menos que se produce un evento de depuración.</span><span class="sxs-lookup"><span data-stu-id="2164e-108">The thread runs freely, unless a debug event occurs.</span></span>|  
|`THREAD_SUSPEND`|<span data-ttu-id="2164e-109">No se puede ejecutar el subproceso.</span><span class="sxs-lookup"><span data-stu-id="2164e-109">The thread cannot run.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2164e-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2164e-110">Remarks</span></span>  
 <span data-ttu-id="2164e-111">El depurador usa el `CorDebugThreadState` enumeración para controlar la ejecución de un subproceso.</span><span class="sxs-lookup"><span data-stu-id="2164e-111">The debugger uses the `CorDebugThreadState` enumeration to control a thread's execution.</span></span> <span data-ttu-id="2164e-112">El estado de un subproceso puede establecerse mediante el [SetDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md) o [ICorDebugController:: SetAllThreadsDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="2164e-112">The state of a thread can be set by using the [ICorDebugThread::SetDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md) or [ICorDebugController::SetAllThreadsDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md) method.</span></span>  
  
 <span data-ttu-id="2164e-113">Una devolución de llamada proporcionada para el [API de hospedaje](../../../../docs/framework/unmanaged-api/hosting/index.md) permite la distribución de mensajes, por lo que no es necesario un estado interrumpido.</span><span class="sxs-lookup"><span data-stu-id="2164e-113">A callback provided to the [hosting API](../../../../docs/framework/unmanaged-api/hosting/index.md) enables message pumping, so an interrupted state is not needed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2164e-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2164e-114">Requirements</span></span>  
 <span data-ttu-id="2164e-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2164e-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2164e-116">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2164e-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2164e-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2164e-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2164e-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2164e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2164e-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="2164e-119">See also</span></span>

- [<span data-ttu-id="2164e-120">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="2164e-120">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
