---
title: ICorDebugBlockingObjectEnum (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugBlockingObjectEnum
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugBlockingObjectEnum
helpviewer_keywords: ICorDebugBlockingObjectEnum interface [.NET Framework debugging]
ms.assetid: 208e5c2d-3f3f-404e-8b3c-7cccc14ddb16
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b62da4047029881ddffff5faee9f06072407bfc6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugblockingobjectenum-interface"></a><span data-ttu-id="8fd41-102">ICorDebugBlockingObjectEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8fd41-102">ICorDebugBlockingObjectEnum Interface</span></span>
<span data-ttu-id="8fd41-103">Proporciona un enumerador para una lista de [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) estructuras.</span><span class="sxs-lookup"><span data-stu-id="8fd41-103">Provides an enumerator for a list of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span> <span data-ttu-id="8fd41-104">Esta interfaz es una subclase de ICorDebugEnum (interfaz).</span><span class="sxs-lookup"><span data-stu-id="8fd41-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8fd41-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="8fd41-105">Methods</span></span>  
  
|<span data-ttu-id="8fd41-106">Método</span><span class="sxs-lookup"><span data-stu-id="8fd41-106">Method</span></span>|<span data-ttu-id="8fd41-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="8fd41-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8fd41-108">Next (método)</span><span class="sxs-lookup"><span data-stu-id="8fd41-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-next-method.md)|<span data-ttu-id="8fd41-109">Enumera una lista de [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) estructuras.</span><span class="sxs-lookup"><span data-stu-id="8fd41-109">Enumerates through a list of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8fd41-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8fd41-110">Remarks</span></span>  
 <span data-ttu-id="8fd41-111">Cada estructura `CorDebugBlockingObject` representa un objeto que está bloqueando un subproceso.</span><span class="sxs-lookup"><span data-stu-id="8fd41-111">Each `CorDebugBlockingObject` structure represents an object that is blocking a thread.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8fd41-112">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="8fd41-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8fd41-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8fd41-113">Requirements</span></span>  
 <span data-ttu-id="8fd41-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8fd41-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8fd41-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8fd41-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8fd41-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8fd41-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8fd41-117">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8fd41-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fd41-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="8fd41-118">See Also</span></span>  
 [<span data-ttu-id="8fd41-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="8fd41-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="8fd41-120">Depuración</span><span class="sxs-lookup"><span data-stu-id="8fd41-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
