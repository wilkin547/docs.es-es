---
description: 'Más información sobre: interfaz ICorDebugChain'
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
ms.openlocfilehash: 391c9a3e54d06d303728da5ab7f105bc8e2558ef
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99661212"
---
# <a name="icordebugchain-interface"></a><span data-ttu-id="26778-103">Interfaz ICorDebugChain</span><span class="sxs-lookup"><span data-stu-id="26778-103">ICorDebugChain Interface</span></span>

<span data-ttu-id="26778-104">Representa un segmento de una pila de llamadas física o lógica.</span><span class="sxs-lookup"><span data-stu-id="26778-104">Represents a segment of a physical or logical call stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="26778-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="26778-105">Methods</span></span>  
  
|<span data-ttu-id="26778-106">Método</span><span class="sxs-lookup"><span data-stu-id="26778-106">Method</span></span>|<span data-ttu-id="26778-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="26778-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="26778-108">Método EnumerateFrames</span><span class="sxs-lookup"><span data-stu-id="26778-108">EnumerateFrames Method</span></span>](icordebugchain-enumerateframes-method.md)|<span data-ttu-id="26778-109">Obtiene un enumerador que contiene todos los marcos de pila administrados de la cadena, empezando por el fotograma más reciente.</span><span class="sxs-lookup"><span data-stu-id="26778-109">Gets an enumerator that contains all the managed stack frames in the chain, starting with the most recent frame.</span></span>|  
|[<span data-ttu-id="26778-110">GetActiveFrame (Método)</span><span class="sxs-lookup"><span data-stu-id="26778-110">GetActiveFrame Method</span></span>](icordebugchain-getactiveframe-method.md)|<span data-ttu-id="26778-111">Obtiene el marco activo (es decir, el más reciente) de la cadena.</span><span class="sxs-lookup"><span data-stu-id="26778-111">Gets the active (that is, most recent) frame on the chain.</span></span>|  
|[<span data-ttu-id="26778-112">Método GetCallee</span><span class="sxs-lookup"><span data-stu-id="26778-112">GetCallee Method</span></span>](icordebugchain-getcallee-method.md)|<span data-ttu-id="26778-113">Obtiene la cadena a la que llamó esta cadena.</span><span class="sxs-lookup"><span data-stu-id="26778-113">Gets the chain that was called by this chain.</span></span>|  
|[<span data-ttu-id="26778-114">Método GetCaller</span><span class="sxs-lookup"><span data-stu-id="26778-114">GetCaller Method</span></span>](icordebugchain-getcaller-method.md)|<span data-ttu-id="26778-115">Obtiene la cadena que llamó a esta cadena.</span><span class="sxs-lookup"><span data-stu-id="26778-115">Gets the chain that called this chain.</span></span>|  
|[<span data-ttu-id="26778-116">Método GetContext</span><span class="sxs-lookup"><span data-stu-id="26778-116">GetContext Method</span></span>](icordebugchain-getcontext-method.md)|<span data-ttu-id="26778-117">Sin implementar.</span><span class="sxs-lookup"><span data-stu-id="26778-117">Not implemented.</span></span>|  
|[<span data-ttu-id="26778-118">Método GetNext</span><span class="sxs-lookup"><span data-stu-id="26778-118">GetNext Method</span></span>](icordebugchain-getnext-method.md)|<span data-ttu-id="26778-119">Obtiene la cadena de fotogramas siguiente para el subproceso.</span><span class="sxs-lookup"><span data-stu-id="26778-119">Gets the next chain of frames for the thread.</span></span>|  
|[<span data-ttu-id="26778-120">Método GetPrevious</span><span class="sxs-lookup"><span data-stu-id="26778-120">GetPrevious Method</span></span>](icordebugchain-getprevious-method.md)|<span data-ttu-id="26778-121">Obtiene la cadena de fotogramas anterior para el subproceso.</span><span class="sxs-lookup"><span data-stu-id="26778-121">Gets the previous chain of frames for the thread.</span></span>|  
|[<span data-ttu-id="26778-122">Método GetReason</span><span class="sxs-lookup"><span data-stu-id="26778-122">GetReason Method</span></span>](icordebugchain-getreason-method.md)|<span data-ttu-id="26778-123">Obtiene el motivo del Genesis de esta cadena de llamada.</span><span class="sxs-lookup"><span data-stu-id="26778-123">Gets the reason for the genesis of this calling chain.</span></span>|  
|[<span data-ttu-id="26778-124">GetRegisterSet (Método)</span><span class="sxs-lookup"><span data-stu-id="26778-124">GetRegisterSet Method</span></span>](icordebugchain-getregisterset-method.md)|<span data-ttu-id="26778-125">Obtiene el conjunto de registros para la parte activa de esta cadena.</span><span class="sxs-lookup"><span data-stu-id="26778-125">Gets the register set for the active part of this chain.</span></span>|  
|[<span data-ttu-id="26778-126">GetStackRange (Método)</span><span class="sxs-lookup"><span data-stu-id="26778-126">GetStackRange Method</span></span>](icordebugchain-getstackrange-method.md)|<span data-ttu-id="26778-127">Obtiene el intervalo de direcciones del segmento de pila para esta cadena.</span><span class="sxs-lookup"><span data-stu-id="26778-127">Gets the address range of the stack segment for this chain.</span></span>|  
|[<span data-ttu-id="26778-128">Método GetThread</span><span class="sxs-lookup"><span data-stu-id="26778-128">GetThread Method</span></span>](icordebugchain-getthread-method.md)|<span data-ttu-id="26778-129">Obtiene el subproceso físico del que forma parte esta cadena de llamadas.</span><span class="sxs-lookup"><span data-stu-id="26778-129">Gets the physical thread this call chain is part of.</span></span>|  
|[<span data-ttu-id="26778-130">Método IsManaged</span><span class="sxs-lookup"><span data-stu-id="26778-130">IsManaged Method</span></span>](icordebugchain-ismanaged-method.md)|<span data-ttu-id="26778-131">Obtiene un valor que indica si esta cadena ejecuta código administrado.</span><span class="sxs-lookup"><span data-stu-id="26778-131">Gets a value that indicates whether this chain is running managed code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="26778-132">Observaciones</span><span class="sxs-lookup"><span data-stu-id="26778-132">Remarks</span></span>  

 <span data-ttu-id="26778-133">Los marcos de pila de una cadena ocupan el espacio de pila contiguo y comparten el mismo subproceso y contexto.</span><span class="sxs-lookup"><span data-stu-id="26778-133">The stack frames in a chain occupy contiguous stack space and share the same thread and context.</span></span> <span data-ttu-id="26778-134">Una cadena puede representar cadenas de código administradas o no administradas.</span><span class="sxs-lookup"><span data-stu-id="26778-134">A chain may represent either managed or unmanaged code chains.</span></span> <span data-ttu-id="26778-135">Una `ICorDebugChain` instancia vacía representa una cadena de código no administrada.</span><span class="sxs-lookup"><span data-stu-id="26778-135">An empty `ICorDebugChain` instance represents an unmanaged code chain.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="26778-136">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="26778-136">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26778-137">Requisitos</span><span class="sxs-lookup"><span data-stu-id="26778-137">Requirements</span></span>  

 <span data-ttu-id="26778-138">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="26778-138">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26778-139">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="26778-139">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="26778-140">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="26778-140">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="26778-141">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26778-141">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26778-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="26778-142">See also</span></span>

- [<span data-ttu-id="26778-143">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="26778-143">Debugging Interfaces</span></span>](debugging-interfaces.md)
