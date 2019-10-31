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
ms.openlocfilehash: 5a451218e0fdc32132a4e79d091ada8355d32fe7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122694"
---
# <a name="icordebuginternalframe2-interface"></a><span data-ttu-id="617ea-102">ICorDebugInternalFrame2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="617ea-102">ICorDebugInternalFrame2 Interface</span></span>
<span data-ttu-id="617ea-103">Proporciona información sobre los marcos internos, incluida la dirección de pila y la posición en relación con los objetos ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="617ea-103">Provides information about internal frames, including stack address and position in relation to ICorDebugFrame objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="617ea-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="617ea-104">Methods</span></span>  
  
|<span data-ttu-id="617ea-105">Método</span><span class="sxs-lookup"><span data-stu-id="617ea-105">Method</span></span>|<span data-ttu-id="617ea-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="617ea-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="617ea-107">GetFrameAddress (método)</span><span class="sxs-lookup"><span data-stu-id="617ea-107">GetFrameAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-getframeaddress-method.md)|<span data-ttu-id="617ea-108">Devuelve la dirección de la pila del marco interno.</span><span class="sxs-lookup"><span data-stu-id="617ea-108">Returns the stack address of the internal frame.</span></span>|  
|[<span data-ttu-id="617ea-109">IsCloserToLeaf (método)</span><span class="sxs-lookup"><span data-stu-id="617ea-109">IsCloserToLeaf Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-isclosertoleaf-method.md)|<span data-ttu-id="617ea-110">Comprueba si el marco interno `this` está más próximo a la hoja que el objeto ICorDebugFrame especificado.</span><span class="sxs-lookup"><span data-stu-id="617ea-110">Checks whether the `this` internal frame is closer to the leaf than the specified ICorDebugFrame object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="617ea-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="617ea-111">Remarks</span></span>  
 <span data-ttu-id="617ea-112">Esta interfaz extiende la interfaz ICorDebugInternalFrame (.</span><span class="sxs-lookup"><span data-stu-id="617ea-112">This interface extends the ICorDebugInternalFrame interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="617ea-113">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="617ea-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="617ea-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="617ea-114">Requirements</span></span>  
 <span data-ttu-id="617ea-115">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="617ea-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="617ea-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="617ea-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="617ea-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="617ea-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="617ea-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="617ea-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="617ea-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="617ea-119">See also</span></span>

- [<span data-ttu-id="617ea-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="617ea-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="617ea-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="617ea-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
