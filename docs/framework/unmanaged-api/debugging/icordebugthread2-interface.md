---
description: 'Más información acerca de: interfaz ICorDebugThread2'
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
ms.openlocfilehash: 81f687f6daff9ffa7298ec6d818a214b8934bcc3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99658508"
---
# <a name="icordebugthread2-interface"></a><span data-ttu-id="05e71-103">Interfaz ICorDebugThread2</span><span class="sxs-lookup"><span data-stu-id="05e71-103">ICorDebugThread2 Interface</span></span>

<span data-ttu-id="05e71-104">Actúa como una extensión lógica de la interfaz ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="05e71-104">Serves as a logical extension to the ICorDebugThread interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="05e71-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="05e71-105">Methods</span></span>  
  
|<span data-ttu-id="05e71-106">Método</span><span class="sxs-lookup"><span data-stu-id="05e71-106">Method</span></span>|<span data-ttu-id="05e71-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="05e71-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="05e71-108">Método GetActiveFunctions</span><span class="sxs-lookup"><span data-stu-id="05e71-108">GetActiveFunctions Method</span></span>](icordebugthread2-getactivefunctions-method.md)|<span data-ttu-id="05e71-109">Obtiene una matriz de instancias de COR_ACTIVE_FUNCTION que contienen datos sobre las funciones activas de los marcos de un subproceso.</span><span class="sxs-lookup"><span data-stu-id="05e71-109">Gets an array of COR_ACTIVE_FUNCTION instances that contain data about the active functions in a thread's frames.</span></span>|  
|[<span data-ttu-id="05e71-110">Método GetConnectionID</span><span class="sxs-lookup"><span data-stu-id="05e71-110">GetConnectionID Method</span></span>](icordebugthread2-getconnectionid-method.md)|<span data-ttu-id="05e71-111">Obtiene un identificador de conexión para este `ICorDebugThread2` .</span><span class="sxs-lookup"><span data-stu-id="05e71-111">Gets a connection identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="05e71-112">Método GetTaskID</span><span class="sxs-lookup"><span data-stu-id="05e71-112">GetTaskID Method</span></span>](icordebugthread2-gettaskid-method.md)|<span data-ttu-id="05e71-113">Obtiene un identificador de tarea para este `ICorDebugThread2` .</span><span class="sxs-lookup"><span data-stu-id="05e71-113">Gets a task identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="05e71-114">Método GetVolatileOSThreadID</span><span class="sxs-lookup"><span data-stu-id="05e71-114">GetVolatileOSThreadID Method</span></span>](icordebugthread2-getvolatileosthreadid-method.md)|<span data-ttu-id="05e71-115">Obtiene el identificador del subproceso del sistema operativo para este `ICorDebugThread2` .</span><span class="sxs-lookup"><span data-stu-id="05e71-115">Gets the operating system thread identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="05e71-116">Método InterceptCurrentException</span><span class="sxs-lookup"><span data-stu-id="05e71-116">InterceptCurrentException Method</span></span>](icordebugthread2-interceptcurrentexception-method.md)|<span data-ttu-id="05e71-117">Permite a un depurador interceptar la excepción actual en un subproceso.</span><span class="sxs-lookup"><span data-stu-id="05e71-117">Allows a debugger to intercept the current exception on a thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="05e71-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="05e71-118">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="05e71-119">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="05e71-119">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05e71-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="05e71-120">Requirements</span></span>  

 <span data-ttu-id="05e71-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="05e71-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05e71-122">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="05e71-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="05e71-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="05e71-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="05e71-124">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05e71-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05e71-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="05e71-125">See also</span></span>

- [<span data-ttu-id="05e71-126">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="05e71-126">Debugging Interfaces</span></span>](debugging-interfaces.md)
