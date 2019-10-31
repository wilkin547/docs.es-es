---
title: ICorDebugRuntimeUnwindableFrame (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugUnwindableFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugUnwindableFrame
helpviewer_keywords:
- ICorDebugUnwindableFrame interface [.NET Framework debugging]
ms.assetid: cd6a3982-6ed3-4909-808d-a66055e813e0
topic_type:
- apiref
ms.openlocfilehash: 2902744b6af3c7b2bd4def73b04807ce3333a8a1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131887"
---
# <a name="icordebugruntimeunwindableframe-interface"></a><span data-ttu-id="485eb-102">ICorDebugRuntimeUnwindableFrame (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="485eb-102">ICorDebugRuntimeUnwindableFrame Interface</span></span>
<span data-ttu-id="485eb-103">Proporciona compatibilidad para métodos no administrados que necesitan que Common Language Runtime (CLR) desenrede un marco.</span><span class="sxs-lookup"><span data-stu-id="485eb-103">Provides support for unmanaged methods that require the common language runtime (CLR) to unwind a frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="485eb-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="485eb-104">Remarks</span></span>  
 <span data-ttu-id="485eb-105">`ICorDebugRuntimeUnwindableFrame` es una versión especializada de la interfaz ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="485eb-105">`ICorDebugRuntimeUnwindableFrame` is a specialized version of the ICorDebugFrame interface.</span></span> <span data-ttu-id="485eb-106">Lo usan los métodos no administrados que requieren que el Runtime desenrede un marco en la pila actual.</span><span class="sxs-lookup"><span data-stu-id="485eb-106">It is used by unmanaged methods that require the runtime to unwind a frame on the current stack.</span></span> <span data-ttu-id="485eb-107">Las convenciones de desenredado existentes no funcionan, ya que no utilizan código compilado JIT.</span><span class="sxs-lookup"><span data-stu-id="485eb-107">Existing unwinding conventions do not work, because they do not use JIT-compiled code.</span></span> <span data-ttu-id="485eb-108">Cuando el depurador ve un marco que no se pueda desenredar, debe utilizar el método [ICorDebugStackWalk:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md) para desenredarlo, pero debe realizar la inspección.</span><span class="sxs-lookup"><span data-stu-id="485eb-108">When the debugger sees an unwindable frame, it should use the [ICorDebugStackWalk::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md) method to unwind it, but it should perform inspection itself.</span></span> <span data-ttu-id="485eb-109">Cuando el depurador recibe un `ICorDebugRuntimeUnwindableFrame`, puede llamar al método [ICorDebugStackWalk:: getContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) para recuperar el contexto del marco.</span><span class="sxs-lookup"><span data-stu-id="485eb-109">When the debugger receives an `ICorDebugRuntimeUnwindableFrame`, it can call the [ICorDebugStackWalk::GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) method to retrieve the context of the frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="485eb-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="485eb-110">Requirements</span></span>  
 <span data-ttu-id="485eb-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="485eb-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="485eb-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="485eb-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="485eb-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="485eb-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="485eb-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="485eb-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="485eb-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="485eb-115">See also</span></span>

- [<span data-ttu-id="485eb-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="485eb-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="485eb-117">Depuración</span><span class="sxs-lookup"><span data-stu-id="485eb-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
