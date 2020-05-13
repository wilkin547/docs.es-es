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
ms.openlocfilehash: ce3ca4745727a1738fdc1a526480d70ffc55ccf8
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209908"
---
# <a name="icordebuginternalframe2-interface"></a><span data-ttu-id="57fb4-102">ICorDebugInternalFrame2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="57fb4-102">ICorDebugInternalFrame2 Interface</span></span>
<span data-ttu-id="57fb4-103">Proporciona información sobre los marcos internos, incluyendo la dirección de la pila y la posición con respecto a los objetos ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="57fb4-103">Provides information about internal frames, including stack address and position in relation to ICorDebugFrame objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="57fb4-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="57fb4-104">Methods</span></span>  
  
|<span data-ttu-id="57fb4-105">Método</span><span class="sxs-lookup"><span data-stu-id="57fb4-105">Method</span></span>|<span data-ttu-id="57fb4-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="57fb4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="57fb4-107">Método GetFrameAddress</span><span class="sxs-lookup"><span data-stu-id="57fb4-107">GetFrameAddress Method</span></span>](icordebuginternalframe2-getframeaddress-method.md)|<span data-ttu-id="57fb4-108">Devuelve la dirección de la pila del marco interno.</span><span class="sxs-lookup"><span data-stu-id="57fb4-108">Returns the stack address of the internal frame.</span></span>|  
|[<span data-ttu-id="57fb4-109">Método IsCloserToLeaf</span><span class="sxs-lookup"><span data-stu-id="57fb4-109">IsCloserToLeaf Method</span></span>](icordebuginternalframe2-isclosertoleaf-method.md)|<span data-ttu-id="57fb4-110">Comprueba si el `this` marco interno está más cerca de la hoja que el objeto ICorDebugFrame especificado.</span><span class="sxs-lookup"><span data-stu-id="57fb4-110">Checks whether the `this` internal frame is closer to the leaf than the specified ICorDebugFrame object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="57fb4-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="57fb4-111">Remarks</span></span>  
 <span data-ttu-id="57fb4-112">Esta interfaz extiende la interfaz ICorDebugInternalFrame (.</span><span class="sxs-lookup"><span data-stu-id="57fb4-112">This interface extends the ICorDebugInternalFrame interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="57fb4-113">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="57fb4-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="57fb4-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="57fb4-114">Requirements</span></span>  
 <span data-ttu-id="57fb4-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="57fb4-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57fb4-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="57fb4-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="57fb4-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="57fb4-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="57fb4-118">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57fb4-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57fb4-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="57fb4-119">See also</span></span>

- [<span data-ttu-id="57fb4-120">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="57fb4-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="57fb4-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="57fb4-121">Debugging</span></span>](index.md)
