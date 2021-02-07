---
description: 'Más información acerca de: interfaz Icordebugruntimeunwindableframe ('
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
ms.openlocfilehash: e83ede8265a400b30f2202115bf47aed6ea43e5e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99717815"
---
# <a name="icordebugruntimeunwindableframe-interface"></a><span data-ttu-id="5b4c5-103">ICorDebugRuntimeUnwindableFrame (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5b4c5-103">ICorDebugRuntimeUnwindableFrame Interface</span></span>

<span data-ttu-id="5b4c5-104">Proporciona compatibilidad para métodos no administrados que necesitan que Common Language Runtime (CLR) desenrede un marco.</span><span class="sxs-lookup"><span data-stu-id="5b4c5-104">Provides support for unmanaged methods that require the common language runtime (CLR) to unwind a frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5b4c5-105">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5b4c5-105">Remarks</span></span>  

 <span data-ttu-id="5b4c5-106">`ICorDebugRuntimeUnwindableFrame` es una versión especializada de la interfaz ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="5b4c5-106">`ICorDebugRuntimeUnwindableFrame` is a specialized version of the ICorDebugFrame interface.</span></span> <span data-ttu-id="5b4c5-107">Lo usan los métodos no administrados que requieren que el Runtime desenrede un marco en la pila actual.</span><span class="sxs-lookup"><span data-stu-id="5b4c5-107">It is used by unmanaged methods that require the runtime to unwind a frame on the current stack.</span></span> <span data-ttu-id="5b4c5-108">Las convenciones de desenredado existentes no funcionan, ya que no utilizan código compilado JIT.</span><span class="sxs-lookup"><span data-stu-id="5b4c5-108">Existing unwinding conventions do not work, because they do not use JIT-compiled code.</span></span> <span data-ttu-id="5b4c5-109">Cuando el depurador ve un marco que no se pueda desenredar, debe utilizar el método [ICorDebugStackWalk:: Next](icordebugstackwalk-next-method.md) para desenredarlo, pero debe realizar la inspección.</span><span class="sxs-lookup"><span data-stu-id="5b4c5-109">When the debugger sees an unwindable frame, it should use the [ICorDebugStackWalk::Next](icordebugstackwalk-next-method.md) method to unwind it, but it should perform inspection itself.</span></span> <span data-ttu-id="5b4c5-110">Cuando el depurador recibe un `ICorDebugRuntimeUnwindableFrame` , puede llamar al método [ICorDebugStackWalk:: getContext](icordebugstackwalk-getcontext-method.md) para recuperar el contexto del marco.</span><span class="sxs-lookup"><span data-stu-id="5b4c5-110">When the debugger receives an `ICorDebugRuntimeUnwindableFrame`, it can call the [ICorDebugStackWalk::GetContext](icordebugstackwalk-getcontext-method.md) method to retrieve the context of the frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b4c5-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5b4c5-111">Requirements</span></span>  

 <span data-ttu-id="5b4c5-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5b4c5-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b4c5-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5b4c5-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5b4c5-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5b4c5-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5b4c5-115">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b4c5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b4c5-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="5b4c5-116">See also</span></span>

- [<span data-ttu-id="5b4c5-117">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="5b4c5-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="5b4c5-118">Depuración</span><span class="sxs-lookup"><span data-stu-id="5b4c5-118">Debugging</span></span>](index.md)
