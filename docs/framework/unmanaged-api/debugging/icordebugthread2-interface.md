---
title: Interfaz ICorDebugThread2
ms.date: 03/30/2017
api_name:
- ICorDebugThread2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2
helpviewer_keywords:
- ICorDebugThread2 interface [.NET Framework debugging]
ms.assetid: 678f89f9-cce7-46d1-af87-5e989abaa93c
topic_type:
- apiref
ms.openlocfilehash: fdaad46b739721ff95b712d4b6461a793ae0a480
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791428"
---
# <a name="icordebugthread2-interface"></a><span data-ttu-id="ee4bf-102">Interfaz ICorDebugThread2</span><span class="sxs-lookup"><span data-stu-id="ee4bf-102">ICorDebugThread2 Interface</span></span>
<span data-ttu-id="ee4bf-103">Actúa como una extensión lógica de la interfaz ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="ee4bf-103">Serves as a logical extension to the ICorDebugThread interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ee4bf-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="ee4bf-104">Methods</span></span>  
  
|<span data-ttu-id="ee4bf-105">Método</span><span class="sxs-lookup"><span data-stu-id="ee4bf-105">Method</span></span>|<span data-ttu-id="ee4bf-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="ee4bf-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ee4bf-107">GetActiveFunctions (método)</span><span class="sxs-lookup"><span data-stu-id="ee4bf-107">GetActiveFunctions Method</span></span>](icordebugthread2-getactivefunctions-method.md)|<span data-ttu-id="ee4bf-108">Obtiene una matriz de instancias de COR_ACTIVE_FUNCTION que contienen datos sobre las funciones activas de los marcos de un subproceso.</span><span class="sxs-lookup"><span data-stu-id="ee4bf-108">Gets an array of COR_ACTIVE_FUNCTION instances that contain data about the active functions in a thread's frames.</span></span>|  
|[<span data-ttu-id="ee4bf-109">GetConnectionID (método)</span><span class="sxs-lookup"><span data-stu-id="ee4bf-109">GetConnectionID Method</span></span>](icordebugthread2-getconnectionid-method.md)|<span data-ttu-id="ee4bf-110">Obtiene un identificador de conexión para esta `ICorDebugThread2`.</span><span class="sxs-lookup"><span data-stu-id="ee4bf-110">Gets a connection identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="ee4bf-111">GetTaskID (método)</span><span class="sxs-lookup"><span data-stu-id="ee4bf-111">GetTaskID Method</span></span>](icordebugthread2-gettaskid-method.md)|<span data-ttu-id="ee4bf-112">Obtiene un identificador de tarea para esta `ICorDebugThread2`.</span><span class="sxs-lookup"><span data-stu-id="ee4bf-112">Gets a task identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="ee4bf-113">GetVolatileOSThreadID (método)</span><span class="sxs-lookup"><span data-stu-id="ee4bf-113">GetVolatileOSThreadID Method</span></span>](icordebugthread2-getvolatileosthreadid-method.md)|<span data-ttu-id="ee4bf-114">Obtiene el identificador del subproceso del sistema operativo para esta `ICorDebugThread2`.</span><span class="sxs-lookup"><span data-stu-id="ee4bf-114">Gets the operating system thread identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="ee4bf-115">InterceptCurrentException (método)</span><span class="sxs-lookup"><span data-stu-id="ee4bf-115">InterceptCurrentException Method</span></span>](icordebugthread2-interceptcurrentexception-method.md)|<span data-ttu-id="ee4bf-116">Permite a un depurador interceptar la excepción actual en un subproceso.</span><span class="sxs-lookup"><span data-stu-id="ee4bf-116">Allows a debugger to intercept the current exception on a thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ee4bf-117">Notas</span><span class="sxs-lookup"><span data-stu-id="ee4bf-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ee4bf-118">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="ee4bf-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee4bf-119">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="ee4bf-119">Requirements</span></span>  
 <span data-ttu-id="ee4bf-120">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ee4bf-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee4bf-121">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ee4bf-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ee4bf-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ee4bf-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ee4bf-123">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee4bf-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee4bf-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="ee4bf-124">See also</span></span>

- [<span data-ttu-id="ee4bf-125">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="ee4bf-125">Debugging Interfaces</span></span>](debugging-interfaces.md)
