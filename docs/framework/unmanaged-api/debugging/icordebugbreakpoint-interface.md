---
title: Interfaz ICorDebugBreakpoint
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
ms.openlocfilehash: 0c84a91c7da553d0c84a4995b4744576d861dcb9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730206"
---
# <a name="icordebugbreakpoint-interface"></a><span data-ttu-id="14e83-102">Interfaz ICorDebugBreakpoint</span><span class="sxs-lookup"><span data-stu-id="14e83-102">ICorDebugBreakpoint Interface</span></span>

<span data-ttu-id="14e83-103">Representa un punto de interrupción en una función o un punto de inspección en un valor.</span><span class="sxs-lookup"><span data-stu-id="14e83-103">Represents a breakpoint in a function, or a watch point on a value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="14e83-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="14e83-104">Methods</span></span>  
  
|<span data-ttu-id="14e83-105">Método</span><span class="sxs-lookup"><span data-stu-id="14e83-105">Method</span></span>|<span data-ttu-id="14e83-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="14e83-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="14e83-107">Método Activate</span><span class="sxs-lookup"><span data-stu-id="14e83-107">Activate Method</span></span>](icordebugbreakpoint-activate-method.md)|<span data-ttu-id="14e83-108">Establece el estado activo de este `ICorDebugBreakpoint` .</span><span class="sxs-lookup"><span data-stu-id="14e83-108">Sets the active state of this `ICorDebugBreakpoint`.</span></span>|  
|[<span data-ttu-id="14e83-109">IsActive (Método)</span><span class="sxs-lookup"><span data-stu-id="14e83-109">IsActive Method</span></span>](icordebugbreakpoint-isactive-method.md)|<span data-ttu-id="14e83-110">Obtiene un valor que indica si este `ICorDebugBreakpoint` está activo.</span><span class="sxs-lookup"><span data-stu-id="14e83-110">Gets a value that indicates whether this `ICorDebugBreakpoint` is active.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="14e83-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="14e83-111">Remarks</span></span>  

 <span data-ttu-id="14e83-112">Los puntos de interrupción no admiten directamente las expresiones condicionales.</span><span class="sxs-lookup"><span data-stu-id="14e83-112">Breakpoints do not directly support conditional expressions.</span></span> <span data-ttu-id="14e83-113">Si se desea esta funcionalidad, un depurador debe implementarla en la parte superior de `ICorDebugBreakpoint` .</span><span class="sxs-lookup"><span data-stu-id="14e83-113">If such functionality is desired, a debugger must implement it on top of `ICorDebugBreakpoint`.</span></span>  
  
 <span data-ttu-id="14e83-114">La interfaz ICorDebugFunctionBreakpoint `ICorDebugBreakpoint` se extiende para admitir puntos de interrupción dentro de las funciones.</span><span class="sxs-lookup"><span data-stu-id="14e83-114">The ICorDebugFunctionBreakpoint interface extends `ICorDebugBreakpoint` to support breakpoints within functions.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="14e83-115">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="14e83-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14e83-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="14e83-116">Requirements</span></span>  

 <span data-ttu-id="14e83-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="14e83-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14e83-118">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="14e83-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="14e83-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="14e83-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="14e83-120">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14e83-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14e83-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="14e83-121">See also</span></span>

- [<span data-ttu-id="14e83-122">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="14e83-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
