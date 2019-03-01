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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 452216a2ba4e8013d107977d82eae1508b2aba78
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56967768"
---
# <a name="icordebugobjectenum-interface"></a><span data-ttu-id="9c68b-102">ICorDebugObjectEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9c68b-102">ICorDebugObjectEnum Interface</span></span>

<span data-ttu-id="9c68b-103">Implementa los métodos ICorDebugEnum y enumera las matrices de objetos según sus direcciones virtuales relativas (RVA).</span><span class="sxs-lookup"><span data-stu-id="9c68b-103">Implements ICorDebugEnum methods, and enumerates arrays of objects by their relative virtual addresses (RVAs).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9c68b-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="9c68b-104">Methods</span></span>  
  
|<span data-ttu-id="9c68b-105">Método</span><span class="sxs-lookup"><span data-stu-id="9c68b-105">Method</span></span>|<span data-ttu-id="9c68b-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="9c68b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9c68b-107">Next (método)</span><span class="sxs-lookup"><span data-stu-id="9c68b-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectenum-next-method.md)|<span data-ttu-id="9c68b-108">Obtiene las RVA del número especificado de objetos de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="9c68b-108">Gets the RVAs of the specified number of objects from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9c68b-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9c68b-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9c68b-110">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="9c68b-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c68b-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9c68b-111">Requirements</span></span>  
 <span data-ttu-id="9c68b-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9c68b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c68b-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9c68b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9c68b-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9c68b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9c68b-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c68b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c68b-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="9c68b-116">See also</span></span>
- [<span data-ttu-id="9c68b-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="9c68b-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
