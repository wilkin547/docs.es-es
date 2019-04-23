---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0f15b9f5961699f905e765426576bdf6f3416793
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59141159"
---
# <a name="icordebugfunctionbreakpoint-interface"></a><span data-ttu-id="54286-102">Interfaz ICorDebugFunctionBreakpoint</span><span class="sxs-lookup"><span data-stu-id="54286-102">ICorDebugFunctionBreakpoint Interface</span></span>

<span data-ttu-id="54286-103">Extiende la interfaz ICorDebugBreakpoint para admitir puntos de interrupción dentro de las funciones.</span><span class="sxs-lookup"><span data-stu-id="54286-103">Extends the ICorDebugBreakpoint interface to support breakpoints within functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="54286-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="54286-104">Methods</span></span>  
  
|<span data-ttu-id="54286-105">Método</span><span class="sxs-lookup"><span data-stu-id="54286-105">Method</span></span>|<span data-ttu-id="54286-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="54286-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="54286-107">GetFunction (método)</span><span class="sxs-lookup"><span data-stu-id="54286-107">GetFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunctionbreakpoint-getfunction-method.md)|<span data-ttu-id="54286-108">Obtiene un puntero de interfaz a un ICorDebugFunction que hace referencia a la función en el que se establece el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="54286-108">Gets an interface pointer to an ICorDebugFunction that references the function in which the breakpoint is set.</span></span>|  
|[<span data-ttu-id="54286-109">GetOffset (método)</span><span class="sxs-lookup"><span data-stu-id="54286-109">GetOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunctionbreakpoint-getoffset-method.md)|<span data-ttu-id="54286-110">Obtiene el desplazamiento del punto de interrupción dentro de la función.</span><span class="sxs-lookup"><span data-stu-id="54286-110">Gets the offset of the breakpoint within the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="54286-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="54286-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="54286-112">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="54286-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54286-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="54286-113">Requirements</span></span>  
 <span data-ttu-id="54286-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="54286-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54286-115">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="54286-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="54286-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="54286-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="54286-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54286-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54286-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="54286-118">See also</span></span>

- [<span data-ttu-id="54286-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="54286-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
