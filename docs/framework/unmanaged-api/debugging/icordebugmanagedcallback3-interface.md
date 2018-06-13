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
ms.openlocfilehash: 6aab35aa5580b53dda513369066ff77f55230265
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33419856"
---
# <a name="icordebugmanagedcallback3-interface"></a><span data-ttu-id="02831-102">ICorDebugManagedCallback3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="02831-102">ICorDebugManagedCallback3 Interface</span></span>
<span data-ttu-id="02831-103">Proporciona un método de devolución de llamada que indica que se ha producido una notificación del depurador personalizada habilitada.</span><span class="sxs-lookup"><span data-stu-id="02831-103">Provides a callback method that indicates that an enabled custom debugger notification has been raised.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="02831-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="02831-104">Methods</span></span>  
  
|<span data-ttu-id="02831-105">Método</span><span class="sxs-lookup"><span data-stu-id="02831-105">Method</span></span>|<span data-ttu-id="02831-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="02831-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="02831-107">CustomNotification (método)</span><span class="sxs-lookup"><span data-stu-id="02831-107">CustomNotification Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md)|<span data-ttu-id="02831-108">Indica que se ha producido una notificación del depurador personalizada habilitada.</span><span class="sxs-lookup"><span data-stu-id="02831-108">Indicates that an enabled custom debugger notification has been raised.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="02831-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="02831-109">Remarks</span></span>  
 <span data-ttu-id="02831-110">Esta interfaz es una extensión lógica de la [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) y [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) interfaces.</span><span class="sxs-lookup"><span data-stu-id="02831-110">This interface is a logical extension of the [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) and [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) interfaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="02831-111">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="02831-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02831-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="02831-112">Requirements</span></span>  
 <span data-ttu-id="02831-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="02831-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02831-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="02831-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="02831-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="02831-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="02831-116">**Versiones de .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02831-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02831-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="02831-117">See Also</span></span>  
 [<span data-ttu-id="02831-118">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="02831-118">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)  
 [<span data-ttu-id="02831-119">ICorDebugManagedCallback2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="02831-119">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [<span data-ttu-id="02831-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="02831-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="02831-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="02831-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
