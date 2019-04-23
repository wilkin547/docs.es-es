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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5a23d21d0ed8c6a6a226d5e58eafb7bde65a4896
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59161465"
---
# <a name="icordebugblockingobjectenum-interface"></a><span data-ttu-id="9302b-102">ICorDebugBlockingObjectEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9302b-102">ICorDebugBlockingObjectEnum Interface</span></span>
<span data-ttu-id="9302b-103">Proporciona un enumerador para una lista de [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) estructuras.</span><span class="sxs-lookup"><span data-stu-id="9302b-103">Provides an enumerator for a list of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span> <span data-ttu-id="9302b-104">Esta interfaz es una subclase de ICorDebugEnum (interfaz).</span><span class="sxs-lookup"><span data-stu-id="9302b-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9302b-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="9302b-105">Methods</span></span>  
  
|<span data-ttu-id="9302b-106">Método</span><span class="sxs-lookup"><span data-stu-id="9302b-106">Method</span></span>|<span data-ttu-id="9302b-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="9302b-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9302b-108">Next (método)</span><span class="sxs-lookup"><span data-stu-id="9302b-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-next-method.md)|<span data-ttu-id="9302b-109">Enumera una lista de [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) estructuras.</span><span class="sxs-lookup"><span data-stu-id="9302b-109">Enumerates through a list of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9302b-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9302b-110">Remarks</span></span>  
 <span data-ttu-id="9302b-111">Cada estructura `CorDebugBlockingObject` representa un objeto que está bloqueando un subproceso.</span><span class="sxs-lookup"><span data-stu-id="9302b-111">Each `CorDebugBlockingObject` structure represents an object that is blocking a thread.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9302b-112">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="9302b-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9302b-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9302b-113">Requirements</span></span>  
 <span data-ttu-id="9302b-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9302b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9302b-115">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9302b-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9302b-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9302b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9302b-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9302b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9302b-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="9302b-118">See also</span></span>

- [<span data-ttu-id="9302b-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="9302b-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="9302b-120">Depuración</span><span class="sxs-lookup"><span data-stu-id="9302b-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
