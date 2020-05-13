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
ms.openlocfilehash: a7a8d96548704f223f05826af79a4e227bdfab06
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379830"
---
# <a name="icordebugthread2-interface"></a><span data-ttu-id="9c662-102">Interfaz ICorDebugThread2</span><span class="sxs-lookup"><span data-stu-id="9c662-102">ICorDebugThread2 Interface</span></span>
<span data-ttu-id="9c662-103">Actúa como una extensión lógica de la interfaz ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="9c662-103">Serves as a logical extension to the ICorDebugThread interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9c662-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="9c662-104">Methods</span></span>  
  
|<span data-ttu-id="9c662-105">Método</span><span class="sxs-lookup"><span data-stu-id="9c662-105">Method</span></span>|<span data-ttu-id="9c662-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="9c662-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9c662-107">Método GetActiveFunctions</span><span class="sxs-lookup"><span data-stu-id="9c662-107">GetActiveFunctions Method</span></span>](icordebugthread2-getactivefunctions-method.md)|<span data-ttu-id="9c662-108">Obtiene una matriz de instancias de COR_ACTIVE_FUNCTION que contienen datos sobre las funciones activas de los marcos de un subproceso.</span><span class="sxs-lookup"><span data-stu-id="9c662-108">Gets an array of COR_ACTIVE_FUNCTION instances that contain data about the active functions in a thread's frames.</span></span>|  
|[<span data-ttu-id="9c662-109">Método GetConnectionID</span><span class="sxs-lookup"><span data-stu-id="9c662-109">GetConnectionID Method</span></span>](icordebugthread2-getconnectionid-method.md)|<span data-ttu-id="9c662-110">Obtiene un identificador de conexión para este `ICorDebugThread2` .</span><span class="sxs-lookup"><span data-stu-id="9c662-110">Gets a connection identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="9c662-111">Método GetTaskID</span><span class="sxs-lookup"><span data-stu-id="9c662-111">GetTaskID Method</span></span>](icordebugthread2-gettaskid-method.md)|<span data-ttu-id="9c662-112">Obtiene un identificador de tarea para este `ICorDebugThread2` .</span><span class="sxs-lookup"><span data-stu-id="9c662-112">Gets a task identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="9c662-113">Método GetVolatileOSThreadID</span><span class="sxs-lookup"><span data-stu-id="9c662-113">GetVolatileOSThreadID Method</span></span>](icordebugthread2-getvolatileosthreadid-method.md)|<span data-ttu-id="9c662-114">Obtiene el identificador del subproceso del sistema operativo para este `ICorDebugThread2` .</span><span class="sxs-lookup"><span data-stu-id="9c662-114">Gets the operating system thread identifier for this `ICorDebugThread2`.</span></span>|  
|[<span data-ttu-id="9c662-115">Método InterceptCurrentException</span><span class="sxs-lookup"><span data-stu-id="9c662-115">InterceptCurrentException Method</span></span>](icordebugthread2-interceptcurrentexception-method.md)|<span data-ttu-id="9c662-116">Permite a un depurador interceptar la excepción actual en un subproceso.</span><span class="sxs-lookup"><span data-stu-id="9c662-116">Allows a debugger to intercept the current exception on a thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9c662-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="9c662-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9c662-118">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="9c662-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c662-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9c662-119">Requirements</span></span>  
 <span data-ttu-id="9c662-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9c662-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c662-121">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9c662-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9c662-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9c662-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9c662-123">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c662-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c662-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9c662-124">See also</span></span>

- [<span data-ttu-id="9c662-125">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="9c662-125">Debugging Interfaces</span></span>](debugging-interfaces.md)
