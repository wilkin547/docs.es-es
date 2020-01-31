---
title: ICorDebugThread3 (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugThread3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread3
helpviewer_keywords:
- ICorDebugThread3 interface [.NET Framework debugging]
ms.assetid: eb2860ef-06cb-4968-a6c3-6d048ecda2a4
topic_type:
- apiref
ms.openlocfilehash: 19bd869aec7e4d046890d2314f5142753ba0b112
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791389"
---
# <a name="icordebugthread3-interface"></a><span data-ttu-id="3321b-102">ICorDebugThread3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3321b-102">ICorDebugThread3 Interface</span></span>
<span data-ttu-id="3321b-103">Proporciona el punto de entrada a [ICorDebugStackWalk](icordebugstackwalk-interface.md) y las interfaces correspondientes.</span><span class="sxs-lookup"><span data-stu-id="3321b-103">Provides the entry point to the [ICorDebugStackWalk](icordebugstackwalk-interface.md) and corresponding interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3321b-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="3321b-104">Methods</span></span>  
  
|<span data-ttu-id="3321b-105">Método</span><span class="sxs-lookup"><span data-stu-id="3321b-105">Method</span></span>|<span data-ttu-id="3321b-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="3321b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3321b-107">CreateStackWalk (método)</span><span class="sxs-lookup"><span data-stu-id="3321b-107">CreateStackWalk Method</span></span>](icordebugthread3-createstackwalk-method.md)|<span data-ttu-id="3321b-108">Crea un objeto [ICorDebugStackWalk](icordebugstackwalk-interface.md) para el subproceso cuya pila desea desenredar.</span><span class="sxs-lookup"><span data-stu-id="3321b-108">Creates an [ICorDebugStackWalk](icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>|  
|[<span data-ttu-id="3321b-109">GetActiveInternalFrames (método)</span><span class="sxs-lookup"><span data-stu-id="3321b-109">GetActiveInternalFrames Method</span></span>](icordebugthread3-getactiveinternalframes-method.md)|<span data-ttu-id="3321b-110">Devuelve una matriz de Marcos internos (objetos[ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) ) en la pila.</span><span class="sxs-lookup"><span data-stu-id="3321b-110">Returns an array of internal frames ([ICorDebugInternalFrame2](icordebuginternalframe2-interface.md) objects) on the stack.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3321b-111">Notas</span><span class="sxs-lookup"><span data-stu-id="3321b-111">Remarks</span></span>  
 <span data-ttu-id="3321b-112">`ICorDebugThread3` es una extensión lógica de la interfaz ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="3321b-112">`ICorDebugThread3` is a logical extension to the ICorDebugThread interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3321b-113">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="3321b-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3321b-114">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="3321b-114">Requirements</span></span>  
 <span data-ttu-id="3321b-115">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3321b-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3321b-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3321b-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3321b-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3321b-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3321b-118">**.NET Framework versiones:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3321b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3321b-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="3321b-119">See also</span></span>

- [<span data-ttu-id="3321b-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="3321b-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="3321b-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="3321b-121">Debugging</span></span>](index.md)
