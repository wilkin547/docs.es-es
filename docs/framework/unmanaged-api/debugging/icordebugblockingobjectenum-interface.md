---
title: ICorDebugBlockingObjectEnum (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugBlockingObjectEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBlockingObjectEnum
helpviewer_keywords:
- ICorDebugBlockingObjectEnum interface [.NET Framework debugging]
ms.assetid: 208e5c2d-3f3f-404e-8b3c-7cccc14ddb16
topic_type:
- apiref
ms.openlocfilehash: 221acf9bea714728a81b9f15c8165c1f9eba16a8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719208"
---
# <a name="icordebugblockingobjectenum-interface"></a><span data-ttu-id="ee1e5-102">ICorDebugBlockingObjectEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ee1e5-102">ICorDebugBlockingObjectEnum Interface</span></span>

<span data-ttu-id="ee1e5-103">Proporciona un enumerador para una lista de estructuras [CorDebugBlockingObject](cordebugblockingobject-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="ee1e5-103">Provides an enumerator for a list of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures.</span></span> <span data-ttu-id="ee1e5-104">Esta interfaz es una subclase de la interfaz ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="ee1e5-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ee1e5-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="ee1e5-105">Methods</span></span>  
  
|<span data-ttu-id="ee1e5-106">Método</span><span class="sxs-lookup"><span data-stu-id="ee1e5-106">Method</span></span>|<span data-ttu-id="ee1e5-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="ee1e5-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ee1e5-108">Next (Método)</span><span class="sxs-lookup"><span data-stu-id="ee1e5-108">Next Method</span></span>](icordebugblockingobjectenum-next-method.md)|<span data-ttu-id="ee1e5-109">Enumera a través de una lista de estructuras [CorDebugBlockingObject](cordebugblockingobject-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="ee1e5-109">Enumerates through a list of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ee1e5-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ee1e5-110">Remarks</span></span>  

 <span data-ttu-id="ee1e5-111">Cada estructura `CorDebugBlockingObject` representa un objeto que está bloqueando un subproceso.</span><span class="sxs-lookup"><span data-stu-id="ee1e5-111">Each `CorDebugBlockingObject` structure represents an object that is blocking a thread.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ee1e5-112">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="ee1e5-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee1e5-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ee1e5-113">Requirements</span></span>  

 <span data-ttu-id="ee1e5-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ee1e5-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee1e5-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ee1e5-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ee1e5-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ee1e5-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ee1e5-117">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee1e5-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee1e5-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ee1e5-118">See also</span></span>

- [<span data-ttu-id="ee1e5-119">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="ee1e5-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="ee1e5-120">Depuración</span><span class="sxs-lookup"><span data-stu-id="ee1e5-120">Debugging</span></span>](index.md)
