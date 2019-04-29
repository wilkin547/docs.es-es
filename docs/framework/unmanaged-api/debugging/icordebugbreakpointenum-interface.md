---
title: Interfaz ICorDebugBreakpointEnum
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
ms.openlocfilehash: 7fd42f13f699b0b79fd69311186f2b2ca0c9998a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645311"
---
# <a name="icordebugbreakpointenum-interface"></a><span data-ttu-id="43b5b-102">Interfaz ICorDebugBreakpointEnum</span><span class="sxs-lookup"><span data-stu-id="43b5b-102">ICorDebugBreakpointEnum Interface</span></span>

<span data-ttu-id="43b5b-103">Implementa los métodos ICorDebugEnum y enumera las matrices ICorDebugBreakpoint.</span><span class="sxs-lookup"><span data-stu-id="43b5b-103">Implements ICorDebugEnum methods, and enumerates ICorDebugBreakpoint arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="43b5b-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="43b5b-104">Methods</span></span>  
  
|<span data-ttu-id="43b5b-105">Método</span><span class="sxs-lookup"><span data-stu-id="43b5b-105">Method</span></span>|<span data-ttu-id="43b5b-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="43b5b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="43b5b-107">Next (método)</span><span class="sxs-lookup"><span data-stu-id="43b5b-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpointenum-next-method.md)|<span data-ttu-id="43b5b-108">Obtiene el número especificado de `ICorDebugBreakpoint` instancias de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="43b5b-108">Gets the specified number of `ICorDebugBreakpoint` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="43b5b-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="43b5b-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="43b5b-110">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="43b5b-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43b5b-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="43b5b-111">Requirements</span></span>  
 <span data-ttu-id="43b5b-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43b5b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43b5b-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="43b5b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="43b5b-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="43b5b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="43b5b-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43b5b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43b5b-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="43b5b-116">See also</span></span>

- [<span data-ttu-id="43b5b-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="43b5b-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
