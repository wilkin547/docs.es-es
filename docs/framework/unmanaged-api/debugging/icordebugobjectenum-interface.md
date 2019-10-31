---
title: ICorDebugObjectEnum (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugObjectEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectEnum
helpviewer_keywords:
- ICorDebugObjectEnum interface [.NET Framework debugging]
ms.assetid: 9ffb4498-7719-49d3-8890-df2c22248a0c
topic_type:
- apiref
ms.openlocfilehash: b77d5859986c90d6ef61c02547014d0bec354106
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73096138"
---
# <a name="icordebugobjectenum-interface"></a><span data-ttu-id="7b4aa-102">ICorDebugObjectEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7b4aa-102">ICorDebugObjectEnum Interface</span></span>

<span data-ttu-id="7b4aa-103">Implementa los métodos ICorDebugEnum y enumera las matrices de objetos por sus direcciones virtuales relativas (RVA).</span><span class="sxs-lookup"><span data-stu-id="7b4aa-103">Implements ICorDebugEnum methods, and enumerates arrays of objects by their relative virtual addresses (RVAs).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7b4aa-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="7b4aa-104">Methods</span></span>  
  
|<span data-ttu-id="7b4aa-105">Método</span><span class="sxs-lookup"><span data-stu-id="7b4aa-105">Method</span></span>|<span data-ttu-id="7b4aa-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="7b4aa-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7b4aa-107">Next (método)</span><span class="sxs-lookup"><span data-stu-id="7b4aa-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectenum-next-method.md)|<span data-ttu-id="7b4aa-108">Obtiene las RVA del número especificado de objetos de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="7b4aa-108">Gets the RVAs of the specified number of objects from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7b4aa-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7b4aa-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7b4aa-110">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="7b4aa-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b4aa-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7b4aa-111">Requirements</span></span>  
 <span data-ttu-id="7b4aa-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b4aa-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b4aa-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7b4aa-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7b4aa-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7b4aa-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7b4aa-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b4aa-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b4aa-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="7b4aa-116">See also</span></span>

- [<span data-ttu-id="7b4aa-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="7b4aa-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
