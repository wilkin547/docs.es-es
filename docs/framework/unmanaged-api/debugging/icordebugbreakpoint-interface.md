---
title: ICorDebugBreakpoint Interfaz1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugBreakpoint
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugBreakpoint
helpviewer_keywords: ICorDebugBreakpoint interface [.NET Framework debugging]
ms.assetid: aa5ad3d7-e1bb-42af-99bc-471224e3bcaa
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cd2c4245b5e3dcc4f7b989a3ca9add8d568467cb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugbreakpoint-interface1"></a><span data-ttu-id="22021-102">ICorDebugBreakpoint Interfaz1</span><span class="sxs-lookup"><span data-stu-id="22021-102">ICorDebugBreakpoint Interface1</span></span>
<span data-ttu-id="22021-103">Representa un punto de interrupción en una función o un punto de inspección en un valor.</span><span class="sxs-lookup"><span data-stu-id="22021-103">Represents a breakpoint in a function, or a watch point on a value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="22021-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="22021-104">Methods</span></span>  
  
|<span data-ttu-id="22021-105">Método</span><span class="sxs-lookup"><span data-stu-id="22021-105">Method</span></span>|<span data-ttu-id="22021-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="22021-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="22021-107">Activate (método)</span><span class="sxs-lookup"><span data-stu-id="22021-107">Activate Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-activate-method.md)|<span data-ttu-id="22021-108">Establece el estado activo de este `ICorDebugBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="22021-108">Sets the active state of this `ICorDebugBreakpoint`.</span></span>|  
|[<span data-ttu-id="22021-109">IsActive (método)</span><span class="sxs-lookup"><span data-stu-id="22021-109">IsActive Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-isactive-method.md)|<span data-ttu-id="22021-110">Obtiene un valor que indica si este `ICorDebugBreakpoint` está activo.</span><span class="sxs-lookup"><span data-stu-id="22021-110">Gets a value that indicates whether this `ICorDebugBreakpoint` is active.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="22021-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="22021-111">Remarks</span></span>  
 <span data-ttu-id="22021-112">Puntos de interrupción no son directamente compatibles con las expresiones condicionales.</span><span class="sxs-lookup"><span data-stu-id="22021-112">Breakpoints do not directly support conditional expressions.</span></span> <span data-ttu-id="22021-113">Si se desea esta funcionalidad, un depurador debe implementarla en la parte superior de `ICorDebugBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="22021-113">If such functionality is desired, a debugger must implement it on top of `ICorDebugBreakpoint`.</span></span>  
  
 <span data-ttu-id="22021-114">ICorDebugFunctionBreakpoint (interfaz) extiende `ICorDebugBreakpoint` para admitir puntos de interrupción dentro de las funciones.</span><span class="sxs-lookup"><span data-stu-id="22021-114">The ICorDebugFunctionBreakpoint interface extends `ICorDebugBreakpoint` to support breakpoints within functions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="22021-115">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="22021-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22021-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="22021-116">Requirements</span></span>  
 <span data-ttu-id="22021-117">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22021-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22021-118">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="22021-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="22021-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="22021-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="22021-120">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22021-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22021-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="22021-121">See Also</span></span>  
 [<span data-ttu-id="22021-122">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="22021-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
