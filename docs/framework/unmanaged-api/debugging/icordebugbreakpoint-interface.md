---
title: ICorDebugBreakpoint Interfaz1
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 220cd1a41ed69325b557e6498a511865b78817ec
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33404520"
---
# <a name="icordebugbreakpoint-interface1"></a><span data-ttu-id="a1e6d-102">ICorDebugBreakpoint Interfaz1</span><span class="sxs-lookup"><span data-stu-id="a1e6d-102">ICorDebugBreakpoint Interface1</span></span>
<span data-ttu-id="a1e6d-103">Representa un punto de interrupción en una función o un punto de inspección en un valor.</span><span class="sxs-lookup"><span data-stu-id="a1e6d-103">Represents a breakpoint in a function, or a watch point on a value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a1e6d-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="a1e6d-104">Methods</span></span>  
  
|<span data-ttu-id="a1e6d-105">Método</span><span class="sxs-lookup"><span data-stu-id="a1e6d-105">Method</span></span>|<span data-ttu-id="a1e6d-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="a1e6d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a1e6d-107">Activate (método)</span><span class="sxs-lookup"><span data-stu-id="a1e6d-107">Activate Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-activate-method.md)|<span data-ttu-id="a1e6d-108">Establece el estado activo de este `ICorDebugBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="a1e6d-108">Sets the active state of this `ICorDebugBreakpoint`.</span></span>|  
|[<span data-ttu-id="a1e6d-109">IsActive (método)</span><span class="sxs-lookup"><span data-stu-id="a1e6d-109">IsActive Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-isactive-method.md)|<span data-ttu-id="a1e6d-110">Obtiene un valor que indica si este `ICorDebugBreakpoint` está activo.</span><span class="sxs-lookup"><span data-stu-id="a1e6d-110">Gets a value that indicates whether this `ICorDebugBreakpoint` is active.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a1e6d-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a1e6d-111">Remarks</span></span>  
 <span data-ttu-id="a1e6d-112">Puntos de interrupción no son directamente compatibles con las expresiones condicionales.</span><span class="sxs-lookup"><span data-stu-id="a1e6d-112">Breakpoints do not directly support conditional expressions.</span></span> <span data-ttu-id="a1e6d-113">Si se desea esta funcionalidad, un depurador debe implementarla en la parte superior de `ICorDebugBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="a1e6d-113">If such functionality is desired, a debugger must implement it on top of `ICorDebugBreakpoint`.</span></span>  
  
 <span data-ttu-id="a1e6d-114">ICorDebugFunctionBreakpoint (interfaz) extiende `ICorDebugBreakpoint` para admitir puntos de interrupción dentro de las funciones.</span><span class="sxs-lookup"><span data-stu-id="a1e6d-114">The ICorDebugFunctionBreakpoint interface extends `ICorDebugBreakpoint` to support breakpoints within functions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a1e6d-115">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="a1e6d-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1e6d-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a1e6d-116">Requirements</span></span>  
 <span data-ttu-id="a1e6d-117">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1e6d-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1e6d-118">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a1e6d-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a1e6d-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a1e6d-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a1e6d-120">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1e6d-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1e6d-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="a1e6d-121">See Also</span></span>  
 [<span data-ttu-id="a1e6d-122">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="a1e6d-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
