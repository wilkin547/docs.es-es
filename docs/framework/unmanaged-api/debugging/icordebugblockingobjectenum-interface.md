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
ms.openlocfilehash: bfd61d985eac3ab56d8a5df9474b2b1a9f641f3e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122845"
---
# <a name="icordebugblockingobjectenum-interface"></a><span data-ttu-id="bf3e8-102">ICorDebugBlockingObjectEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bf3e8-102">ICorDebugBlockingObjectEnum Interface</span></span>
<span data-ttu-id="bf3e8-103">Proporciona un enumerador para una lista de estructuras [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="bf3e8-103">Provides an enumerator for a list of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span> <span data-ttu-id="bf3e8-104">Esta interfaz es una subclase de la interfaz ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="bf3e8-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bf3e8-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="bf3e8-105">Methods</span></span>  
  
|<span data-ttu-id="bf3e8-106">Método</span><span class="sxs-lookup"><span data-stu-id="bf3e8-106">Method</span></span>|<span data-ttu-id="bf3e8-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="bf3e8-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bf3e8-108">Next (método)</span><span class="sxs-lookup"><span data-stu-id="bf3e8-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-next-method.md)|<span data-ttu-id="bf3e8-109">Enumera a través de una lista de estructuras [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="bf3e8-109">Enumerates through a list of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bf3e8-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bf3e8-110">Remarks</span></span>  
 <span data-ttu-id="bf3e8-111">Cada estructura `CorDebugBlockingObject` representa un objeto que está bloqueando un subproceso.</span><span class="sxs-lookup"><span data-stu-id="bf3e8-111">Each `CorDebugBlockingObject` structure represents an object that is blocking a thread.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bf3e8-112">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="bf3e8-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf3e8-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bf3e8-113">Requirements</span></span>  
 <span data-ttu-id="bf3e8-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf3e8-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf3e8-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bf3e8-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bf3e8-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bf3e8-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bf3e8-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf3e8-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf3e8-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="bf3e8-118">See also</span></span>

- [<span data-ttu-id="bf3e8-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="bf3e8-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="bf3e8-120">Depuración</span><span class="sxs-lookup"><span data-stu-id="bf3e8-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
