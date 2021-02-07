---
description: 'Más información sobre: ICorDebugStackWalk (interfaz)'
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
ms.openlocfilehash: 27dcdfc90829a3a28d81ad28dce0cd4d1d674948
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99738096"
---
# <a name="icordebugstackwalk-interface"></a><span data-ttu-id="fa309-103">ICorDebugStackWalk (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fa309-103">ICorDebugStackWalk Interface</span></span>

<span data-ttu-id="fa309-104">Proporciona métodos para obtener los métodos administrados, o marcos, de la pila de un subproceso.</span><span class="sxs-lookup"><span data-stu-id="fa309-104">Provides methods for getting the managed methods, or frames, on a thread’s stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fa309-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="fa309-105">Methods</span></span>  
  
|<span data-ttu-id="fa309-106">Método</span><span class="sxs-lookup"><span data-stu-id="fa309-106">Method</span></span>|<span data-ttu-id="fa309-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="fa309-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fa309-108">Método GetContext</span><span class="sxs-lookup"><span data-stu-id="fa309-108">GetContext Method</span></span>](icordebugstackwalk-getcontext-method.md)|<span data-ttu-id="fa309-109">Devuelve el contexto del marco actual del `ICorDebugStackWalk` objeto.</span><span class="sxs-lookup"><span data-stu-id="fa309-109">Returns the context for the current frame in the `ICorDebugStackWalk` object.</span></span>|  
|[<span data-ttu-id="fa309-110">Método SetContext</span><span class="sxs-lookup"><span data-stu-id="fa309-110">SetContext Method</span></span>](icordebugstackwalk-setcontext-method.md)|<span data-ttu-id="fa309-111">Establece el `ICorDebugStackWalk` contexto actual del objeto en un contexto válido para el subproceso.</span><span class="sxs-lookup"><span data-stu-id="fa309-111">Sets the `ICorDebugStackWalk` object’s current context to a valid context for the thread.</span></span>|  
|[<span data-ttu-id="fa309-112">Next (método)</span><span class="sxs-lookup"><span data-stu-id="fa309-112">Next Method</span></span>](icordebugstackwalk-next-method.md)|<span data-ttu-id="fa309-113">Mueve el `ICorDebugStackWalk` objeto al siguiente fotograma.</span><span class="sxs-lookup"><span data-stu-id="fa309-113">Moves the `ICorDebugStackWalk` object to the next frame.</span></span>|  
|[<span data-ttu-id="fa309-114">Método GetFrame</span><span class="sxs-lookup"><span data-stu-id="fa309-114">GetFrame Method</span></span>](icordebugstackwalk-getframe-method.md)|<span data-ttu-id="fa309-115">Obtiene el marco actual del `ICorDebugStackWalk` objeto.</span><span class="sxs-lookup"><span data-stu-id="fa309-115">Gets the current frame in the `ICorDebugStackWalk` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fa309-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="fa309-116">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fa309-117">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="fa309-117">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa309-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fa309-118">Requirements</span></span>  

 <span data-ttu-id="fa309-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa309-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa309-120">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fa309-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fa309-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fa309-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fa309-122">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa309-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa309-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="fa309-123">See also</span></span>

- [<span data-ttu-id="fa309-124">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="fa309-124">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="fa309-125">Depuración</span><span class="sxs-lookup"><span data-stu-id="fa309-125">Debugging</span></span>](index.md)
