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
ms.openlocfilehash: f4bacfe94178ea78b1c3afd15a2e100076c38a84
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777994"
---
# <a name="icordebugchain-interface"></a><span data-ttu-id="c14f1-102">Interfaz ICorDebugChain</span><span class="sxs-lookup"><span data-stu-id="c14f1-102">ICorDebugChain Interface</span></span>

<span data-ttu-id="c14f1-103">Representa un segmento de una pila de llamadas física o lógica.</span><span class="sxs-lookup"><span data-stu-id="c14f1-103">Represents a segment of a physical or logical call stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c14f1-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="c14f1-104">Methods</span></span>  
  
|<span data-ttu-id="c14f1-105">Método</span><span class="sxs-lookup"><span data-stu-id="c14f1-105">Method</span></span>|<span data-ttu-id="c14f1-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="c14f1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c14f1-107">EnumerateFrames (método)</span><span class="sxs-lookup"><span data-stu-id="c14f1-107">EnumerateFrames Method</span></span>](icordebugchain-enumerateframes-method.md)|<span data-ttu-id="c14f1-108">Obtiene un enumerador que contiene todos los marcos de pila administrados de la cadena, empezando por el fotograma más reciente.</span><span class="sxs-lookup"><span data-stu-id="c14f1-108">Gets an enumerator that contains all the managed stack frames in the chain, starting with the most recent frame.</span></span>|  
|[<span data-ttu-id="c14f1-109">GetActiveFrame (método)</span><span class="sxs-lookup"><span data-stu-id="c14f1-109">GetActiveFrame Method</span></span>](icordebugchain-getactiveframe-method.md)|<span data-ttu-id="c14f1-110">Obtiene el marco activo (es decir, el más reciente) de la cadena.</span><span class="sxs-lookup"><span data-stu-id="c14f1-110">Gets the active (that is, most recent) frame on the chain.</span></span>|  
|[<span data-ttu-id="c14f1-111">GetCallee (método)</span><span class="sxs-lookup"><span data-stu-id="c14f1-111">GetCallee Method</span></span>](icordebugchain-getcallee-method.md)|<span data-ttu-id="c14f1-112">Obtiene la cadena a la que llamó esta cadena.</span><span class="sxs-lookup"><span data-stu-id="c14f1-112">Gets the chain that was called by this chain.</span></span>|  
|[<span data-ttu-id="c14f1-113">GetCaller (método)</span><span class="sxs-lookup"><span data-stu-id="c14f1-113">GetCaller Method</span></span>](icordebugchain-getcaller-method.md)|<span data-ttu-id="c14f1-114">Obtiene la cadena que llamó a esta cadena.</span><span class="sxs-lookup"><span data-stu-id="c14f1-114">Gets the chain that called this chain.</span></span>|  
|[<span data-ttu-id="c14f1-115">GetContext (método)</span><span class="sxs-lookup"><span data-stu-id="c14f1-115">GetContext Method</span></span>](icordebugchain-getcontext-method.md)|<span data-ttu-id="c14f1-116">Sin implementar.</span><span class="sxs-lookup"><span data-stu-id="c14f1-116">Not implemented.</span></span>|  
|[<span data-ttu-id="c14f1-117">GetNext (método)</span><span class="sxs-lookup"><span data-stu-id="c14f1-117">GetNext Method</span></span>](icordebugchain-getnext-method.md)|<span data-ttu-id="c14f1-118">Obtiene la cadena de fotogramas siguiente para el subproceso.</span><span class="sxs-lookup"><span data-stu-id="c14f1-118">Gets the next chain of frames for the thread.</span></span>|  
|[<span data-ttu-id="c14f1-119">GetPrevious (método)</span><span class="sxs-lookup"><span data-stu-id="c14f1-119">GetPrevious Method</span></span>](icordebugchain-getprevious-method.md)|<span data-ttu-id="c14f1-120">Obtiene la cadena de fotogramas anterior para el subproceso.</span><span class="sxs-lookup"><span data-stu-id="c14f1-120">Gets the previous chain of frames for the thread.</span></span>|  
|[<span data-ttu-id="c14f1-121">GetReason (método)</span><span class="sxs-lookup"><span data-stu-id="c14f1-121">GetReason Method</span></span>](icordebugchain-getreason-method.md)|<span data-ttu-id="c14f1-122">Obtiene el motivo del Genesis de esta cadena de llamada.</span><span class="sxs-lookup"><span data-stu-id="c14f1-122">Gets the reason for the genesis of this calling chain.</span></span>|  
|[<span data-ttu-id="c14f1-123">GetRegisterSet (método)</span><span class="sxs-lookup"><span data-stu-id="c14f1-123">GetRegisterSet Method</span></span>](icordebugchain-getregisterset-method.md)|<span data-ttu-id="c14f1-124">Obtiene el conjunto de registros para la parte activa de esta cadena.</span><span class="sxs-lookup"><span data-stu-id="c14f1-124">Gets the register set for the active part of this chain.</span></span>|  
|[<span data-ttu-id="c14f1-125">GetStackRange (método)</span><span class="sxs-lookup"><span data-stu-id="c14f1-125">GetStackRange Method</span></span>](icordebugchain-getstackrange-method.md)|<span data-ttu-id="c14f1-126">Obtiene el intervalo de direcciones del segmento de pila para esta cadena.</span><span class="sxs-lookup"><span data-stu-id="c14f1-126">Gets the address range of the stack segment for this chain.</span></span>|  
|[<span data-ttu-id="c14f1-127">GetThread (método)</span><span class="sxs-lookup"><span data-stu-id="c14f1-127">GetThread Method</span></span>](icordebugchain-getthread-method.md)|<span data-ttu-id="c14f1-128">Obtiene el subproceso físico del que forma parte esta cadena de llamadas.</span><span class="sxs-lookup"><span data-stu-id="c14f1-128">Gets the physical thread this call chain is part of.</span></span>|  
|[<span data-ttu-id="c14f1-129">IsManaged (método)</span><span class="sxs-lookup"><span data-stu-id="c14f1-129">IsManaged Method</span></span>](icordebugchain-ismanaged-method.md)|<span data-ttu-id="c14f1-130">Obtiene un valor que indica si esta cadena ejecuta código administrado.</span><span class="sxs-lookup"><span data-stu-id="c14f1-130">Gets a value that indicates whether this chain is running managed code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c14f1-131">Notas</span><span class="sxs-lookup"><span data-stu-id="c14f1-131">Remarks</span></span>  
 <span data-ttu-id="c14f1-132">Los marcos de pila de una cadena ocupan el espacio de pila contiguo y comparten el mismo subproceso y contexto.</span><span class="sxs-lookup"><span data-stu-id="c14f1-132">The stack frames in a chain occupy contiguous stack space and share the same thread and context.</span></span> <span data-ttu-id="c14f1-133">Una cadena puede representar cadenas de código administradas o no administradas.</span><span class="sxs-lookup"><span data-stu-id="c14f1-133">A chain may represent either managed or unmanaged code chains.</span></span> <span data-ttu-id="c14f1-134">Una instancia de `ICorDebugChain` vacía representa una cadena de código no administrada.</span><span class="sxs-lookup"><span data-stu-id="c14f1-134">An empty `ICorDebugChain` instance represents an unmanaged code chain.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c14f1-135">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="c14f1-135">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c14f1-136">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="c14f1-136">Requirements</span></span>  
 <span data-ttu-id="c14f1-137">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c14f1-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c14f1-138">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c14f1-138">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c14f1-139">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c14f1-139">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c14f1-140">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c14f1-140">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c14f1-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="c14f1-141">See also</span></span>

- [<span data-ttu-id="c14f1-142">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="c14f1-142">Debugging Interfaces</span></span>](debugging-interfaces.md)
