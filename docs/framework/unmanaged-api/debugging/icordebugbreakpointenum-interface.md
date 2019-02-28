---
title: ICorDebugBreakpointEnum (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpointEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpointEnum
helpviewer_keywords:
- ICorDebugBreakpointEnum interface [.NET Framework debugging]
ms.assetid: 4c6f4f6e-52cc-402e-881b-7b8526544c90
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7b5268eb4240f7c3ff254f4d3d9a13ab494530a1
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56968743"
---
# <a name="icordebugbreakpointenum-interface"></a><span data-ttu-id="5fbd7-102">ICorDebugBreakpointEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5fbd7-102">ICorDebugBreakpointEnum Interface</span></span>

<span data-ttu-id="5fbd7-103">Implementa los métodos ICorDebugEnum y enumera las matrices ICorDebugBreakpoint.</span><span class="sxs-lookup"><span data-stu-id="5fbd7-103">Implements ICorDebugEnum methods, and enumerates ICorDebugBreakpoint arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5fbd7-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="5fbd7-104">Methods</span></span>  
  
|<span data-ttu-id="5fbd7-105">Método</span><span class="sxs-lookup"><span data-stu-id="5fbd7-105">Method</span></span>|<span data-ttu-id="5fbd7-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="5fbd7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5fbd7-107">Next (método)</span><span class="sxs-lookup"><span data-stu-id="5fbd7-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpointenum-next-method.md)|<span data-ttu-id="5fbd7-108">Obtiene el número especificado de `ICorDebugBreakpoint` instancias de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="5fbd7-108">Gets the specified number of `ICorDebugBreakpoint` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5fbd7-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5fbd7-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5fbd7-110">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="5fbd7-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5fbd7-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5fbd7-111">Requirements</span></span>  
 <span data-ttu-id="5fbd7-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5fbd7-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5fbd7-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5fbd7-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5fbd7-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5fbd7-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5fbd7-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5fbd7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fbd7-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="5fbd7-116">See also</span></span>
- [<span data-ttu-id="5fbd7-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="5fbd7-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
