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
ms.openlocfilehash: fa31b8a6cc96935319e9bef3e561790b65e33a87
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777592"
---
# <a name="icordebugheapvalue-interface"></a><span data-ttu-id="2e6ce-102">Interfaz ICorDebugHeapValue</span><span class="sxs-lookup"><span data-stu-id="2e6ce-102">ICorDebugHeapValue Interface</span></span>

<span data-ttu-id="2e6ce-103">Subclase de "ICorDebugValue" que representa un objeto recopilado por el recolector de elementos no utilizados de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="2e6ce-103">A subclass of "ICorDebugValue" that represents an object that has been collected by the common language runtime (CLR) garbage collector.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2e6ce-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="2e6ce-104">Methods</span></span>  
  
|<span data-ttu-id="2e6ce-105">Método</span><span class="sxs-lookup"><span data-stu-id="2e6ce-105">Method</span></span>|<span data-ttu-id="2e6ce-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="2e6ce-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2e6ce-107">CreateRelocBreakpoint (método)</span><span class="sxs-lookup"><span data-stu-id="2e6ce-107">CreateRelocBreakpoint Method</span></span>](icordebugheapvalue-createrelocbreakpoint-method.md)|<span data-ttu-id="2e6ce-108">Sin implementar.</span><span class="sxs-lookup"><span data-stu-id="2e6ce-108">Not implemented.</span></span>|  
|[<span data-ttu-id="2e6ce-109">IsValid (método)</span><span class="sxs-lookup"><span data-stu-id="2e6ce-109">IsValid Method</span></span>](icordebugheapvalue-isvalid-method.md)|<span data-ttu-id="2e6ce-110">Obtiene un valor que indica si el objeto representado por este `ICorDebugHeapValue` es válido o si lo ha reclamado el recolector de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="2e6ce-110">Gets a value that indicates whether the object represented by this `ICorDebugHeapValue` is valid, or has been reclaimed by the garbage collector.</span></span> <span data-ttu-id="2e6ce-111">Este método está en desuso en la versión .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="2e6ce-111">This method has been deprecated in the .NET Framework version 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2e6ce-112">Notas</span><span class="sxs-lookup"><span data-stu-id="2e6ce-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2e6ce-113">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="2e6ce-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e6ce-114">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="2e6ce-114">Requirements</span></span>  
 <span data-ttu-id="2e6ce-115">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2e6ce-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e6ce-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2e6ce-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2e6ce-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2e6ce-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2e6ce-118">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e6ce-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e6ce-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="2e6ce-119">See also</span></span>

- [<span data-ttu-id="2e6ce-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="2e6ce-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
