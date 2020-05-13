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
ms.openlocfilehash: 5f71dfcdffaaa683ca4f2abebaa99115ef90e0ff
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378906"
---
# <a name="icordebugstackwalk-interface"></a><span data-ttu-id="c5a72-102">ICorDebugStackWalk (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c5a72-102">ICorDebugStackWalk Interface</span></span>
<span data-ttu-id="c5a72-103">Proporciona métodos para obtener los métodos administrados, o marcos, de la pila de un subproceso.</span><span class="sxs-lookup"><span data-stu-id="c5a72-103">Provides methods for getting the managed methods, or frames, on a thread’s stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c5a72-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="c5a72-104">Methods</span></span>  
  
|<span data-ttu-id="c5a72-105">Método</span><span class="sxs-lookup"><span data-stu-id="c5a72-105">Method</span></span>|<span data-ttu-id="c5a72-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="c5a72-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c5a72-107">Método GetContext</span><span class="sxs-lookup"><span data-stu-id="c5a72-107">GetContext Method</span></span>](icordebugstackwalk-getcontext-method.md)|<span data-ttu-id="c5a72-108">Devuelve el contexto del marco actual del `ICorDebugStackWalk` objeto.</span><span class="sxs-lookup"><span data-stu-id="c5a72-108">Returns the context for the current frame in the `ICorDebugStackWalk` object.</span></span>|  
|[<span data-ttu-id="c5a72-109">Método SetContext</span><span class="sxs-lookup"><span data-stu-id="c5a72-109">SetContext Method</span></span>](icordebugstackwalk-setcontext-method.md)|<span data-ttu-id="c5a72-110">Establece el `ICorDebugStackWalk` contexto actual del objeto en un contexto válido para el subproceso.</span><span class="sxs-lookup"><span data-stu-id="c5a72-110">Sets the `ICorDebugStackWalk` object’s current context to a valid context for the thread.</span></span>|  
|[<span data-ttu-id="c5a72-111">Next (Método)</span><span class="sxs-lookup"><span data-stu-id="c5a72-111">Next Method</span></span>](icordebugstackwalk-next-method.md)|<span data-ttu-id="c5a72-112">Mueve el `ICorDebugStackWalk` objeto al siguiente fotograma.</span><span class="sxs-lookup"><span data-stu-id="c5a72-112">Moves the `ICorDebugStackWalk` object to the next frame.</span></span>|  
|[<span data-ttu-id="c5a72-113">Método GetFrame</span><span class="sxs-lookup"><span data-stu-id="c5a72-113">GetFrame Method</span></span>](icordebugstackwalk-getframe-method.md)|<span data-ttu-id="c5a72-114">Obtiene el marco actual del `ICorDebugStackWalk` objeto.</span><span class="sxs-lookup"><span data-stu-id="c5a72-114">Gets the current frame in the `ICorDebugStackWalk` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c5a72-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c5a72-115">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c5a72-116">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="c5a72-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5a72-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c5a72-117">Requirements</span></span>  
 <span data-ttu-id="c5a72-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c5a72-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5a72-119">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c5a72-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c5a72-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c5a72-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c5a72-121">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5a72-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5a72-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c5a72-122">See also</span></span>

- [<span data-ttu-id="c5a72-123">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="c5a72-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="c5a72-124">Depuración</span><span class="sxs-lookup"><span data-stu-id="c5a72-124">Debugging</span></span>](index.md)
