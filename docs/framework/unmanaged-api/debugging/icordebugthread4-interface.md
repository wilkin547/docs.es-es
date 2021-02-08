---
description: 'Más información acerca de: interfaz ICorDebugThread4'
title: ICorDebugThread4 (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugThread4
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread4
helpviewer_keywords:
- ICorDebugThread4 interface [.NET Framework debugging]
ms.assetid: a8c7719a-322b-4133-8566-4c27218dc104
topic_type:
- apiref
ms.openlocfilehash: 4ad587cee81ce635df0a8917b7a6d68e60aaf0b3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800921"
---
# <a name="icordebugthread4-interface"></a><span data-ttu-id="53f63-103">ICorDebugThread4 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="53f63-103">ICorDebugThread4 Interface</span></span>

<span data-ttu-id="53f63-104">Proporciona información de bloqueo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="53f63-104">Provides thread blocking information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="53f63-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="53f63-105">Methods</span></span>  
  
|<span data-ttu-id="53f63-106">Método</span><span class="sxs-lookup"><span data-stu-id="53f63-106">Method</span></span>|<span data-ttu-id="53f63-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="53f63-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="53f63-108">Método GetBlockingObjects</span><span class="sxs-lookup"><span data-stu-id="53f63-108">GetBlockingObjects Method</span></span>](icordebugthread4-getblockingobjects-method.md)|<span data-ttu-id="53f63-109">Proporciona una enumeración ordenada de las estructuras [CorDebugBlockingObject](cordebugblockingobject-structure.md) que proporcionan información de bloqueo de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="53f63-109">Provides an ordered enumeration of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures that provide thread blocking information.</span></span>|  
|[<span data-ttu-id="53f63-110">Método HadUnhandledException</span><span class="sxs-lookup"><span data-stu-id="53f63-110">HadUnhandledException Method</span></span>](icordebugthread4-hadunhandledexception-method.md)|<span data-ttu-id="53f63-111">Indica si el subproceso ha tenido alguna vez una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="53f63-111">Indicates whether the thread has ever had an unhandled exception.</span></span>|  
|[<span data-ttu-id="53f63-112">Método GetCurrentCustomDebuggerNotification</span><span class="sxs-lookup"><span data-stu-id="53f63-112">GetCurrentCustomDebuggerNotification Method</span></span>](icordebugthread4-getcurrentcustomdebuggernotification-method.md)|<span data-ttu-id="53f63-113">Obtiene el objeto [ICorDebugManagedCallback3 (:: customnotification (](icordebugmanagedcallback3-customnotification-method.md) actual en el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="53f63-113">Gets the current [ICorDebugManagedCallback3::CustomNotification](icordebugmanagedcallback3-customnotification-method.md) object on the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="53f63-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="53f63-114">Remarks</span></span>  

 <span data-ttu-id="53f63-115">Esta interfaz es una extensión lógica de las interfaces ICorDebugThread, ICorDebugThread2 y [ICorDebugThread3](icordebugthread3-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="53f63-115">This interface is a logical extension of the ICorDebugThread, ICorDebugThread2, and [ICorDebugThread3](icordebugthread3-interface.md) interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="53f63-116">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="53f63-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53f63-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="53f63-117">Requirements</span></span>  

 <span data-ttu-id="53f63-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="53f63-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53f63-119">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="53f63-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="53f63-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="53f63-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="53f63-121">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53f63-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53f63-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="53f63-122">See also</span></span>

- [<span data-ttu-id="53f63-123">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="53f63-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="53f63-124">Depuración</span><span class="sxs-lookup"><span data-stu-id="53f63-124">Debugging</span></span>](index.md)
