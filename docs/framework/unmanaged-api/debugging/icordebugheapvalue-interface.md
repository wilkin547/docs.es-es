---
description: 'Más información sobre: interfaz ICorDebugHeapValue'
title: Interfaz ICorDebugHeapValue
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue
helpviewer_keywords:
- ICorDebugHeapValue interface [.NET Framework debugging]
ms.assetid: 1bca66db-0359-4ae8-846e-e35f7e547e8b
topic_type:
- apiref
ms.openlocfilehash: 7c65cbce530f0d1f00d8610031fb604a0118ee29
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803690"
---
# <a name="icordebugheapvalue-interface"></a><span data-ttu-id="2a9c8-103">Interfaz ICorDebugHeapValue</span><span class="sxs-lookup"><span data-stu-id="2a9c8-103">ICorDebugHeapValue Interface</span></span>

<span data-ttu-id="2a9c8-104">Subclase de "ICorDebugValue" que representa un objeto recopilado por el recolector de elementos no utilizados de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="2a9c8-104">A subclass of "ICorDebugValue" that represents an object that has been collected by the common language runtime (CLR) garbage collector.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2a9c8-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="2a9c8-105">Methods</span></span>  
  
|<span data-ttu-id="2a9c8-106">Método</span><span class="sxs-lookup"><span data-stu-id="2a9c8-106">Method</span></span>|<span data-ttu-id="2a9c8-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="2a9c8-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2a9c8-108">Método CreateRelocBreakpoint</span><span class="sxs-lookup"><span data-stu-id="2a9c8-108">CreateRelocBreakpoint Method</span></span>](icordebugheapvalue-createrelocbreakpoint-method.md)|<span data-ttu-id="2a9c8-109">Sin implementar.</span><span class="sxs-lookup"><span data-stu-id="2a9c8-109">Not implemented.</span></span>|  
|[<span data-ttu-id="2a9c8-110">Método IsValid</span><span class="sxs-lookup"><span data-stu-id="2a9c8-110">IsValid Method</span></span>](icordebugheapvalue-isvalid-method.md)|<span data-ttu-id="2a9c8-111">Obtiene un valor que indica si el objeto representado por este objeto `ICorDebugHeapValue` es válido o si lo ha reclamado el recolector de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="2a9c8-111">Gets a value that indicates whether the object represented by this `ICorDebugHeapValue` is valid, or has been reclaimed by the garbage collector.</span></span> <span data-ttu-id="2a9c8-112">Este método está en desuso en la versión .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="2a9c8-112">This method has been deprecated in the .NET Framework version 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2a9c8-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2a9c8-113">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2a9c8-114">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="2a9c8-114">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a9c8-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2a9c8-115">Requirements</span></span>  

 <span data-ttu-id="2a9c8-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a9c8-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a9c8-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2a9c8-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2a9c8-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2a9c8-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2a9c8-119">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a9c8-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a9c8-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="2a9c8-120">See also</span></span>

- [<span data-ttu-id="2a9c8-121">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="2a9c8-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
