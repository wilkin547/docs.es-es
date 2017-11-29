---
title: ICorDebugThread4 (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread4
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread4
helpviewer_keywords: ICorDebugThread4 interface [.NET Framework debugging]
ms.assetid: a8c7719a-322b-4133-8566-4c27218dc104
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e54611a38193a05a33381e798a61977d7aec41a6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugthread4-interface"></a><span data-ttu-id="1bfe3-102">ICorDebugThread4 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1bfe3-102">ICorDebugThread4 Interface</span></span>
<span data-ttu-id="1bfe3-103">Proporciona información de bloqueo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="1bfe3-103">Provides thread blocking information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1bfe3-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="1bfe3-104">Methods</span></span>  
  
|<span data-ttu-id="1bfe3-105">Método</span><span class="sxs-lookup"><span data-stu-id="1bfe3-105">Method</span></span>|<span data-ttu-id="1bfe3-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="1bfe3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1bfe3-107">GetBlockingObjects (método)</span><span class="sxs-lookup"><span data-stu-id="1bfe3-107">GetBlockingObjects Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-getblockingobjects-method.md)|<span data-ttu-id="1bfe3-108">Proporciona una enumeración ordenada de [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) estructuras que proporcionan información de bloqueo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="1bfe3-108">Provides an ordered enumeration of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures that provide thread blocking information.</span></span>|  
|[<span data-ttu-id="1bfe3-109">HadUnhandledException (método)</span><span class="sxs-lookup"><span data-stu-id="1bfe3-109">HadUnhandledException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-hadunhandledexception-method.md)|<span data-ttu-id="1bfe3-110">Indica si el subproceso nunca ha tenido una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="1bfe3-110">Indicates whether the thread has ever had an unhandled exception.</span></span>|  
|[<span data-ttu-id="1bfe3-111">GetCurrentCustomDebuggerNotification (método)</span><span class="sxs-lookup"><span data-stu-id="1bfe3-111">GetCurrentCustomDebuggerNotification Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-getcurrentcustomdebuggernotification-method.md)|<span data-ttu-id="1bfe3-112">Obtiene el actual [ICorDebugManagedCallback3:: CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) objeto en el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="1bfe3-112">Gets the current [ICorDebugManagedCallback3::CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) object on the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1bfe3-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1bfe3-113">Remarks</span></span>  
 <span data-ttu-id="1bfe3-114">Esta interfaz es una extensión lógica de la ICorDebugThread, ICorDebugThread2, y [ICorDebugThread3](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-interface.md) interfaces.</span><span class="sxs-lookup"><span data-stu-id="1bfe3-114">This interface is a logical extension of the ICorDebugThread, ICorDebugThread2, and [ICorDebugThread3](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-interface.md) interfaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1bfe3-115">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="1bfe3-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1bfe3-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1bfe3-116">Requirements</span></span>  
 <span data-ttu-id="1bfe3-117">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1bfe3-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1bfe3-118">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1bfe3-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1bfe3-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1bfe3-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1bfe3-120">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1bfe3-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bfe3-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="1bfe3-121">See Also</span></span>  
 [<span data-ttu-id="1bfe3-122">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="1bfe3-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="1bfe3-123">Depuración</span><span class="sxs-lookup"><span data-stu-id="1bfe3-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
