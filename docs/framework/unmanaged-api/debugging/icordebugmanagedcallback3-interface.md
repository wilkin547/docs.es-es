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
ms.openlocfilehash: 63e3f166c4cbf17f4892dccf770343bfbf6e0284
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209752"
---
# <a name="icordebugmanagedcallback3-interface"></a><span data-ttu-id="66199-102">ICorDebugManagedCallback3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="66199-102">ICorDebugManagedCallback3 Interface</span></span>
<span data-ttu-id="66199-103">Proporciona un método de devolución de llamada que indica que se ha producido una notificación del depurador personalizada habilitada.</span><span class="sxs-lookup"><span data-stu-id="66199-103">Provides a callback method that indicates that an enabled custom debugger notification has been raised.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="66199-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="66199-104">Methods</span></span>  
  
|<span data-ttu-id="66199-105">Método</span><span class="sxs-lookup"><span data-stu-id="66199-105">Method</span></span>|<span data-ttu-id="66199-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="66199-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="66199-107">Método CustomNotification</span><span class="sxs-lookup"><span data-stu-id="66199-107">CustomNotification Method</span></span>](icordebugmanagedcallback3-customnotification-method.md)|<span data-ttu-id="66199-108">Indica que se ha generado una notificación de depurador personalizada habilitada.</span><span class="sxs-lookup"><span data-stu-id="66199-108">Indicates that an enabled custom debugger notification has been raised.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="66199-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="66199-109">Remarks</span></span>  
 <span data-ttu-id="66199-110">Esta interfaz es una extensión lógica de las interfaces [ICorDebugManagedCallback](icordebugmanagedcallback-interface.md) e [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="66199-110">This interface is a logical extension of the [ICorDebugManagedCallback](icordebugmanagedcallback-interface.md) and [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="66199-111">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="66199-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66199-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="66199-112">Requirements</span></span>  
 <span data-ttu-id="66199-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="66199-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66199-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="66199-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="66199-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="66199-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="66199-116">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66199-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66199-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="66199-117">See also</span></span>

- [<span data-ttu-id="66199-118">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="66199-118">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
- [<span data-ttu-id="66199-119">ICorDebugManagedCallback2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="66199-119">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="66199-120">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="66199-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="66199-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="66199-121">Debugging</span></span>](index.md)
