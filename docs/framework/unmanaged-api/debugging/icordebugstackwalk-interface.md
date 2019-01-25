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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fb58040394d99ae0c5a10672946fa5a6ead5e751
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54533421"
---
# <a name="icordebugstackwalk-interface"></a><span data-ttu-id="856db-102">ICorDebugStackWalk (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="856db-102">ICorDebugStackWalk Interface</span></span>
<span data-ttu-id="856db-103">Proporciona métodos para obtener los métodos administrados, o marcos, de la pila de un subproceso.</span><span class="sxs-lookup"><span data-stu-id="856db-103">Provides methods for getting the managed methods, or frames, on a thread’s stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="856db-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="856db-104">Methods</span></span>  
  
|<span data-ttu-id="856db-105">Método</span><span class="sxs-lookup"><span data-stu-id="856db-105">Method</span></span>|<span data-ttu-id="856db-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="856db-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="856db-107">GetContext (método)</span><span class="sxs-lookup"><span data-stu-id="856db-107">GetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md)|<span data-ttu-id="856db-108">Devuelve el contexto para el fotograma actual en el `ICorDebugStackWalk` objeto.</span><span class="sxs-lookup"><span data-stu-id="856db-108">Returns the context for the current frame in the `ICorDebugStackWalk` object.</span></span>|  
|[<span data-ttu-id="856db-109">SetContext (método)</span><span class="sxs-lookup"><span data-stu-id="856db-109">SetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-setcontext-method.md)|<span data-ttu-id="856db-110">Establece el `ICorDebugStackWalk` contexto actual del objeto en un contexto válido para el subproceso.</span><span class="sxs-lookup"><span data-stu-id="856db-110">Sets the `ICorDebugStackWalk` object’s current context to a valid context for the thread.</span></span>|  
|[<span data-ttu-id="856db-111">Next (método)</span><span class="sxs-lookup"><span data-stu-id="856db-111">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md)|<span data-ttu-id="856db-112">Mueve el `ICorDebugStackWalk` objeto al marco siguiente.</span><span class="sxs-lookup"><span data-stu-id="856db-112">Moves the `ICorDebugStackWalk` object to the next frame.</span></span>|  
|[<span data-ttu-id="856db-113">GetFrame (método)</span><span class="sxs-lookup"><span data-stu-id="856db-113">GetFrame Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getframe-method.md)|<span data-ttu-id="856db-114">Obtiene el marco actual el `ICorDebugStackWalk` objeto.</span><span class="sxs-lookup"><span data-stu-id="856db-114">Gets the current frame in the `ICorDebugStackWalk` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="856db-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="856db-115">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="856db-116">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="856db-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="856db-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="856db-117">Requirements</span></span>  
 <span data-ttu-id="856db-118">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="856db-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="856db-119">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="856db-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="856db-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="856db-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="856db-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="856db-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="856db-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="856db-122">See also</span></span>
- [<span data-ttu-id="856db-123">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="856db-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="856db-124">Depuración</span><span class="sxs-lookup"><span data-stu-id="856db-124">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
