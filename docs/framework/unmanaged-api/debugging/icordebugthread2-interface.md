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
ms.openlocfilehash: 82648714c375998e9daa1bb59cd9ebd9802b5794
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993946"
---
# <a name="icordebugthread2-interface"></a><span data-ttu-id="de00f-102">Interfaz ICorDebugThread2</span><span class="sxs-lookup"><span data-stu-id="de00f-102">ICorDebugThread2 Interface</span></span>
<span data-ttu-id="de00f-103">Actúa como una extensión lógica ICorDebugThread (interfaz).</span><span class="sxs-lookup"><span data-stu-id="de00f-103">Serves as a logical extension to the ICorDebugThread interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="de00f-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="de00f-104">Methods</span></span>  
  
|<span data-ttu-id="de00f-105">Método</span><span class="sxs-lookup"><span data-stu-id="de00f-105">Method</span></span>|<span data-ttu-id="de00f-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="de00f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="de00f-107">GetActiveFunctions (método)</span><span class="sxs-lookup"><span data-stu-id="de00f-107">GetActiveFunctions Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getactivefunctions-method.md)|<span data-ttu-id="de00f-108">Obtiene una matriz de instancias COR_ACTIVE_FUNCTION que contienen datos sobre las funciones activas en los marcos de un subproceso.</span><span class="sxs-lookup"><span data-stu-id="de00f-108">Gets an array of COR_ACTIVE_FUNCTION instances that contain data about the active functions in a thread's frames.</span></span>|  
|[<span data-ttu-id="de00f-109">GetConnectionID (método)</span><span class="sxs-lookup"><span data-stu-id="de00f-109">GetConnectionID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getconnectionid-method.md)|<span data-ttu-id="de00f-110">Obtiene un identificador de conexión para este `ICorDebugThread2`.</span><span class="sxs-lookup"><span data-stu-id="de00f-110">Gets a connection identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="de00f-111">GetTaskID (método)</span><span class="sxs-lookup"><span data-stu-id="de00f-111">GetTaskID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-gettaskid-method.md)|<span data-ttu-id="de00f-112">Obtiene un identificador de tarea para este `ICorDebugThread2`.</span><span class="sxs-lookup"><span data-stu-id="de00f-112">Gets a task identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="de00f-113">GetVolatileOSThreadID (método)</span><span class="sxs-lookup"><span data-stu-id="de00f-113">GetVolatileOSThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getvolatileosthreadid-method.md)|<span data-ttu-id="de00f-114">Obtiene el identificador del subproceso del sistema operativo para este `ICorDebugThread2`.</span><span class="sxs-lookup"><span data-stu-id="de00f-114">Gets the operating system thread identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="de00f-115">InterceptCurrentException (método)</span><span class="sxs-lookup"><span data-stu-id="de00f-115">InterceptCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interceptcurrentexception-method.md)|<span data-ttu-id="de00f-116">Permite a un depurador interceptar la excepción actual en un subproceso.</span><span class="sxs-lookup"><span data-stu-id="de00f-116">Allows a debugger to intercept the current exception on a thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="de00f-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="de00f-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="de00f-118">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="de00f-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de00f-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="de00f-119">Requirements</span></span>  
 <span data-ttu-id="de00f-120">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="de00f-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de00f-121">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="de00f-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="de00f-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="de00f-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="de00f-123">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de00f-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de00f-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="de00f-124">See also</span></span>

- [<span data-ttu-id="de00f-125">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="de00f-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
