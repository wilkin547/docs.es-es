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
ms.openlocfilehash: e391a02571481d75ce88ae3f3b2b6421705d661c
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894699"
---
# <a name="icordebugbreakpointenum-interface"></a><span data-ttu-id="5533e-102">Interfaz ICorDebugBreakpointEnum</span><span class="sxs-lookup"><span data-stu-id="5533e-102">ICorDebugBreakpointEnum Interface</span></span>

<span data-ttu-id="5533e-103">Implementa los métodos de ICorDebugEnum y enumera las matrices de ICorDebugBreakpoint.</span><span class="sxs-lookup"><span data-stu-id="5533e-103">Implements ICorDebugEnum methods, and enumerates ICorDebugBreakpoint arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5533e-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="5533e-104">Methods</span></span>  
  
|<span data-ttu-id="5533e-105">Método</span><span class="sxs-lookup"><span data-stu-id="5533e-105">Method</span></span>|<span data-ttu-id="5533e-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="5533e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5533e-107">Next (Método)</span><span class="sxs-lookup"><span data-stu-id="5533e-107">Next Method</span></span>](icordebugbreakpointenum-next-method.md)|<span data-ttu-id="5533e-108">Obtiene el número especificado de `ICorDebugBreakpoint` instancias de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="5533e-108">Gets the specified number of `ICorDebugBreakpoint` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5533e-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5533e-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5533e-110">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="5533e-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5533e-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5533e-111">Requirements</span></span>  
 <span data-ttu-id="5533e-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5533e-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5533e-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5533e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5533e-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5533e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5533e-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5533e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5533e-116">Consulta también</span><span class="sxs-lookup"><span data-stu-id="5533e-116">See also</span></span>

- [<span data-ttu-id="5533e-117">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="5533e-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
