---
description: 'Más información acerca de: interfaz Icordebugmanagedcallback3 ('
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
ms.openlocfilehash: 9fb3d44b1d793935ac997e8e4d8d86de4466f7b2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801194"
---
# <a name="icordebugmanagedcallback3-interface"></a><span data-ttu-id="51e26-103">ICorDebugManagedCallback3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="51e26-103">ICorDebugManagedCallback3 Interface</span></span>

<span data-ttu-id="51e26-104">Proporciona un método de devolución de llamada que indica que se ha producido una notificación del depurador personalizada habilitada.</span><span class="sxs-lookup"><span data-stu-id="51e26-104">Provides a callback method that indicates that an enabled custom debugger notification has been raised.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="51e26-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="51e26-105">Methods</span></span>  
  
|<span data-ttu-id="51e26-106">Método</span><span class="sxs-lookup"><span data-stu-id="51e26-106">Method</span></span>|<span data-ttu-id="51e26-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="51e26-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="51e26-108">Método CustomNotification</span><span class="sxs-lookup"><span data-stu-id="51e26-108">CustomNotification Method</span></span>](icordebugmanagedcallback3-customnotification-method.md)|<span data-ttu-id="51e26-109">Indica que se ha generado una notificación de depurador personalizada habilitada.</span><span class="sxs-lookup"><span data-stu-id="51e26-109">Indicates that an enabled custom debugger notification has been raised.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="51e26-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="51e26-110">Remarks</span></span>  

 <span data-ttu-id="51e26-111">Esta interfaz es una extensión lógica de las interfaces [ICorDebugManagedCallback](icordebugmanagedcallback-interface.md) e [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="51e26-111">This interface is a logical extension of the [ICorDebugManagedCallback](icordebugmanagedcallback-interface.md) and [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="51e26-112">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="51e26-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51e26-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="51e26-113">Requirements</span></span>  

 <span data-ttu-id="51e26-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51e26-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51e26-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="51e26-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="51e26-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="51e26-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="51e26-117">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51e26-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51e26-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="51e26-118">See also</span></span>

- [<span data-ttu-id="51e26-119">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="51e26-119">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
- [<span data-ttu-id="51e26-120">ICorDebugManagedCallback2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="51e26-120">ICorDebugManagedCallback2 Interface</span></span>](icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="51e26-121">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="51e26-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="51e26-122">Depuración</span><span class="sxs-lookup"><span data-stu-id="51e26-122">Debugging</span></span>](index.md)
