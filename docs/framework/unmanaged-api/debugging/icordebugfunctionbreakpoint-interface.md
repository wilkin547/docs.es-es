---
description: 'Más información acerca de: interfaz ICorDebugFunctionBreakpoint'
title: Interfaz ICorDebugFunctionBreakpoint
ms.date: 03/30/2017
api_name:
- ICorDebugFunctionBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunctionBreakpoint
helpviewer_keywords:
- ICorDebugFunctionBreakpoint interface [.NET Framework debugging]
ms.assetid: 9c149303-14b1-4138-83d7-e8c3e0fcd332
topic_type:
- apiref
ms.openlocfilehash: 5d7597369241272d91de4b94a60d787304dc1c6e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99661134"
---
# <a name="icordebugfunctionbreakpoint-interface"></a><span data-ttu-id="44ad0-103">Interfaz ICorDebugFunctionBreakpoint</span><span class="sxs-lookup"><span data-stu-id="44ad0-103">ICorDebugFunctionBreakpoint Interface</span></span>

<span data-ttu-id="44ad0-104">Extiende la interfaz ICorDebugBreakpoint para admitir puntos de interrupción dentro de las funciones.</span><span class="sxs-lookup"><span data-stu-id="44ad0-104">Extends the ICorDebugBreakpoint interface to support breakpoints within functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="44ad0-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="44ad0-105">Methods</span></span>  
  
|<span data-ttu-id="44ad0-106">Método</span><span class="sxs-lookup"><span data-stu-id="44ad0-106">Method</span></span>|<span data-ttu-id="44ad0-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="44ad0-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="44ad0-108">Método GetFunction</span><span class="sxs-lookup"><span data-stu-id="44ad0-108">GetFunction Method</span></span>](icordebugfunctionbreakpoint-getfunction-method.md)|<span data-ttu-id="44ad0-109">Obtiene un puntero de interfaz a una ICorDebugFunction que hace referencia a la función en la que se establece el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="44ad0-109">Gets an interface pointer to an ICorDebugFunction that references the function in which the breakpoint is set.</span></span>|  
|[<span data-ttu-id="44ad0-110">Método GetOffset</span><span class="sxs-lookup"><span data-stu-id="44ad0-110">GetOffset Method</span></span>](icordebugfunctionbreakpoint-getoffset-method.md)|<span data-ttu-id="44ad0-111">Obtiene el desplazamiento del punto de interrupción dentro de la función.</span><span class="sxs-lookup"><span data-stu-id="44ad0-111">Gets the offset of the breakpoint within the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="44ad0-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="44ad0-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="44ad0-113">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="44ad0-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44ad0-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="44ad0-114">Requirements</span></span>  

 <span data-ttu-id="44ad0-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="44ad0-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44ad0-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="44ad0-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="44ad0-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="44ad0-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="44ad0-118">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44ad0-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44ad0-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="44ad0-119">See also</span></span>

- [<span data-ttu-id="44ad0-120">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="44ad0-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
