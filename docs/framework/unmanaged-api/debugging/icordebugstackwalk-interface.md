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
ms.openlocfilehash: e33e9be112a6a10f89b88005496ce2e63dff2d54
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59080688"
---
# <a name="icordebugstackwalk-interface"></a><span data-ttu-id="8ba83-102">ICorDebugStackWalk (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8ba83-102">ICorDebugStackWalk Interface</span></span>
<span data-ttu-id="8ba83-103">Proporciona métodos para obtener los métodos administrados, o marcos, de la pila de un subproceso.</span><span class="sxs-lookup"><span data-stu-id="8ba83-103">Provides methods for getting the managed methods, or frames, on a thread’s stack.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8ba83-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="8ba83-104">Methods</span></span>  
  
|<span data-ttu-id="8ba83-105">Método</span><span class="sxs-lookup"><span data-stu-id="8ba83-105">Method</span></span>|<span data-ttu-id="8ba83-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="8ba83-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8ba83-107">Método GetContext</span><span class="sxs-lookup"><span data-stu-id="8ba83-107">GetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md)|<span data-ttu-id="8ba83-108">Devuelve el contexto para el fotograma actual en el `ICorDebugStackWalk` objeto.</span><span class="sxs-lookup"><span data-stu-id="8ba83-108">Returns the context for the current frame in the `ICorDebugStackWalk` object.</span></span>|  
|[<span data-ttu-id="8ba83-109">Método SetContext</span><span class="sxs-lookup"><span data-stu-id="8ba83-109">SetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-setcontext-method.md)|<span data-ttu-id="8ba83-110">Establece el `ICorDebugStackWalk` contexto actual del objeto en un contexto válido para el subproceso.</span><span class="sxs-lookup"><span data-stu-id="8ba83-110">Sets the `ICorDebugStackWalk` object’s current context to a valid context for the thread.</span></span>|  
|[<span data-ttu-id="8ba83-111">Método Next</span><span class="sxs-lookup"><span data-stu-id="8ba83-111">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md)|<span data-ttu-id="8ba83-112">Mueve el `ICorDebugStackWalk` objeto al marco siguiente.</span><span class="sxs-lookup"><span data-stu-id="8ba83-112">Moves the `ICorDebugStackWalk` object to the next frame.</span></span>|  
|[<span data-ttu-id="8ba83-113">Método GetFrame</span><span class="sxs-lookup"><span data-stu-id="8ba83-113">GetFrame Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getframe-method.md)|<span data-ttu-id="8ba83-114">Obtiene el marco actual el `ICorDebugStackWalk` objeto.</span><span class="sxs-lookup"><span data-stu-id="8ba83-114">Gets the current frame in the `ICorDebugStackWalk` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8ba83-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8ba83-115">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8ba83-116">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="8ba83-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ba83-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8ba83-117">Requirements</span></span>  
 <span data-ttu-id="8ba83-118">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8ba83-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ba83-119">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8ba83-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8ba83-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8ba83-120">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="8ba83-121">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="8ba83-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8ba83-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="8ba83-122">See also</span></span>

- [<span data-ttu-id="8ba83-123">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="8ba83-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="8ba83-124">Depuración</span><span class="sxs-lookup"><span data-stu-id="8ba83-124">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
