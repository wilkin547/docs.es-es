---
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
ms.openlocfilehash: ee3ea319360bba1a113c15daf8cf143ea512e5cd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733326"
---
# <a name="icordebugheapvalue-interface"></a><span data-ttu-id="ff5c2-102">Interfaz ICorDebugHeapValue</span><span class="sxs-lookup"><span data-stu-id="ff5c2-102">ICorDebugHeapValue Interface</span></span>

<span data-ttu-id="ff5c2-103">Subclase de "ICorDebugValue" que representa un objeto recopilado por el recolector de elementos no utilizados de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="ff5c2-103">A subclass of "ICorDebugValue" that represents an object that has been collected by the common language runtime (CLR) garbage collector.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ff5c2-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="ff5c2-104">Methods</span></span>  
  
|<span data-ttu-id="ff5c2-105">Método</span><span class="sxs-lookup"><span data-stu-id="ff5c2-105">Method</span></span>|<span data-ttu-id="ff5c2-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="ff5c2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ff5c2-107">Método CreateRelocBreakpoint</span><span class="sxs-lookup"><span data-stu-id="ff5c2-107">CreateRelocBreakpoint Method</span></span>](icordebugheapvalue-createrelocbreakpoint-method.md)|<span data-ttu-id="ff5c2-108">Sin implementar.</span><span class="sxs-lookup"><span data-stu-id="ff5c2-108">Not implemented.</span></span>|  
|[<span data-ttu-id="ff5c2-109">Método IsValid</span><span class="sxs-lookup"><span data-stu-id="ff5c2-109">IsValid Method</span></span>](icordebugheapvalue-isvalid-method.md)|<span data-ttu-id="ff5c2-110">Obtiene un valor que indica si el objeto representado por este objeto `ICorDebugHeapValue` es válido o si lo ha reclamado el recolector de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="ff5c2-110">Gets a value that indicates whether the object represented by this `ICorDebugHeapValue` is valid, or has been reclaimed by the garbage collector.</span></span> <span data-ttu-id="ff5c2-111">Este método está en desuso en la versión .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="ff5c2-111">This method has been deprecated in the .NET Framework version 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ff5c2-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ff5c2-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ff5c2-113">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="ff5c2-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff5c2-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ff5c2-114">Requirements</span></span>  

 <span data-ttu-id="ff5c2-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff5c2-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff5c2-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ff5c2-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ff5c2-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ff5c2-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ff5c2-118">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff5c2-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff5c2-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ff5c2-119">See also</span></span>

- [<span data-ttu-id="ff5c2-120">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="ff5c2-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
