---
title: Interfaz ICorDebugChain
ms.date: 03/30/2017
api_name:
- ICorDebugChain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain
helpviewer_keywords:
- ICorDebugChain interface [.NET Framework debugging]
ms.assetid: f671f519-1cb3-4ae5-b9f1-abc5e783459f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 01dded47fca26df11781153eb45693057a25ad01
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59220713"
---
# <a name="icordebugchain-interface"></a><span data-ttu-id="3b55e-102">Interfaz ICorDebugChain</span><span class="sxs-lookup"><span data-stu-id="3b55e-102">ICorDebugChain Interface</span></span>

<span data-ttu-id="3b55e-103">Representa un segmento de una pila de llamadas física o lógica.</span><span class="sxs-lookup"><span data-stu-id="3b55e-103">Represents a segment of a physical or logical call stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3b55e-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="3b55e-104">Methods</span></span>  
  
|<span data-ttu-id="3b55e-105">Método</span><span class="sxs-lookup"><span data-stu-id="3b55e-105">Method</span></span>|<span data-ttu-id="3b55e-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="3b55e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3b55e-107">Método EnumerateFrames</span><span class="sxs-lookup"><span data-stu-id="3b55e-107">EnumerateFrames Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-enumerateframes-method.md)|<span data-ttu-id="3b55e-108">Obtiene un enumerador que contiene todos los marcos de pila administrados de la cadena, empezando por el marco más reciente.</span><span class="sxs-lookup"><span data-stu-id="3b55e-108">Gets an enumerator that contains all the managed stack frames in the chain, starting with the most recent frame.</span></span>|  
|[<span data-ttu-id="3b55e-109">Método GetActiveFrame</span><span class="sxs-lookup"><span data-stu-id="3b55e-109">GetActiveFrame Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getactiveframe-method.md)|<span data-ttu-id="3b55e-110">Obtiene el activo (es decir, más reciente) marco en la cadena.</span><span class="sxs-lookup"><span data-stu-id="3b55e-110">Gets the active (that is, most recent) frame on the chain.</span></span>|  
|[<span data-ttu-id="3b55e-111">Método GetCallee</span><span class="sxs-lookup"><span data-stu-id="3b55e-111">GetCallee Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcallee-method.md)|<span data-ttu-id="3b55e-112">Obtiene la cadena que se llamó por esta cadena.</span><span class="sxs-lookup"><span data-stu-id="3b55e-112">Gets the chain that was called by this chain.</span></span>|  
|[<span data-ttu-id="3b55e-113">Método GetCaller</span><span class="sxs-lookup"><span data-stu-id="3b55e-113">GetCaller Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcaller-method.md)|<span data-ttu-id="3b55e-114">Obtiene la cadena que llamó esta cadena.</span><span class="sxs-lookup"><span data-stu-id="3b55e-114">Gets the chain that called this chain.</span></span>|  
|[<span data-ttu-id="3b55e-115">Método GetContext</span><span class="sxs-lookup"><span data-stu-id="3b55e-115">GetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getcontext-method.md)|<span data-ttu-id="3b55e-116">Sin implementar.</span><span class="sxs-lookup"><span data-stu-id="3b55e-116">Not implemented.</span></span>|  
|[<span data-ttu-id="3b55e-117">Método GetNext</span><span class="sxs-lookup"><span data-stu-id="3b55e-117">GetNext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getnext-method.md)|<span data-ttu-id="3b55e-118">Obtiene la siguiente cadena de marcos del subproceso.</span><span class="sxs-lookup"><span data-stu-id="3b55e-118">Gets the next chain of frames for the thread.</span></span>|  
|[<span data-ttu-id="3b55e-119">Método GetPrevious</span><span class="sxs-lookup"><span data-stu-id="3b55e-119">GetPrevious Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getprevious-method.md)|<span data-ttu-id="3b55e-120">Obtiene la cadena anterior de marcos del subproceso.</span><span class="sxs-lookup"><span data-stu-id="3b55e-120">Gets the previous chain of frames for the thread.</span></span>|  
|[<span data-ttu-id="3b55e-121">Método GetReason</span><span class="sxs-lookup"><span data-stu-id="3b55e-121">GetReason Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getreason-method.md)|<span data-ttu-id="3b55e-122">Obtiene la razón para la génesis de esta cadena de llamada.</span><span class="sxs-lookup"><span data-stu-id="3b55e-122">Gets the reason for the genesis of this calling chain.</span></span>|  
|[<span data-ttu-id="3b55e-123">Método GetRegisterSet</span><span class="sxs-lookup"><span data-stu-id="3b55e-123">GetRegisterSet Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getregisterset-method.md)|<span data-ttu-id="3b55e-124">Obtiene el conjunto de registros para la parte activa de esta cadena.</span><span class="sxs-lookup"><span data-stu-id="3b55e-124">Gets the register set for the active part of this chain.</span></span>|  
|[<span data-ttu-id="3b55e-125">Método GetStackRange</span><span class="sxs-lookup"><span data-stu-id="3b55e-125">GetStackRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getstackrange-method.md)|<span data-ttu-id="3b55e-126">Obtiene el intervalo de direcciones del segmento de pila para esta cadena.</span><span class="sxs-lookup"><span data-stu-id="3b55e-126">Gets the address range of the stack segment for this chain.</span></span>|  
|[<span data-ttu-id="3b55e-127">Método GetThread</span><span class="sxs-lookup"><span data-stu-id="3b55e-127">GetThread Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-getthread-method.md)|<span data-ttu-id="3b55e-128">Obtiene el subproceso físico que esta cadena de llamada es parte de.</span><span class="sxs-lookup"><span data-stu-id="3b55e-128">Gets the physical thread this call chain is part of.</span></span>|  
|[<span data-ttu-id="3b55e-129">Método IsManaged</span><span class="sxs-lookup"><span data-stu-id="3b55e-129">IsManaged Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-ismanaged-method.md)|<span data-ttu-id="3b55e-130">Obtiene un valor que indica si esta cadena ejecuta código administrado.</span><span class="sxs-lookup"><span data-stu-id="3b55e-130">Gets a value that indicates whether this chain is running managed code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3b55e-131">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3b55e-131">Remarks</span></span>  
 <span data-ttu-id="3b55e-132">Los marcos de pila en una cadena ocupan espacio de pila contiguo y comparten el mismo subproceso y contexto.</span><span class="sxs-lookup"><span data-stu-id="3b55e-132">The stack frames in a chain occupy contiguous stack space and share the same thread and context.</span></span> <span data-ttu-id="3b55e-133">Una cadena puede representar cualquier cadenas de código administrado o no administrado.</span><span class="sxs-lookup"><span data-stu-id="3b55e-133">A chain may represent either managed or unmanaged code chains.</span></span> <span data-ttu-id="3b55e-134">Un valor vacío `ICorDebugChain` instancia representa una cadena de código no administrado.</span><span class="sxs-lookup"><span data-stu-id="3b55e-134">An empty `ICorDebugChain` instance represents an unmanaged code chain.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3b55e-135">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="3b55e-135">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b55e-136">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3b55e-136">Requirements</span></span>  
 <span data-ttu-id="3b55e-137">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3b55e-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b55e-138">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3b55e-138">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3b55e-139">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3b55e-139">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="3b55e-140">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="3b55e-140">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3b55e-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="3b55e-141">See also</span></span>

- [<span data-ttu-id="3b55e-142">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="3b55e-142">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
