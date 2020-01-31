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
ms.openlocfilehash: 53d8d219a13f2dade16a338efccf0837f8de0158
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784372"
---
# <a name="icordebugbreakpoint-interface"></a><span data-ttu-id="d8d7a-102">Interfaz ICorDebugBreakpoint</span><span class="sxs-lookup"><span data-stu-id="d8d7a-102">ICorDebugBreakpoint Interface</span></span>

<span data-ttu-id="d8d7a-103">Representa un punto de interrupción en una función o un punto de inspección en un valor.</span><span class="sxs-lookup"><span data-stu-id="d8d7a-103">Represents a breakpoint in a function, or a watch point on a value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d8d7a-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="d8d7a-104">Methods</span></span>  
  
|<span data-ttu-id="d8d7a-105">Método</span><span class="sxs-lookup"><span data-stu-id="d8d7a-105">Method</span></span>|<span data-ttu-id="d8d7a-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="d8d7a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d8d7a-107">Activate (método)</span><span class="sxs-lookup"><span data-stu-id="d8d7a-107">Activate Method</span></span>](icordebugbreakpoint-activate-method.md)|<span data-ttu-id="d8d7a-108">Establece el estado activo de este `ICorDebugBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="d8d7a-108">Sets the active state of this `ICorDebugBreakpoint`.</span></span>|  
|[<span data-ttu-id="d8d7a-109">IsActive (método)</span><span class="sxs-lookup"><span data-stu-id="d8d7a-109">IsActive Method</span></span>](icordebugbreakpoint-isactive-method.md)|<span data-ttu-id="d8d7a-110">Obtiene un valor que indica si este `ICorDebugBreakpoint` está activo.</span><span class="sxs-lookup"><span data-stu-id="d8d7a-110">Gets a value that indicates whether this `ICorDebugBreakpoint` is active.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d8d7a-111">Notas</span><span class="sxs-lookup"><span data-stu-id="d8d7a-111">Remarks</span></span>  
 <span data-ttu-id="d8d7a-112">Los puntos de interrupción no admiten directamente las expresiones condicionales.</span><span class="sxs-lookup"><span data-stu-id="d8d7a-112">Breakpoints do not directly support conditional expressions.</span></span> <span data-ttu-id="d8d7a-113">Si se desea esta funcionalidad, un depurador debe implementarla encima de `ICorDebugBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="d8d7a-113">If such functionality is desired, a debugger must implement it on top of `ICorDebugBreakpoint`.</span></span>  
  
 <span data-ttu-id="d8d7a-114">La interfaz ICorDebugFunctionBreakpoint extiende `ICorDebugBreakpoint` para admitir puntos de interrupción dentro de las funciones.</span><span class="sxs-lookup"><span data-stu-id="d8d7a-114">The ICorDebugFunctionBreakpoint interface extends `ICorDebugBreakpoint` to support breakpoints within functions.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d8d7a-115">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="d8d7a-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8d7a-116">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="d8d7a-116">Requirements</span></span>  
 <span data-ttu-id="d8d7a-117">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8d7a-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8d7a-118">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d8d7a-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d8d7a-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d8d7a-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d8d7a-120">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8d7a-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8d7a-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="d8d7a-121">See also</span></span>

- [<span data-ttu-id="d8d7a-122">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="d8d7a-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
