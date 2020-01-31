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
ms.openlocfilehash: be1e1cd0d38ad71de43478af5565bb1ac98a8c0d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76778002"
---
# <a name="icordebugblockingobjectenum-interface"></a><span data-ttu-id="5733e-102">ICorDebugBlockingObjectEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5733e-102">ICorDebugBlockingObjectEnum Interface</span></span>
<span data-ttu-id="5733e-103">Proporciona un enumerador para una lista de estructuras [CorDebugBlockingObject](cordebugblockingobject-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="5733e-103">Provides an enumerator for a list of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures.</span></span> <span data-ttu-id="5733e-104">Esta interfaz es una subclase de la interfaz ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="5733e-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5733e-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="5733e-105">Methods</span></span>  
  
|<span data-ttu-id="5733e-106">Método</span><span class="sxs-lookup"><span data-stu-id="5733e-106">Method</span></span>|<span data-ttu-id="5733e-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="5733e-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5733e-108">Next (método)</span><span class="sxs-lookup"><span data-stu-id="5733e-108">Next Method</span></span>](icordebugblockingobjectenum-next-method.md)|<span data-ttu-id="5733e-109">Enumera a través de una lista de estructuras [CorDebugBlockingObject](cordebugblockingobject-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="5733e-109">Enumerates through a list of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5733e-110">Notas</span><span class="sxs-lookup"><span data-stu-id="5733e-110">Remarks</span></span>  
 <span data-ttu-id="5733e-111">Cada estructura `CorDebugBlockingObject` representa un objeto que está bloqueando un subproceso.</span><span class="sxs-lookup"><span data-stu-id="5733e-111">Each `CorDebugBlockingObject` structure represents an object that is blocking a thread.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5733e-112">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="5733e-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5733e-113">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="5733e-113">Requirements</span></span>  
 <span data-ttu-id="5733e-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5733e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5733e-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5733e-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5733e-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5733e-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5733e-117">**.NET Framework versiones:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5733e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5733e-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="5733e-118">See also</span></span>

- [<span data-ttu-id="5733e-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="5733e-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="5733e-120">Depuración</span><span class="sxs-lookup"><span data-stu-id="5733e-120">Debugging</span></span>](index.md)
