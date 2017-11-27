---
title: ICorDebugThread2 Interfaz1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread2
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread2
helpviewer_keywords: ICorDebugThread2 interface [.NET Framework debugging]
ms.assetid: 678f89f9-cce7-46d1-af87-5e989abaa93c
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5d3a554d075adb56294e4693b234ce22735fb982
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugthread2-interface1"></a><span data-ttu-id="330c9-102">ICorDebugThread2 Interfaz1</span><span class="sxs-lookup"><span data-stu-id="330c9-102">ICorDebugThread2 Interface1</span></span>
<span data-ttu-id="330c9-103">Actúa como una extensión lógica ICorDebugThread (interfaz).</span><span class="sxs-lookup"><span data-stu-id="330c9-103">Serves as a logical extension to the ICorDebugThread interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="330c9-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="330c9-104">Methods</span></span>  
  
|<span data-ttu-id="330c9-105">Método</span><span class="sxs-lookup"><span data-stu-id="330c9-105">Method</span></span>|<span data-ttu-id="330c9-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="330c9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="330c9-107">GetActiveFunctions (método)</span><span class="sxs-lookup"><span data-stu-id="330c9-107">GetActiveFunctions Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getactivefunctions-method.md)|<span data-ttu-id="330c9-108">Obtiene una matriz de instancias COR_ACTIVE_FUNCTION que contienen datos sobre las funciones activas en los marcos de un subproceso.</span><span class="sxs-lookup"><span data-stu-id="330c9-108">Gets an array of COR_ACTIVE_FUNCTION instances that contain data about the active functions in a thread's frames.</span></span>|  
|[<span data-ttu-id="330c9-109">GetConnectionID (método)</span><span class="sxs-lookup"><span data-stu-id="330c9-109">GetConnectionID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getconnectionid-method.md)|<span data-ttu-id="330c9-110">Obtiene un identificador de conexión para este `ICorDebugThread2`.</span><span class="sxs-lookup"><span data-stu-id="330c9-110">Gets a connection identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="330c9-111">GetTaskID (método)</span><span class="sxs-lookup"><span data-stu-id="330c9-111">GetTaskID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-gettaskid-method.md)|<span data-ttu-id="330c9-112">Obtiene un identificador de tarea para `ICorDebugThread2`.</span><span class="sxs-lookup"><span data-stu-id="330c9-112">Gets a task identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="330c9-113">GetVolatileOSThreadID (método)</span><span class="sxs-lookup"><span data-stu-id="330c9-113">GetVolatileOSThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-getvolatileosthreadid-method.md)|<span data-ttu-id="330c9-114">Obtiene el identificador de subproceso del sistema operativo de este `ICorDebugThread2`.</span><span class="sxs-lookup"><span data-stu-id="330c9-114">Gets the operating system thread identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="330c9-115">InterceptCurrentException (método)</span><span class="sxs-lookup"><span data-stu-id="330c9-115">InterceptCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interceptcurrentexception-method.md)|<span data-ttu-id="330c9-116">Permite a un depurador interceptar la excepción actual en un subproceso.</span><span class="sxs-lookup"><span data-stu-id="330c9-116">Allows a debugger to intercept the current exception on a thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="330c9-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="330c9-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="330c9-118">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="330c9-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="330c9-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="330c9-119">Requirements</span></span>  
 <span data-ttu-id="330c9-120">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="330c9-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="330c9-121">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="330c9-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="330c9-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="330c9-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="330c9-123">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="330c9-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="330c9-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="330c9-124">See Also</span></span>  
 [<span data-ttu-id="330c9-125">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="330c9-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
