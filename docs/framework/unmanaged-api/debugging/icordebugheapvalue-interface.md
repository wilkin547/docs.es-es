---
title: ICorDebugHeapValue Interfaz1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d2ab132b73369526204f8fd811e1567b07b4a9b0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugheapvalue-interface1"></a><span data-ttu-id="47561-102">ICorDebugHeapValue Interfaz1</span><span class="sxs-lookup"><span data-stu-id="47561-102">ICorDebugHeapValue Interface1</span></span>
<span data-ttu-id="47561-103">Una subclase de "ICorDebugValue" que representa un objeto que ha sido recopilado por el recolector de elementos no utilizados de common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="47561-103">A subclass of "ICorDebugValue" that represents an object that has been collected by the common language runtime (CLR) garbage collector.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="47561-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="47561-104">Methods</span></span>  
  
|<span data-ttu-id="47561-105">Método</span><span class="sxs-lookup"><span data-stu-id="47561-105">Method</span></span>|<span data-ttu-id="47561-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="47561-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="47561-107">CreateRelocBreakpoint (método)</span><span class="sxs-lookup"><span data-stu-id="47561-107">CreateRelocBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-createrelocbreakpoint-method.md)|<span data-ttu-id="47561-108">Sin implementar.</span><span class="sxs-lookup"><span data-stu-id="47561-108">Not implemented.</span></span>|  
|[<span data-ttu-id="47561-109">IsValid (método)</span><span class="sxs-lookup"><span data-stu-id="47561-109">IsValid Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-isvalid-method.md)|<span data-ttu-id="47561-110">Obtiene un valor que indica si el objeto representado por este `ICorDebugHeapValue` es válido o se ha recuperado por el recolector de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="47561-110">Gets a value that indicates whether the object represented by this `ICorDebugHeapValue` is valid, or has been reclaimed by the garbage collector.</span></span> <span data-ttu-id="47561-111">Este método está en desuso en la versión 2.0 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="47561-111">This method has been deprecated in the .NET Framework version 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="47561-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="47561-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="47561-113">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="47561-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47561-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="47561-114">Requirements</span></span>  
 <span data-ttu-id="47561-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="47561-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47561-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="47561-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="47561-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="47561-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="47561-118">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47561-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47561-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="47561-119">See Also</span></span>  
    
    
    
 [<span data-ttu-id="47561-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="47561-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
