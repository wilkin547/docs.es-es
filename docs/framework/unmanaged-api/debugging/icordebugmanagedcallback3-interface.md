---
title: ICorDebugManagedCallback3 (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback3
helpviewer_keywords:
- ICorDebugManagedCallback3 interface [.NET Framework debugging]
ms.assetid: a95389d3-cf2e-47a4-9805-61426acc6b65
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 138ac80a9abb64d4c004e83e53ed1eea2b124ff2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69909906"
---
# <a name="icordebugmanagedcallback3-interface"></a><span data-ttu-id="e9aa8-102">ICorDebugManagedCallback3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e9aa8-102">ICorDebugManagedCallback3 Interface</span></span>
<span data-ttu-id="e9aa8-103">Proporciona un método de devolución de llamada que indica que se ha producido una notificación del depurador personalizada habilitada.</span><span class="sxs-lookup"><span data-stu-id="e9aa8-103">Provides a callback method that indicates that an enabled custom debugger notification has been raised.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e9aa8-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="e9aa8-104">Methods</span></span>  
  
|<span data-ttu-id="e9aa8-105">Método</span><span class="sxs-lookup"><span data-stu-id="e9aa8-105">Method</span></span>|<span data-ttu-id="e9aa8-106">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="e9aa8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e9aa8-107">CustomNotification (método)</span><span class="sxs-lookup"><span data-stu-id="e9aa8-107">CustomNotification Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md)|<span data-ttu-id="e9aa8-108">Indica que se ha generado una notificación de depurador personalizada habilitada.</span><span class="sxs-lookup"><span data-stu-id="e9aa8-108">Indicates that an enabled custom debugger notification has been raised.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e9aa8-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e9aa8-109">Remarks</span></span>  
 <span data-ttu-id="e9aa8-110">Esta interfaz es una extensión lógica de las interfaces [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) e [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="e9aa8-110">This interface is a logical extension of the [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) and [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e9aa8-111">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="e9aa8-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9aa8-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e9aa8-112">Requirements</span></span>  
 <span data-ttu-id="e9aa8-113">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9aa8-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9aa8-114">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="e9aa8-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e9aa8-115">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e9aa8-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e9aa8-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9aa8-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9aa8-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="e9aa8-117">See also</span></span>

- [<span data-ttu-id="e9aa8-118">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e9aa8-118">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
- [<span data-ttu-id="e9aa8-119">ICorDebugManagedCallback2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e9aa8-119">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="e9aa8-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="e9aa8-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="e9aa8-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="e9aa8-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
