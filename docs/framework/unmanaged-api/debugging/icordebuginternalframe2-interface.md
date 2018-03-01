---
title: ICorDebugInternalFrame2 (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d87303fbe95804b458a42ed43b65f29233814977
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebuginternalframe2-interface"></a><span data-ttu-id="0c207-102">ICorDebugInternalFrame2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0c207-102">ICorDebugInternalFrame2 Interface</span></span>
<span data-ttu-id="0c207-103">Proporciona información sobre los marcos internos, incluyendo la dirección de la pila y la posición en relación con objetos ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="0c207-103">Provides information about internal frames, including stack address and position in relation to ICorDebugFrame objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0c207-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="0c207-104">Methods</span></span>  
  
|<span data-ttu-id="0c207-105">Método</span><span class="sxs-lookup"><span data-stu-id="0c207-105">Method</span></span>|<span data-ttu-id="0c207-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="0c207-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0c207-107">GetFrameAddress (método)</span><span class="sxs-lookup"><span data-stu-id="0c207-107">GetFrameAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-getframeaddress-method.md)|<span data-ttu-id="0c207-108">Devuelve la dirección de la pila del marco interno.</span><span class="sxs-lookup"><span data-stu-id="0c207-108">Returns the stack address of the internal frame.</span></span>|  
|[<span data-ttu-id="0c207-109">IsCloserToLeaf (método)</span><span class="sxs-lookup"><span data-stu-id="0c207-109">IsCloserToLeaf Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-isclosertoleaf-method.md)|<span data-ttu-id="0c207-110">Comprueba si el `this` marco interno está más cerca de la hoja que el objeto ICorDebugFrame especificado.</span><span class="sxs-lookup"><span data-stu-id="0c207-110">Checks whether the `this` internal frame is closer to the leaf than the specified ICorDebugFrame object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0c207-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0c207-111">Remarks</span></span>  
 <span data-ttu-id="0c207-112">Esta interfaz extiende ICorDebugInternalFrame (interfaz).</span><span class="sxs-lookup"><span data-stu-id="0c207-112">This interface extends the ICorDebugInternalFrame interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0c207-113">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="0c207-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c207-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0c207-114">Requirements</span></span>  
 <span data-ttu-id="0c207-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0c207-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c207-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0c207-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0c207-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0c207-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0c207-118">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c207-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c207-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="0c207-119">See Also</span></span>  
 [<span data-ttu-id="0c207-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="0c207-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="0c207-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="0c207-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
