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
ms.openlocfilehash: dd867db8886c1c74d209e080b6b810ed4adc3654
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54589339"
---
# <a name="icordebuginternalframe2-interface"></a><span data-ttu-id="028cd-102">ICorDebugInternalFrame2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="028cd-102">ICorDebugInternalFrame2 Interface</span></span>
<span data-ttu-id="028cd-103">Proporciona información sobre los marcos internos, incluyendo la dirección de la pila y la posición en relación con los objetos ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="028cd-103">Provides information about internal frames, including stack address and position in relation to ICorDebugFrame objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="028cd-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="028cd-104">Methods</span></span>  
  
|<span data-ttu-id="028cd-105">Método</span><span class="sxs-lookup"><span data-stu-id="028cd-105">Method</span></span>|<span data-ttu-id="028cd-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="028cd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="028cd-107">GetFrameAddress (método)</span><span class="sxs-lookup"><span data-stu-id="028cd-107">GetFrameAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-getframeaddress-method.md)|<span data-ttu-id="028cd-108">Devuelve la dirección de pila del marco interno.</span><span class="sxs-lookup"><span data-stu-id="028cd-108">Returns the stack address of the internal frame.</span></span>|  
|[<span data-ttu-id="028cd-109">IsCloserToLeaf (método)</span><span class="sxs-lookup"><span data-stu-id="028cd-109">IsCloserToLeaf Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-isclosertoleaf-method.md)|<span data-ttu-id="028cd-110">Comprueba si el `this` marco interno está más cerca de la hoja que el objeto ICorDebugFrame especificado.</span><span class="sxs-lookup"><span data-stu-id="028cd-110">Checks whether the `this` internal frame is closer to the leaf than the specified ICorDebugFrame object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="028cd-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="028cd-111">Remarks</span></span>  
 <span data-ttu-id="028cd-112">Esta interfaz extiende ICorDebugInternalFrame (interfaz).</span><span class="sxs-lookup"><span data-stu-id="028cd-112">This interface extends the ICorDebugInternalFrame interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="028cd-113">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="028cd-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="028cd-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="028cd-114">Requirements</span></span>  
 <span data-ttu-id="028cd-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="028cd-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="028cd-116">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="028cd-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="028cd-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="028cd-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="028cd-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="028cd-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="028cd-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="028cd-119">See also</span></span>
- [<span data-ttu-id="028cd-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="028cd-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="028cd-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="028cd-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
