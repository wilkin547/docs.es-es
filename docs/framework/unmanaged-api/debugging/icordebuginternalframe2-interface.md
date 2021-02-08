---
description: 'Más información acerca de: interfaz ICorDebugInternalFrame2'
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
ms.openlocfilehash: 3edc666c043513562b2fcece478b2879f294ce33
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791106"
---
# <a name="icordebuginternalframe2-interface"></a><span data-ttu-id="1e11d-103">ICorDebugInternalFrame2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1e11d-103">ICorDebugInternalFrame2 Interface</span></span>

<span data-ttu-id="1e11d-104">Proporciona información sobre los marcos internos, incluyendo la dirección de la pila y la posición con respecto a los objetos ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="1e11d-104">Provides information about internal frames, including stack address and position in relation to ICorDebugFrame objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1e11d-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="1e11d-105">Methods</span></span>  
  
|<span data-ttu-id="1e11d-106">Método</span><span class="sxs-lookup"><span data-stu-id="1e11d-106">Method</span></span>|<span data-ttu-id="1e11d-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="1e11d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1e11d-108">Método GetFrameAddress</span><span class="sxs-lookup"><span data-stu-id="1e11d-108">GetFrameAddress Method</span></span>](icordebuginternalframe2-getframeaddress-method.md)|<span data-ttu-id="1e11d-109">Devuelve la dirección de la pila del marco interno.</span><span class="sxs-lookup"><span data-stu-id="1e11d-109">Returns the stack address of the internal frame.</span></span>|  
|[<span data-ttu-id="1e11d-110">Método IsCloserToLeaf</span><span class="sxs-lookup"><span data-stu-id="1e11d-110">IsCloserToLeaf Method</span></span>](icordebuginternalframe2-isclosertoleaf-method.md)|<span data-ttu-id="1e11d-111">Comprueba si el `this` marco interno está más cerca de la hoja que el objeto ICorDebugFrame especificado.</span><span class="sxs-lookup"><span data-stu-id="1e11d-111">Checks whether the `this` internal frame is closer to the leaf than the specified ICorDebugFrame object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1e11d-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1e11d-112">Remarks</span></span>  

 <span data-ttu-id="1e11d-113">Esta interfaz extiende la interfaz ICorDebugInternalFrame (.</span><span class="sxs-lookup"><span data-stu-id="1e11d-113">This interface extends the ICorDebugInternalFrame interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1e11d-114">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="1e11d-114">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e11d-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1e11d-115">Requirements</span></span>  

 <span data-ttu-id="1e11d-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1e11d-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e11d-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1e11d-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1e11d-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1e11d-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1e11d-119">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e11d-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e11d-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="1e11d-120">See also</span></span>

- [<span data-ttu-id="1e11d-121">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="1e11d-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="1e11d-122">Depuración</span><span class="sxs-lookup"><span data-stu-id="1e11d-122">Debugging</span></span>](index.md)
