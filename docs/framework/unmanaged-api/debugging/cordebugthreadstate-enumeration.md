---
description: 'Más información sobre: enumeración CorDebugThreadState ('
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
ms.openlocfilehash: 0cf83ee31547e49ccc7d09e0ab4ee85548688b36
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99661814"
---
# <a name="cordebugthreadstate-enumeration"></a><span data-ttu-id="1c971-103">CorDebugThreadState (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="1c971-103">CorDebugThreadState Enumeration</span></span>

<span data-ttu-id="1c971-104">Especifica el estado de un subproceso de depuración.</span><span class="sxs-lookup"><span data-stu-id="1c971-104">Specifies the state of a thread for debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c971-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1c971-105">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugThreadState {  
    THREAD_RUN,  
    THREAD_SUSPEND  
} CorDebugThreadState;  
```  
  
## <a name="members"></a><span data-ttu-id="1c971-106">Members</span><span class="sxs-lookup"><span data-stu-id="1c971-106">Members</span></span>  
  
|<span data-ttu-id="1c971-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="1c971-107">Member</span></span>|<span data-ttu-id="1c971-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="1c971-108">Description</span></span>|  
|------------|-----------------|  
|`THREAD_RUN`|<span data-ttu-id="1c971-109">El subproceso se ejecuta libremente, a menos que se produzca un evento de depuración.</span><span class="sxs-lookup"><span data-stu-id="1c971-109">The thread runs freely, unless a debug event occurs.</span></span>|  
|`THREAD_SUSPEND`|<span data-ttu-id="1c971-110">No se puede ejecutar el subproceso.</span><span class="sxs-lookup"><span data-stu-id="1c971-110">The thread cannot run.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1c971-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1c971-111">Remarks</span></span>  

 <span data-ttu-id="1c971-112">El depurador utiliza la `CorDebugThreadState` enumeración para controlar la ejecución de un subproceso.</span><span class="sxs-lookup"><span data-stu-id="1c971-112">The debugger uses the `CorDebugThreadState` enumeration to control a thread's execution.</span></span> <span data-ttu-id="1c971-113">El estado de un subproceso se puede establecer mediante el método [ICorDebugThread:: setdebugstate (](icordebugthread-setdebugstate-method.md) o [ICorDebugController:: setallthreadsdebugstate (](icordebugcontroller-setallthreadsdebugstate-method.md) .</span><span class="sxs-lookup"><span data-stu-id="1c971-113">The state of a thread can be set by using the [ICorDebugThread::SetDebugState](icordebugthread-setdebugstate-method.md) or [ICorDebugController::SetAllThreadsDebugState](icordebugcontroller-setallthreadsdebugstate-method.md) method.</span></span>  
  
 <span data-ttu-id="1c971-114">Una devolución de llamada proporcionada a la [API de hospedaje](../hosting/index.md) permite el suministro de mensajes, por lo que no se necesita un estado interrumpido.</span><span class="sxs-lookup"><span data-stu-id="1c971-114">A callback provided to the [hosting API](../hosting/index.md) enables message pumping, so an interrupted state is not needed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c971-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1c971-115">Requirements</span></span>  

 <span data-ttu-id="1c971-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c971-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c971-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1c971-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1c971-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1c971-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1c971-119">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c971-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c971-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="1c971-120">See also</span></span>

- [<span data-ttu-id="1c971-121">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="1c971-121">Debugging Enumerations</span></span>](debugging-enumerations.md)
