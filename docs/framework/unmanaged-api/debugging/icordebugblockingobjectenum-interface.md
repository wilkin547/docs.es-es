---
description: 'Más información acerca de: interfaz ICorDebugBlockingObjectEnum'
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
ms.openlocfilehash: 4f28039cb8a9bdcb376a9acf22572d29e41a2adf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754074"
---
# <a name="icordebugblockingobjectenum-interface"></a><span data-ttu-id="cb1b0-103">ICorDebugBlockingObjectEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="cb1b0-103">ICorDebugBlockingObjectEnum Interface</span></span>

<span data-ttu-id="cb1b0-104">Proporciona un enumerador para una lista de estructuras [CorDebugBlockingObject](cordebugblockingobject-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="cb1b0-104">Provides an enumerator for a list of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures.</span></span> <span data-ttu-id="cb1b0-105">Esta interfaz es una subclase de la interfaz ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="cb1b0-105">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cb1b0-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="cb1b0-106">Methods</span></span>  
  
|<span data-ttu-id="cb1b0-107">Método</span><span class="sxs-lookup"><span data-stu-id="cb1b0-107">Method</span></span>|<span data-ttu-id="cb1b0-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="cb1b0-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cb1b0-109">Next (método)</span><span class="sxs-lookup"><span data-stu-id="cb1b0-109">Next Method</span></span>](icordebugblockingobjectenum-next-method.md)|<span data-ttu-id="cb1b0-110">Enumera a través de una lista de estructuras [CorDebugBlockingObject](cordebugblockingobject-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="cb1b0-110">Enumerates through a list of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cb1b0-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="cb1b0-111">Remarks</span></span>  

 <span data-ttu-id="cb1b0-112">Cada estructura `CorDebugBlockingObject` representa un objeto que está bloqueando un subproceso.</span><span class="sxs-lookup"><span data-stu-id="cb1b0-112">Each `CorDebugBlockingObject` structure represents an object that is blocking a thread.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cb1b0-113">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="cb1b0-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb1b0-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cb1b0-114">Requirements</span></span>  

 <span data-ttu-id="cb1b0-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cb1b0-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb1b0-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cb1b0-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cb1b0-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cb1b0-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cb1b0-118">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb1b0-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb1b0-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="cb1b0-119">See also</span></span>

- [<span data-ttu-id="cb1b0-120">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="cb1b0-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="cb1b0-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="cb1b0-121">Debugging</span></span>](index.md)
