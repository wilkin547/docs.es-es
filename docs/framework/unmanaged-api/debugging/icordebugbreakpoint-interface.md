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
ms.openlocfilehash: b92c3d3328c657762ed002155ef4947a9292b19e
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894725"
---
# <a name="icordebugbreakpoint-interface"></a><span data-ttu-id="70790-102">Interfaz ICorDebugBreakpoint</span><span class="sxs-lookup"><span data-stu-id="70790-102">ICorDebugBreakpoint Interface</span></span>

<span data-ttu-id="70790-103">Representa un punto de interrupción en una función o un punto de inspección en un valor.</span><span class="sxs-lookup"><span data-stu-id="70790-103">Represents a breakpoint in a function, or a watch point on a value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="70790-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="70790-104">Methods</span></span>  
  
|<span data-ttu-id="70790-105">Método</span><span class="sxs-lookup"><span data-stu-id="70790-105">Method</span></span>|<span data-ttu-id="70790-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="70790-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="70790-107">Método Activate</span><span class="sxs-lookup"><span data-stu-id="70790-107">Activate Method</span></span>](icordebugbreakpoint-activate-method.md)|<span data-ttu-id="70790-108">Establece el estado activo de este `ICorDebugBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="70790-108">Sets the active state of this `ICorDebugBreakpoint`.</span></span>|  
|[<span data-ttu-id="70790-109">IsActive (Método)</span><span class="sxs-lookup"><span data-stu-id="70790-109">IsActive Method</span></span>](icordebugbreakpoint-isactive-method.md)|<span data-ttu-id="70790-110">Obtiene un valor que indica si este `ICorDebugBreakpoint` está activo.</span><span class="sxs-lookup"><span data-stu-id="70790-110">Gets a value that indicates whether this `ICorDebugBreakpoint` is active.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="70790-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="70790-111">Remarks</span></span>  
 <span data-ttu-id="70790-112">Los puntos de interrupción no admiten directamente las expresiones condicionales.</span><span class="sxs-lookup"><span data-stu-id="70790-112">Breakpoints do not directly support conditional expressions.</span></span> <span data-ttu-id="70790-113">Si se desea esta funcionalidad, un depurador debe implementarla en la `ICorDebugBreakpoint`parte superior de.</span><span class="sxs-lookup"><span data-stu-id="70790-113">If such functionality is desired, a debugger must implement it on top of `ICorDebugBreakpoint`.</span></span>  
  
 <span data-ttu-id="70790-114">La interfaz ICorDebugFunctionBreakpoint se `ICorDebugBreakpoint` extiende para admitir puntos de interrupción dentro de las funciones.</span><span class="sxs-lookup"><span data-stu-id="70790-114">The ICorDebugFunctionBreakpoint interface extends `ICorDebugBreakpoint` to support breakpoints within functions.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="70790-115">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="70790-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70790-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="70790-116">Requirements</span></span>  
 <span data-ttu-id="70790-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="70790-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70790-118">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="70790-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="70790-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="70790-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="70790-120">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70790-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70790-121">Consulta también</span><span class="sxs-lookup"><span data-stu-id="70790-121">See also</span></span>

- [<span data-ttu-id="70790-122">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="70790-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
