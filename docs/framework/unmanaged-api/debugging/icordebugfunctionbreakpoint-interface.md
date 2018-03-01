---
title: ICorDebugFunctionBreakpoint Interfaz1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 019a94243773fcb1751f419d8e38a6759fa1d3bd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugfunctionbreakpoint-interface1"></a><span data-ttu-id="2d354-102">ICorDebugFunctionBreakpoint Interfaz1</span><span class="sxs-lookup"><span data-stu-id="2d354-102">ICorDebugFunctionBreakpoint Interface1</span></span>
<span data-ttu-id="2d354-103">Extiende la interfaz ICorDebugBreakpoint para admitir puntos de interrupción dentro de las funciones.</span><span class="sxs-lookup"><span data-stu-id="2d354-103">Extends the ICorDebugBreakpoint interface to support breakpoints within functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2d354-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="2d354-104">Methods</span></span>  
  
|<span data-ttu-id="2d354-105">Método</span><span class="sxs-lookup"><span data-stu-id="2d354-105">Method</span></span>|<span data-ttu-id="2d354-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="2d354-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2d354-107">GetFunction (método)</span><span class="sxs-lookup"><span data-stu-id="2d354-107">GetFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunctionbreakpoint-getfunction-method.md)|<span data-ttu-id="2d354-108">Obtiene un puntero de interfaz a un ICorDebugFunction que hace referencia a la función en el que se establece el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="2d354-108">Gets an interface pointer to an ICorDebugFunction that references the function in which the breakpoint is set.</span></span>|  
|[<span data-ttu-id="2d354-109">GetOffset (método)</span><span class="sxs-lookup"><span data-stu-id="2d354-109">GetOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunctionbreakpoint-getoffset-method.md)|<span data-ttu-id="2d354-110">Obtiene el desplazamiento del punto de interrupción dentro de la función.</span><span class="sxs-lookup"><span data-stu-id="2d354-110">Gets the offset of the breakpoint within the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2d354-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2d354-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2d354-112">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="2d354-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d354-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2d354-113">Requirements</span></span>  
 <span data-ttu-id="2d354-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2d354-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d354-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2d354-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2d354-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2d354-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2d354-117">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d354-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d354-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="2d354-118">See Also</span></span>  
 [<span data-ttu-id="2d354-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="2d354-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
