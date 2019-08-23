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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4d21c221bba3ac668924003f96580bb660229ad7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963001"
---
# <a name="icordebugthread2-interface"></a><span data-ttu-id="f6d51-102">Interfaz ICorDebugThread2</span><span class="sxs-lookup"><span data-stu-id="f6d51-102">ICorDebugThread2 Interface</span></span>
<span data-ttu-id="f6d51-103">Actúa como una extensión lógica de la interfaz ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="f6d51-103">Serves as a logical extension to the ICorDebugThread interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f6d51-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="f6d51-104">Methods</span></span>  
  
|<span data-ttu-id="f6d51-105">Método</span><span class="sxs-lookup"><span data-stu-id="f6d51-105">Method</span></span>|<span data-ttu-id="f6d51-106">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="f6d51-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f6d51-107">GetActiveFunctions (método)</span><span class="sxs-lookup"><span data-stu-id="f6d51-107">GetActiveFunctions Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getactivefunctions-method.md)|<span data-ttu-id="f6d51-108">Obtiene una matriz de instancias de COR_ACTIVE_FUNCTION que contienen datos sobre las funciones activas de los marcos de un subproceso.</span><span class="sxs-lookup"><span data-stu-id="f6d51-108">Gets an array of COR_ACTIVE_FUNCTION instances that contain data about the active functions in a thread's frames.</span></span>|  
|[<span data-ttu-id="f6d51-109">GetConnectionID (método)</span><span class="sxs-lookup"><span data-stu-id="f6d51-109">GetConnectionID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getconnectionid-method.md)|<span data-ttu-id="f6d51-110">Obtiene un identificador de conexión para este `ICorDebugThread2`.</span><span class="sxs-lookup"><span data-stu-id="f6d51-110">Gets a connection identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="f6d51-111">GetTaskID (método)</span><span class="sxs-lookup"><span data-stu-id="f6d51-111">GetTaskID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-gettaskid-method.md)|<span data-ttu-id="f6d51-112">Obtiene un identificador de tarea para este `ICorDebugThread2`.</span><span class="sxs-lookup"><span data-stu-id="f6d51-112">Gets a task identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="f6d51-113">GetVolatileOSThreadID (método)</span><span class="sxs-lookup"><span data-stu-id="f6d51-113">GetVolatileOSThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getvolatileosthreadid-method.md)|<span data-ttu-id="f6d51-114">Obtiene el identificador del subproceso del sistema operativo `ICorDebugThread2`para este.</span><span class="sxs-lookup"><span data-stu-id="f6d51-114">Gets the operating system thread identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="f6d51-115">InterceptCurrentException (método)</span><span class="sxs-lookup"><span data-stu-id="f6d51-115">InterceptCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interceptcurrentexception-method.md)|<span data-ttu-id="f6d51-116">Permite a un depurador interceptar la excepción actual en un subproceso.</span><span class="sxs-lookup"><span data-stu-id="f6d51-116">Allows a debugger to intercept the current exception on a thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f6d51-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f6d51-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f6d51-118">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="f6d51-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6d51-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f6d51-119">Requirements</span></span>  
 <span data-ttu-id="f6d51-120">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f6d51-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6d51-121">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="f6d51-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f6d51-122">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f6d51-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f6d51-123">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6d51-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6d51-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="f6d51-124">See also</span></span>

- [<span data-ttu-id="f6d51-125">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="f6d51-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
