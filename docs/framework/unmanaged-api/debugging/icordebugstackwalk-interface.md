---
title: ICorDebugStackWalk (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk
helpviewer_keywords:
- ICorDebugStackWalk interface [.NET Framework debugging]
ms.assetid: 16d695e8-975d-431b-8421-e9e6c3e3f476
topic_type:
- apiref
ms.openlocfilehash: 48f1b485b6dfa8fd898f6ea00eee2d7b397deba6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131868"
---
# <a name="icordebugstackwalk-interface"></a><span data-ttu-id="de9e2-102">ICorDebugStackWalk (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="de9e2-102">ICorDebugStackWalk Interface</span></span>
<span data-ttu-id="de9e2-103">Proporciona métodos para obtener los métodos administrados, o marcos, de la pila de un subproceso.</span><span class="sxs-lookup"><span data-stu-id="de9e2-103">Provides methods for getting the managed methods, or frames, on a thread’s stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="de9e2-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="de9e2-104">Methods</span></span>  
  
|<span data-ttu-id="de9e2-105">Método</span><span class="sxs-lookup"><span data-stu-id="de9e2-105">Method</span></span>|<span data-ttu-id="de9e2-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="de9e2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="de9e2-107">GetContext (método)</span><span class="sxs-lookup"><span data-stu-id="de9e2-107">GetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md)|<span data-ttu-id="de9e2-108">Devuelve el contexto del marco actual en el objeto `ICorDebugStackWalk`.</span><span class="sxs-lookup"><span data-stu-id="de9e2-108">Returns the context for the current frame in the `ICorDebugStackWalk` object.</span></span>|  
|[<span data-ttu-id="de9e2-109">SetContext (método)</span><span class="sxs-lookup"><span data-stu-id="de9e2-109">SetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-setcontext-method.md)|<span data-ttu-id="de9e2-110">Establece el contexto actual del objeto `ICorDebugStackWalk` en un contexto válido para el subproceso.</span><span class="sxs-lookup"><span data-stu-id="de9e2-110">Sets the `ICorDebugStackWalk` object’s current context to a valid context for the thread.</span></span>|  
|[<span data-ttu-id="de9e2-111">Next (método)</span><span class="sxs-lookup"><span data-stu-id="de9e2-111">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md)|<span data-ttu-id="de9e2-112">Mueve el objeto de `ICorDebugStackWalk` al fotograma siguiente.</span><span class="sxs-lookup"><span data-stu-id="de9e2-112">Moves the `ICorDebugStackWalk` object to the next frame.</span></span>|  
|[<span data-ttu-id="de9e2-113">GetFrame (método)</span><span class="sxs-lookup"><span data-stu-id="de9e2-113">GetFrame Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getframe-method.md)|<span data-ttu-id="de9e2-114">Obtiene el marco actual del objeto `ICorDebugStackWalk`.</span><span class="sxs-lookup"><span data-stu-id="de9e2-114">Gets the current frame in the `ICorDebugStackWalk` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="de9e2-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="de9e2-115">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="de9e2-116">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="de9e2-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de9e2-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="de9e2-117">Requirements</span></span>  
 <span data-ttu-id="de9e2-118">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="de9e2-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de9e2-119">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="de9e2-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="de9e2-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="de9e2-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="de9e2-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de9e2-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de9e2-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="de9e2-122">See also</span></span>

- [<span data-ttu-id="de9e2-123">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="de9e2-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="de9e2-124">Depuración</span><span class="sxs-lookup"><span data-stu-id="de9e2-124">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
