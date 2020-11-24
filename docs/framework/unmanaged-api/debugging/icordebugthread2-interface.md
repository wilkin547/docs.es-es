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
ms.openlocfilehash: fd4ad536d7d3df2b8f91f206459122cf083c8b9c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95691141"
---
# <a name="icordebugthread2-interface"></a><span data-ttu-id="c86eb-102">Interfaz ICorDebugThread2</span><span class="sxs-lookup"><span data-stu-id="c86eb-102">ICorDebugThread2 Interface</span></span>

<span data-ttu-id="c86eb-103">Actúa como una extensión lógica de la interfaz ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="c86eb-103">Serves as a logical extension to the ICorDebugThread interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c86eb-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="c86eb-104">Methods</span></span>  
  
|<span data-ttu-id="c86eb-105">Método</span><span class="sxs-lookup"><span data-stu-id="c86eb-105">Method</span></span>|<span data-ttu-id="c86eb-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="c86eb-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c86eb-107">Método GetActiveFunctions</span><span class="sxs-lookup"><span data-stu-id="c86eb-107">GetActiveFunctions Method</span></span>](icordebugthread2-getactivefunctions-method.md)|<span data-ttu-id="c86eb-108">Obtiene una matriz de instancias de COR_ACTIVE_FUNCTION que contienen datos sobre las funciones activas de los marcos de un subproceso.</span><span class="sxs-lookup"><span data-stu-id="c86eb-108">Gets an array of COR_ACTIVE_FUNCTION instances that contain data about the active functions in a thread's frames.</span></span>|  
|[<span data-ttu-id="c86eb-109">Método GetConnectionID</span><span class="sxs-lookup"><span data-stu-id="c86eb-109">GetConnectionID Method</span></span>](icordebugthread2-getconnectionid-method.md)|<span data-ttu-id="c86eb-110">Obtiene un identificador de conexión para este `ICorDebugThread2` .</span><span class="sxs-lookup"><span data-stu-id="c86eb-110">Gets a connection identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="c86eb-111">Método GetTaskID</span><span class="sxs-lookup"><span data-stu-id="c86eb-111">GetTaskID Method</span></span>](icordebugthread2-gettaskid-method.md)|<span data-ttu-id="c86eb-112">Obtiene un identificador de tarea para este `ICorDebugThread2` .</span><span class="sxs-lookup"><span data-stu-id="c86eb-112">Gets a task identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="c86eb-113">Método GetVolatileOSThreadID</span><span class="sxs-lookup"><span data-stu-id="c86eb-113">GetVolatileOSThreadID Method</span></span>](icordebugthread2-getvolatileosthreadid-method.md)|<span data-ttu-id="c86eb-114">Obtiene el identificador del subproceso del sistema operativo para este `ICorDebugThread2` .</span><span class="sxs-lookup"><span data-stu-id="c86eb-114">Gets the operating system thread identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="c86eb-115">Método InterceptCurrentException</span><span class="sxs-lookup"><span data-stu-id="c86eb-115">InterceptCurrentException Method</span></span>](icordebugthread2-interceptcurrentexception-method.md)|<span data-ttu-id="c86eb-116">Permite a un depurador interceptar la excepción actual en un subproceso.</span><span class="sxs-lookup"><span data-stu-id="c86eb-116">Allows a debugger to intercept the current exception on a thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c86eb-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c86eb-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c86eb-118">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="c86eb-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c86eb-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c86eb-119">Requirements</span></span>  

 <span data-ttu-id="c86eb-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c86eb-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c86eb-121">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c86eb-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c86eb-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c86eb-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c86eb-123">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c86eb-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c86eb-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c86eb-124">See also</span></span>

- [<span data-ttu-id="c86eb-125">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="c86eb-125">Debugging Interfaces</span></span>](debugging-interfaces.md)
