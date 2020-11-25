---
title: Interfaz ICorDebugCodeEnum
ms.date: 03/30/2017
api_name:
- ICorDebugCodeEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCodeEnum
helpviewer_keywords:
- ICorDebugCodeEnum interface [.NET Framework debugging]
ms.assetid: b5589171-a4a0-4c00-bbdc-6e0a42233b75
topic_type:
- apiref
ms.openlocfilehash: b611dcabc1e5cc36f5c6342f0a832cc81de8c1d5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720742"
---
# <a name="icordebugcodeenum-interface"></a><span data-ttu-id="002b3-102">Interfaz ICorDebugCodeEnum</span><span class="sxs-lookup"><span data-stu-id="002b3-102">ICorDebugCodeEnum Interface</span></span>

<span data-ttu-id="002b3-103">Implementa los métodos "ICorDebugEnum" y enumera las matrices "ICorDebugCode".</span><span class="sxs-lookup"><span data-stu-id="002b3-103">Implements "ICorDebugEnum" methods, and enumerates "ICorDebugCode" arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="002b3-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="002b3-104">Methods</span></span>  
  
|<span data-ttu-id="002b3-105">Método</span><span class="sxs-lookup"><span data-stu-id="002b3-105">Method</span></span>|<span data-ttu-id="002b3-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="002b3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="002b3-107">Next (Método)</span><span class="sxs-lookup"><span data-stu-id="002b3-107">Next Method</span></span>](icordebugcodeenum-next-method.md)|<span data-ttu-id="002b3-108">Obtiene el número especificado de `ICorDebugCode` instancias de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="002b3-108">Gets the specified number of `ICorDebugCode` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="002b3-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="002b3-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="002b3-110">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="002b3-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="002b3-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="002b3-111">Requirements</span></span>  

 <span data-ttu-id="002b3-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="002b3-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="002b3-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="002b3-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="002b3-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="002b3-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="002b3-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="002b3-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="002b3-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="002b3-116">See also</span></span>

- [<span data-ttu-id="002b3-117">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="002b3-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
