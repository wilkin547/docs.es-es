---
title: ICorDebugBreakpoint (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpoint
helpviewer_keywords:
- ICorDebugBreakpoint interface [.NET Framework debugging]
ms.assetid: aa5ad3d7-e1bb-42af-99bc-471224e3bcaa
topic_type:
- apiref
ms.openlocfilehash: 29bb84341c2cb4177c43f798d25a1a6d50099aa5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122798"
---
# <a name="icordebugbreakpoint-interface"></a><span data-ttu-id="496a4-102">ICorDebugBreakpoint (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="496a4-102">ICorDebugBreakpoint Interface</span></span>

<span data-ttu-id="496a4-103">Representa un punto de interrupción en una función o un punto de inspección en un valor.</span><span class="sxs-lookup"><span data-stu-id="496a4-103">Represents a breakpoint in a function, or a watch point on a value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="496a4-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="496a4-104">Methods</span></span>  
  
|<span data-ttu-id="496a4-105">Método</span><span class="sxs-lookup"><span data-stu-id="496a4-105">Method</span></span>|<span data-ttu-id="496a4-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="496a4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="496a4-107">Activate (método)</span><span class="sxs-lookup"><span data-stu-id="496a4-107">Activate Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-activate-method.md)|<span data-ttu-id="496a4-108">Establece el estado activo de este `ICorDebugBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="496a4-108">Sets the active state of this `ICorDebugBreakpoint`.</span></span>|  
|[<span data-ttu-id="496a4-109">IsActive (método)</span><span class="sxs-lookup"><span data-stu-id="496a4-109">IsActive Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-isactive-method.md)|<span data-ttu-id="496a4-110">Obtiene un valor que indica si este `ICorDebugBreakpoint` está activo.</span><span class="sxs-lookup"><span data-stu-id="496a4-110">Gets a value that indicates whether this `ICorDebugBreakpoint` is active.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="496a4-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="496a4-111">Remarks</span></span>  
 <span data-ttu-id="496a4-112">Los puntos de interrupción no admiten directamente las expresiones condicionales.</span><span class="sxs-lookup"><span data-stu-id="496a4-112">Breakpoints do not directly support conditional expressions.</span></span> <span data-ttu-id="496a4-113">Si se desea esta funcionalidad, un depurador debe implementarla encima de `ICorDebugBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="496a4-113">If such functionality is desired, a debugger must implement it on top of `ICorDebugBreakpoint`.</span></span>  
  
 <span data-ttu-id="496a4-114">La interfaz ICorDebugFunctionBreakpoint extiende `ICorDebugBreakpoint` para admitir puntos de interrupción dentro de las funciones.</span><span class="sxs-lookup"><span data-stu-id="496a4-114">The ICorDebugFunctionBreakpoint interface extends `ICorDebugBreakpoint` to support breakpoints within functions.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="496a4-115">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="496a4-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="496a4-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="496a4-116">Requirements</span></span>  
 <span data-ttu-id="496a4-117">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="496a4-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="496a4-118">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="496a4-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="496a4-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="496a4-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="496a4-120">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="496a4-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="496a4-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="496a4-121">See also</span></span>

- [<span data-ttu-id="496a4-122">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="496a4-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
