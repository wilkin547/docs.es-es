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
ms.openlocfilehash: 22ae1d24040a8ee5000e0ff2fbeb2b45e08050df
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784353"
---
# <a name="icordebugbreakpointenum-interface"></a><span data-ttu-id="a782d-102">Interfaz ICorDebugBreakpointEnum</span><span class="sxs-lookup"><span data-stu-id="a782d-102">ICorDebugBreakpointEnum Interface</span></span>

<span data-ttu-id="a782d-103">Implementa los métodos de ICorDebugEnum y enumera las matrices de ICorDebugBreakpoint.</span><span class="sxs-lookup"><span data-stu-id="a782d-103">Implements ICorDebugEnum methods, and enumerates ICorDebugBreakpoint arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a782d-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="a782d-104">Methods</span></span>  
  
|<span data-ttu-id="a782d-105">Método</span><span class="sxs-lookup"><span data-stu-id="a782d-105">Method</span></span>|<span data-ttu-id="a782d-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="a782d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a782d-107">Next (método)</span><span class="sxs-lookup"><span data-stu-id="a782d-107">Next Method</span></span>](icordebugbreakpointenum-next-method.md)|<span data-ttu-id="a782d-108">Obtiene el número especificado de instancias de `ICorDebugBreakpoint` de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="a782d-108">Gets the specified number of `ICorDebugBreakpoint` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a782d-109">Notas</span><span class="sxs-lookup"><span data-stu-id="a782d-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a782d-110">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="a782d-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a782d-111">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="a782d-111">Requirements</span></span>  
 <span data-ttu-id="a782d-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a782d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a782d-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a782d-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a782d-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a782d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a782d-115">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a782d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a782d-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="a782d-116">See also</span></span>

- [<span data-ttu-id="a782d-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="a782d-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
