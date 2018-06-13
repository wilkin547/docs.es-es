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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3e2edc64cd9067ed89ae0e309c6a5630319ce835
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33420604"
---
# <a name="icordebugruntimeunwindableframe-interface"></a><span data-ttu-id="7ad90-102">ICorDebugRuntimeUnwindableFrame (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7ad90-102">ICorDebugRuntimeUnwindableFrame Interface</span></span>
<span data-ttu-id="7ad90-103">Proporciona compatibilidad para métodos no administrados que necesitan que Common Language Runtime (CLR) desenrede un marco.</span><span class="sxs-lookup"><span data-stu-id="7ad90-103">Provides support for unmanaged methods that require the common language runtime (CLR) to unwind a frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7ad90-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7ad90-104">Remarks</span></span>  
 <span data-ttu-id="7ad90-105">`ICorDebugRuntimeUnwindableFrame` es una versión especializada de ICorDebugFrame (interfaz).</span><span class="sxs-lookup"><span data-stu-id="7ad90-105">`ICorDebugRuntimeUnwindableFrame` is a specialized version of the ICorDebugFrame interface.</span></span> <span data-ttu-id="7ad90-106">Se utiliza por métodos no administrados que necesitan que el runtime desenrede un marco en la pila actual.</span><span class="sxs-lookup"><span data-stu-id="7ad90-106">It is used by unmanaged methods that require the runtime to unwind a frame on the current stack.</span></span> <span data-ttu-id="7ad90-107">Convenciones de desenredado existentes no funcionan, ya que no usan código compilado JIT.</span><span class="sxs-lookup"><span data-stu-id="7ad90-107">Existing unwinding conventions do not work, because they do not use JIT-compiled code.</span></span> <span data-ttu-id="7ad90-108">Cuando el depurador ve un marco no se pueden desenredar, debe usar el [ICorDebugStackWalk:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md) método desenrede, pero debe realizar la inspección.</span><span class="sxs-lookup"><span data-stu-id="7ad90-108">When the debugger sees an unwindable frame, it should use the [ICorDebugStackWalk::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md) method to unwind it, but it should perform inspection itself.</span></span> <span data-ttu-id="7ad90-109">Cuando el depurador recibe un `ICorDebugRuntimeUnwindableFrame`, puede llamar a la [ICorDebugStackWalk:: GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) método para recuperar el contexto del marco.</span><span class="sxs-lookup"><span data-stu-id="7ad90-109">When the debugger receives an `ICorDebugRuntimeUnwindableFrame`, it can call the [ICorDebugStackWalk::GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) method to retrieve the context of the frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ad90-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7ad90-110">Requirements</span></span>  
 <span data-ttu-id="7ad90-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ad90-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ad90-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7ad90-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7ad90-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7ad90-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7ad90-114">**Versiones de .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ad90-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ad90-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="7ad90-115">See Also</span></span>  
 [<span data-ttu-id="7ad90-116">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="7ad90-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="7ad90-117">Depuración</span><span class="sxs-lookup"><span data-stu-id="7ad90-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
