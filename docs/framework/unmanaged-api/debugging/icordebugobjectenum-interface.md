---
title: Interfaz ICorDebugObjectEnum
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
ms.openlocfilehash: 1faa78150659b4397cd4174583b607e1f7841b8f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943360"
---
# <a name="icordebugobjectenum-interface"></a><span data-ttu-id="b2179-102">Interfaz ICorDebugObjectEnum</span><span class="sxs-lookup"><span data-stu-id="b2179-102">ICorDebugObjectEnum Interface</span></span>

<span data-ttu-id="b2179-103">Implementa los métodos ICorDebugEnum y enumera las matrices de objetos por sus direcciones virtuales relativas (RVA).</span><span class="sxs-lookup"><span data-stu-id="b2179-103">Implements ICorDebugEnum methods, and enumerates arrays of objects by their relative virtual addresses (RVAs).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b2179-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="b2179-104">Methods</span></span>  
  
|<span data-ttu-id="b2179-105">Método</span><span class="sxs-lookup"><span data-stu-id="b2179-105">Method</span></span>|<span data-ttu-id="b2179-106">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="b2179-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b2179-107">Next (método)</span><span class="sxs-lookup"><span data-stu-id="b2179-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectenum-next-method.md)|<span data-ttu-id="b2179-108">Obtiene las RVA del número especificado de objetos de la enumeración, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="b2179-108">Gets the RVAs of the specified number of objects from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b2179-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b2179-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b2179-110">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="b2179-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2179-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b2179-111">Requirements</span></span>  
 <span data-ttu-id="b2179-112">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2179-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2179-113">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="b2179-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b2179-114">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b2179-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b2179-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2179-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2179-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="b2179-116">See also</span></span>

- [<span data-ttu-id="b2179-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="b2179-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
