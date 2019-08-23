---
title: ICorDebugInternalFrame2 (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame2
helpviewer_keywords:
- ICorDebugInternalFrame2 interface [.NET Framework debugging]
ms.assetid: d4755569-85b8-4ff4-bf50-0e608e76429f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2377773b471b387376f0284522ebe29d6b003ae3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69910112"
---
# <a name="icordebuginternalframe2-interface"></a><span data-ttu-id="28e9d-102">ICorDebugInternalFrame2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="28e9d-102">ICorDebugInternalFrame2 Interface</span></span>
<span data-ttu-id="28e9d-103">Proporciona información sobre los marcos internos, incluida la dirección de pila y la posición en relación con los objetos ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="28e9d-103">Provides information about internal frames, including stack address and position in relation to ICorDebugFrame objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="28e9d-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="28e9d-104">Methods</span></span>  
  
|<span data-ttu-id="28e9d-105">Método</span><span class="sxs-lookup"><span data-stu-id="28e9d-105">Method</span></span>|<span data-ttu-id="28e9d-106">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="28e9d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="28e9d-107">GetFrameAddress (método)</span><span class="sxs-lookup"><span data-stu-id="28e9d-107">GetFrameAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-getframeaddress-method.md)|<span data-ttu-id="28e9d-108">Devuelve la dirección de la pila del marco interno.</span><span class="sxs-lookup"><span data-stu-id="28e9d-108">Returns the stack address of the internal frame.</span></span>|  
|[<span data-ttu-id="28e9d-109">IsCloserToLeaf (método)</span><span class="sxs-lookup"><span data-stu-id="28e9d-109">IsCloserToLeaf Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-isclosertoleaf-method.md)|<span data-ttu-id="28e9d-110">Comprueba si el `this` marco interno está más cerca de la hoja que el objeto ICorDebugFrame especificado.</span><span class="sxs-lookup"><span data-stu-id="28e9d-110">Checks whether the `this` internal frame is closer to the leaf than the specified ICorDebugFrame object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="28e9d-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="28e9d-111">Remarks</span></span>  
 <span data-ttu-id="28e9d-112">Esta interfaz extiende la interfaz ICorDebugInternalFrame (.</span><span class="sxs-lookup"><span data-stu-id="28e9d-112">This interface extends the ICorDebugInternalFrame interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="28e9d-113">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="28e9d-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28e9d-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="28e9d-114">Requirements</span></span>  
 <span data-ttu-id="28e9d-115">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="28e9d-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28e9d-116">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="28e9d-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="28e9d-117">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="28e9d-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="28e9d-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28e9d-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28e9d-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="28e9d-119">See also</span></span>

- [<span data-ttu-id="28e9d-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="28e9d-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="28e9d-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="28e9d-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
