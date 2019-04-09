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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a68e061c6def61746ee65f8a25818f8dbcd785b5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59159736"
---
# <a name="icordebugbreakpoint-interface"></a><span data-ttu-id="80ab4-102">Interfaz ICorDebugBreakpoint</span><span class="sxs-lookup"><span data-stu-id="80ab4-102">ICorDebugBreakpoint Interface</span></span>

<span data-ttu-id="80ab4-103">Representa un punto de interrupción en una función o un punto de inspección en un valor.</span><span class="sxs-lookup"><span data-stu-id="80ab4-103">Represents a breakpoint in a function, or a watch point on a value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="80ab4-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="80ab4-104">Methods</span></span>  
  
|<span data-ttu-id="80ab4-105">Método</span><span class="sxs-lookup"><span data-stu-id="80ab4-105">Method</span></span>|<span data-ttu-id="80ab4-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="80ab4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="80ab4-107">Método Activate</span><span class="sxs-lookup"><span data-stu-id="80ab4-107">Activate Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-activate-method.md)|<span data-ttu-id="80ab4-108">Establece el estado activo de este `ICorDebugBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="80ab4-108">Sets the active state of this `ICorDebugBreakpoint`.</span></span>|  
|[<span data-ttu-id="80ab4-109">Método IsActive</span><span class="sxs-lookup"><span data-stu-id="80ab4-109">IsActive Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-isactive-method.md)|<span data-ttu-id="80ab4-110">Obtiene un valor que indica si este `ICorDebugBreakpoint` está activo.</span><span class="sxs-lookup"><span data-stu-id="80ab4-110">Gets a value that indicates whether this `ICorDebugBreakpoint` is active.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="80ab4-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="80ab4-111">Remarks</span></span>  
 <span data-ttu-id="80ab4-112">Los puntos de interrupción no admiten directamente las expresiones condicionales.</span><span class="sxs-lookup"><span data-stu-id="80ab4-112">Breakpoints do not directly support conditional expressions.</span></span> <span data-ttu-id="80ab4-113">Si se desea esa funcionalidad, un depurador debe implementarla en la parte superior de `ICorDebugBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="80ab4-113">If such functionality is desired, a debugger must implement it on top of `ICorDebugBreakpoint`.</span></span>  
  
 <span data-ttu-id="80ab4-114">ICorDebugFunctionBreakpoint (interfaz) extiende `ICorDebugBreakpoint` para admitir puntos de interrupción dentro de las funciones.</span><span class="sxs-lookup"><span data-stu-id="80ab4-114">The ICorDebugFunctionBreakpoint interface extends `ICorDebugBreakpoint` to support breakpoints within functions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="80ab4-115">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="80ab4-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80ab4-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="80ab4-116">Requirements</span></span>  
 <span data-ttu-id="80ab4-117">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80ab4-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80ab4-118">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="80ab4-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="80ab4-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="80ab4-119">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="80ab4-120">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="80ab4-120">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="80ab4-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="80ab4-121">See also</span></span>

- [<span data-ttu-id="80ab4-122">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="80ab4-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
