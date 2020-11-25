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
ms.openlocfilehash: a17c46d5ef08963bb0d7fc280ba8b90531e41c5b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719637"
---
# <a name="icordebuginternalframe2-interface"></a><span data-ttu-id="1f961-102">ICorDebugInternalFrame2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1f961-102">ICorDebugInternalFrame2 Interface</span></span>

<span data-ttu-id="1f961-103">Proporciona información sobre los marcos internos, incluyendo la dirección de la pila y la posición con respecto a los objetos ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="1f961-103">Provides information about internal frames, including stack address and position in relation to ICorDebugFrame objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1f961-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="1f961-104">Methods</span></span>  
  
|<span data-ttu-id="1f961-105">Método</span><span class="sxs-lookup"><span data-stu-id="1f961-105">Method</span></span>|<span data-ttu-id="1f961-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="1f961-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1f961-107">Método GetFrameAddress</span><span class="sxs-lookup"><span data-stu-id="1f961-107">GetFrameAddress Method</span></span>](icordebuginternalframe2-getframeaddress-method.md)|<span data-ttu-id="1f961-108">Devuelve la dirección de la pila del marco interno.</span><span class="sxs-lookup"><span data-stu-id="1f961-108">Returns the stack address of the internal frame.</span></span>|  
|[<span data-ttu-id="1f961-109">Método IsCloserToLeaf</span><span class="sxs-lookup"><span data-stu-id="1f961-109">IsCloserToLeaf Method</span></span>](icordebuginternalframe2-isclosertoleaf-method.md)|<span data-ttu-id="1f961-110">Comprueba si el `this` marco interno está más cerca de la hoja que el objeto ICorDebugFrame especificado.</span><span class="sxs-lookup"><span data-stu-id="1f961-110">Checks whether the `this` internal frame is closer to the leaf than the specified ICorDebugFrame object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1f961-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1f961-111">Remarks</span></span>  

 <span data-ttu-id="1f961-112">Esta interfaz extiende la interfaz ICorDebugInternalFrame (.</span><span class="sxs-lookup"><span data-stu-id="1f961-112">This interface extends the ICorDebugInternalFrame interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1f961-113">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="1f961-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f961-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1f961-114">Requirements</span></span>  

 <span data-ttu-id="1f961-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1f961-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f961-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1f961-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1f961-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1f961-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1f961-118">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f961-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f961-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1f961-119">See also</span></span>

- [<span data-ttu-id="1f961-120">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="1f961-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="1f961-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="1f961-121">Debugging</span></span>](index.md)
