---
description: 'Más información acerca de: ICorDebugBreakpoint (interfaz)'
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
ms.openlocfilehash: 63917512cceeccedea37acdf2ba7ab3b849d9fad
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99711809"
---
# <a name="icordebugbreakpoint-interface"></a><span data-ttu-id="b3493-103">Interfaz ICorDebugBreakpoint</span><span class="sxs-lookup"><span data-stu-id="b3493-103">ICorDebugBreakpoint Interface</span></span>

<span data-ttu-id="b3493-104">Representa un punto de interrupción en una función o un punto de inspección en un valor.</span><span class="sxs-lookup"><span data-stu-id="b3493-104">Represents a breakpoint in a function, or a watch point on a value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b3493-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="b3493-105">Methods</span></span>  
  
|<span data-ttu-id="b3493-106">Método</span><span class="sxs-lookup"><span data-stu-id="b3493-106">Method</span></span>|<span data-ttu-id="b3493-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="b3493-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b3493-108">Método Activate</span><span class="sxs-lookup"><span data-stu-id="b3493-108">Activate Method</span></span>](icordebugbreakpoint-activate-method.md)|<span data-ttu-id="b3493-109">Establece el estado activo de este `ICorDebugBreakpoint` .</span><span class="sxs-lookup"><span data-stu-id="b3493-109">Sets the active state of this `ICorDebugBreakpoint`.</span></span>|  
|[<span data-ttu-id="b3493-110">IsActive (Método)</span><span class="sxs-lookup"><span data-stu-id="b3493-110">IsActive Method</span></span>](icordebugbreakpoint-isactive-method.md)|<span data-ttu-id="b3493-111">Obtiene un valor que indica si este `ICorDebugBreakpoint` está activo.</span><span class="sxs-lookup"><span data-stu-id="b3493-111">Gets a value that indicates whether this `ICorDebugBreakpoint` is active.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b3493-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b3493-112">Remarks</span></span>  

 <span data-ttu-id="b3493-113">Los puntos de interrupción no admiten directamente las expresiones condicionales.</span><span class="sxs-lookup"><span data-stu-id="b3493-113">Breakpoints do not directly support conditional expressions.</span></span> <span data-ttu-id="b3493-114">Si se desea esta funcionalidad, un depurador debe implementarla en la parte superior de `ICorDebugBreakpoint` .</span><span class="sxs-lookup"><span data-stu-id="b3493-114">If such functionality is desired, a debugger must implement it on top of `ICorDebugBreakpoint`.</span></span>  
  
 <span data-ttu-id="b3493-115">La interfaz ICorDebugFunctionBreakpoint `ICorDebugBreakpoint` se extiende para admitir puntos de interrupción dentro de las funciones.</span><span class="sxs-lookup"><span data-stu-id="b3493-115">The ICorDebugFunctionBreakpoint interface extends `ICorDebugBreakpoint` to support breakpoints within functions.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b3493-116">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="b3493-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3493-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b3493-117">Requirements</span></span>  

 <span data-ttu-id="b3493-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b3493-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3493-119">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b3493-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b3493-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b3493-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b3493-121">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3493-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3493-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="b3493-122">See also</span></span>

- [<span data-ttu-id="b3493-123">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="b3493-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
