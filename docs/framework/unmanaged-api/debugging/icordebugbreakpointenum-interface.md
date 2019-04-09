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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59149076"
---
# <a name="icordebugbreakpointenum-interface"></a><span data-ttu-id="f46b1-102">Interfaz ICorDebugBreakpointEnum</span><span class="sxs-lookup"><span data-stu-id="f46b1-102">ICorDebugBreakpointEnum Interface</span></span>

<span data-ttu-id="f46b1-103">Implementa los métodos ICorDebugEnum y enumera las matrices ICorDebugBreakpoint.</span><span class="sxs-lookup"><span data-stu-id="f46b1-103">Implements ICorDebugEnum methods, and enumerates ICorDebugBreakpoint arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f46b1-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="f46b1-104">Methods</span></span>  
  
|<span data-ttu-id="f46b1-105">Método</span><span class="sxs-lookup"><span data-stu-id="f46b1-105">Method</span></span>|<span data-ttu-id="f46b1-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="f46b1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f46b1-107">Método Next</span><span class="sxs-lookup"><span data-stu-id="f46b1-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpointenum-next-method.md)|<span data-ttu-id="f46b1-108">Obtiene el número especificado de `ICorDebugBreakpoint` instancias de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="f46b1-108">Gets the specified number of `ICorDebugBreakpoint` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f46b1-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f46b1-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f46b1-110">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="f46b1-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f46b1-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f46b1-111">Requirements</span></span>  
 <span data-ttu-id="f46b1-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f46b1-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f46b1-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f46b1-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f46b1-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f46b1-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="f46b1-115">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="f46b1-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f46b1-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="f46b1-116">See also</span></span>

- [<span data-ttu-id="f46b1-117">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="f46b1-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
