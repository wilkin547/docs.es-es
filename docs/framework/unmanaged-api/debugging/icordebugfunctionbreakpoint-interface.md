---
title: ICorDebugFunctionBreakpoint Interfaz1
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
ms.openlocfilehash: 6cd4c430798333dd22c36ce30e7c9ce05bdc8f56
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33414188"
---
# <a name="icordebugfunctionbreakpoint-interface1"></a><span data-ttu-id="67e2c-102">ICorDebugFunctionBreakpoint Interfaz1</span><span class="sxs-lookup"><span data-stu-id="67e2c-102">ICorDebugFunctionBreakpoint Interface1</span></span>
<span data-ttu-id="67e2c-103">Extiende la interfaz ICorDebugBreakpoint para admitir puntos de interrupción dentro de las funciones.</span><span class="sxs-lookup"><span data-stu-id="67e2c-103">Extends the ICorDebugBreakpoint interface to support breakpoints within functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="67e2c-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="67e2c-104">Methods</span></span>  
  
|<span data-ttu-id="67e2c-105">Método</span><span class="sxs-lookup"><span data-stu-id="67e2c-105">Method</span></span>|<span data-ttu-id="67e2c-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="67e2c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="67e2c-107">GetFunction (método)</span><span class="sxs-lookup"><span data-stu-id="67e2c-107">GetFunction Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunctionbreakpoint-getfunction-method.md)|<span data-ttu-id="67e2c-108">Obtiene un puntero de interfaz a un ICorDebugFunction que hace referencia a la función en el que se establece el punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="67e2c-108">Gets an interface pointer to an ICorDebugFunction that references the function in which the breakpoint is set.</span></span>|  
|[<span data-ttu-id="67e2c-109">GetOffset (método)</span><span class="sxs-lookup"><span data-stu-id="67e2c-109">GetOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunctionbreakpoint-getoffset-method.md)|<span data-ttu-id="67e2c-110">Obtiene el desplazamiento del punto de interrupción dentro de la función.</span><span class="sxs-lookup"><span data-stu-id="67e2c-110">Gets the offset of the breakpoint within the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="67e2c-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="67e2c-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="67e2c-112">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="67e2c-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67e2c-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="67e2c-113">Requirements</span></span>  
 <span data-ttu-id="67e2c-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67e2c-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67e2c-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="67e2c-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="67e2c-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="67e2c-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="67e2c-117">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67e2c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67e2c-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="67e2c-118">See Also</span></span>  
 [<span data-ttu-id="67e2c-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="67e2c-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
