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
ms.openlocfilehash: f22d9d86e2b943a8825e1ec271a401b03f73fb6c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33407019"
---
# <a name="icordebugblockingobjectenum-interface"></a><span data-ttu-id="522e1-102">ICorDebugBlockingObjectEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="522e1-102">ICorDebugBlockingObjectEnum Interface</span></span>
<span data-ttu-id="522e1-103">Proporciona un enumerador para una lista de [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) estructuras.</span><span class="sxs-lookup"><span data-stu-id="522e1-103">Provides an enumerator for a list of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span> <span data-ttu-id="522e1-104">Esta interfaz es una subclase de ICorDebugEnum (interfaz).</span><span class="sxs-lookup"><span data-stu-id="522e1-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="522e1-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="522e1-105">Methods</span></span>  
  
|<span data-ttu-id="522e1-106">Método</span><span class="sxs-lookup"><span data-stu-id="522e1-106">Method</span></span>|<span data-ttu-id="522e1-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="522e1-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="522e1-108">Next (método)</span><span class="sxs-lookup"><span data-stu-id="522e1-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-next-method.md)|<span data-ttu-id="522e1-109">Enumera una lista de [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) estructuras.</span><span class="sxs-lookup"><span data-stu-id="522e1-109">Enumerates through a list of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="522e1-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="522e1-110">Remarks</span></span>  
 <span data-ttu-id="522e1-111">Cada estructura `CorDebugBlockingObject` representa un objeto que está bloqueando un subproceso.</span><span class="sxs-lookup"><span data-stu-id="522e1-111">Each `CorDebugBlockingObject` structure represents an object that is blocking a thread.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="522e1-112">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="522e1-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="522e1-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="522e1-113">Requirements</span></span>  
 <span data-ttu-id="522e1-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="522e1-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="522e1-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="522e1-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="522e1-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="522e1-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="522e1-117">**Versiones de .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="522e1-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="522e1-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="522e1-118">See Also</span></span>  
 [<span data-ttu-id="522e1-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="522e1-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="522e1-120">Depuración</span><span class="sxs-lookup"><span data-stu-id="522e1-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
