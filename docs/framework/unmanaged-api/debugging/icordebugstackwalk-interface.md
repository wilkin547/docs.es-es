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
ms.openlocfilehash: a6283d699263dc9b79e457010f31923f77443129
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791877"
---
# <a name="icordebugstackwalk-interface"></a><span data-ttu-id="a1ade-102">ICorDebugStackWalk (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a1ade-102">ICorDebugStackWalk Interface</span></span>
<span data-ttu-id="a1ade-103">Proporciona métodos para obtener los métodos administrados, o marcos, de la pila de un subproceso.</span><span class="sxs-lookup"><span data-stu-id="a1ade-103">Provides methods for getting the managed methods, or frames, on a thread’s stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a1ade-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="a1ade-104">Methods</span></span>  
  
|<span data-ttu-id="a1ade-105">Método</span><span class="sxs-lookup"><span data-stu-id="a1ade-105">Method</span></span>|<span data-ttu-id="a1ade-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="a1ade-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a1ade-107">GetContext (método)</span><span class="sxs-lookup"><span data-stu-id="a1ade-107">GetContext Method</span></span>](icordebugstackwalk-getcontext-method.md)|<span data-ttu-id="a1ade-108">Devuelve el contexto del marco actual en el objeto `ICorDebugStackWalk`.</span><span class="sxs-lookup"><span data-stu-id="a1ade-108">Returns the context for the current frame in the `ICorDebugStackWalk` object.</span></span>|  
|[<span data-ttu-id="a1ade-109">SetContext (método)</span><span class="sxs-lookup"><span data-stu-id="a1ade-109">SetContext Method</span></span>](icordebugstackwalk-setcontext-method.md)|<span data-ttu-id="a1ade-110">Establece el contexto actual del objeto `ICorDebugStackWalk` en un contexto válido para el subproceso.</span><span class="sxs-lookup"><span data-stu-id="a1ade-110">Sets the `ICorDebugStackWalk` object’s current context to a valid context for the thread.</span></span>|  
|[<span data-ttu-id="a1ade-111">Next (método)</span><span class="sxs-lookup"><span data-stu-id="a1ade-111">Next Method</span></span>](icordebugstackwalk-next-method.md)|<span data-ttu-id="a1ade-112">Mueve el objeto de `ICorDebugStackWalk` al fotograma siguiente.</span><span class="sxs-lookup"><span data-stu-id="a1ade-112">Moves the `ICorDebugStackWalk` object to the next frame.</span></span>|  
|[<span data-ttu-id="a1ade-113">GetFrame (método)</span><span class="sxs-lookup"><span data-stu-id="a1ade-113">GetFrame Method</span></span>](icordebugstackwalk-getframe-method.md)|<span data-ttu-id="a1ade-114">Obtiene el marco actual del objeto `ICorDebugStackWalk`.</span><span class="sxs-lookup"><span data-stu-id="a1ade-114">Gets the current frame in the `ICorDebugStackWalk` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a1ade-115">Notas</span><span class="sxs-lookup"><span data-stu-id="a1ade-115">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a1ade-116">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="a1ade-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1ade-117">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="a1ade-117">Requirements</span></span>  
 <span data-ttu-id="a1ade-118">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1ade-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1ade-119">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a1ade-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a1ade-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a1ade-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a1ade-121">**.NET Framework versiones:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1ade-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1ade-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="a1ade-122">See also</span></span>

- [<span data-ttu-id="a1ade-123">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="a1ade-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="a1ade-124">Depuración</span><span class="sxs-lookup"><span data-stu-id="a1ade-124">Debugging</span></span>](index.md)
