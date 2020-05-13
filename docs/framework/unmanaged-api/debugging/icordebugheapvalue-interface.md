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
ms.openlocfilehash: 36a485413490045ca49b99fca4fe5d43edc37114
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213015"
---
# <a name="icordebugheapvalue-interface"></a><span data-ttu-id="a668e-102">Interfaz ICorDebugHeapValue</span><span class="sxs-lookup"><span data-stu-id="a668e-102">ICorDebugHeapValue Interface</span></span>

<span data-ttu-id="a668e-103">Subclase de "ICorDebugValue" que representa un objeto recopilado por el recolector de elementos no utilizados de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="a668e-103">A subclass of "ICorDebugValue" that represents an object that has been collected by the common language runtime (CLR) garbage collector.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a668e-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="a668e-104">Methods</span></span>  
  
|<span data-ttu-id="a668e-105">Método</span><span class="sxs-lookup"><span data-stu-id="a668e-105">Method</span></span>|<span data-ttu-id="a668e-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="a668e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a668e-107">Método CreateRelocBreakpoint</span><span class="sxs-lookup"><span data-stu-id="a668e-107">CreateRelocBreakpoint Method</span></span>](icordebugheapvalue-createrelocbreakpoint-method.md)|<span data-ttu-id="a668e-108">No implementado.</span><span class="sxs-lookup"><span data-stu-id="a668e-108">Not implemented.</span></span>|  
|[<span data-ttu-id="a668e-109">Método IsValid</span><span class="sxs-lookup"><span data-stu-id="a668e-109">IsValid Method</span></span>](icordebugheapvalue-isvalid-method.md)|<span data-ttu-id="a668e-110">Obtiene un valor que indica si el objeto representado por este objeto `ICorDebugHeapValue` es válido o si lo ha reclamado el recolector de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="a668e-110">Gets a value that indicates whether the object represented by this `ICorDebugHeapValue` is valid, or has been reclaimed by the garbage collector.</span></span> <span data-ttu-id="a668e-111">Este método está en desuso en la versión .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="a668e-111">This method has been deprecated in the .NET Framework version 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a668e-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a668e-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a668e-113">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="a668e-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a668e-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a668e-114">Requirements</span></span>  
 <span data-ttu-id="a668e-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a668e-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a668e-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a668e-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a668e-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a668e-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a668e-118">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a668e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a668e-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a668e-119">See also</span></span>

- [<span data-ttu-id="a668e-120">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="a668e-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
