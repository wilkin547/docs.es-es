---
title: ICorDebugHeapValue Interfaz1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugHeapValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugHeapValue
helpviewer_keywords: ICorDebugHeapValue interface [.NET Framework debugging]
ms.assetid: 1bca66db-0359-4ae8-846e-e35f7e547e8b
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7868fc84ba3003909992334d1a66e1ed243eca18
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugheapvalue-interface1"></a><span data-ttu-id="c5229-102">ICorDebugHeapValue Interfaz1</span><span class="sxs-lookup"><span data-stu-id="c5229-102">ICorDebugHeapValue Interface1</span></span>
<span data-ttu-id="c5229-103">Una subclase de "ICorDebugValue" que representa un objeto que ha sido recopilado por el recolector de elementos no utilizados de common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="c5229-103">A subclass of "ICorDebugValue" that represents an object that has been collected by the common language runtime (CLR) garbage collector.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c5229-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="c5229-104">Methods</span></span>  
  
|<span data-ttu-id="c5229-105">Método</span><span class="sxs-lookup"><span data-stu-id="c5229-105">Method</span></span>|<span data-ttu-id="c5229-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="c5229-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c5229-107">CreateRelocBreakpoint (método)</span><span class="sxs-lookup"><span data-stu-id="c5229-107">CreateRelocBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-createrelocbreakpoint-method.md)|<span data-ttu-id="c5229-108">Sin implementar.</span><span class="sxs-lookup"><span data-stu-id="c5229-108">Not implemented.</span></span>|  
|[<span data-ttu-id="c5229-109">IsValid (método)</span><span class="sxs-lookup"><span data-stu-id="c5229-109">IsValid Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-isvalid-method.md)|<span data-ttu-id="c5229-110">Obtiene un valor que indica si el objeto representado por este `ICorDebugHeapValue` es válido o se ha recuperado por el recolector de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="c5229-110">Gets a value that indicates whether the object represented by this `ICorDebugHeapValue` is valid, or has been reclaimed by the garbage collector.</span></span> <span data-ttu-id="c5229-111">Este método está en desuso en la versión 2.0 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c5229-111">This method has been deprecated in the .NET Framework version 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c5229-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c5229-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c5229-113">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="c5229-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5229-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c5229-114">Requirements</span></span>  
 <span data-ttu-id="c5229-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c5229-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5229-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c5229-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c5229-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c5229-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c5229-118">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5229-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5229-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="c5229-119">See Also</span></span>  
    
    
    
 [<span data-ttu-id="c5229-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="c5229-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
