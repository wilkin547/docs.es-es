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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d5fcd8c17c4006714fa9d11aece5cccc57c97087
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59075501"
---
# <a name="icordebugheapvalue-interface"></a><span data-ttu-id="ee959-102">Interfaz ICorDebugHeapValue</span><span class="sxs-lookup"><span data-stu-id="ee959-102">ICorDebugHeapValue Interface</span></span>

<span data-ttu-id="ee959-103">Una subclase de "ICorDebugValue" que representa un objeto que se han recopilado por el recolector de elementos no utilizados de common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="ee959-103">A subclass of "ICorDebugValue" that represents an object that has been collected by the common language runtime (CLR) garbage collector.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ee959-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="ee959-104">Methods</span></span>  
  
|<span data-ttu-id="ee959-105">Método</span><span class="sxs-lookup"><span data-stu-id="ee959-105">Method</span></span>|<span data-ttu-id="ee959-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="ee959-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ee959-107">Método CreateRelocBreakpoint</span><span class="sxs-lookup"><span data-stu-id="ee959-107">CreateRelocBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-createrelocbreakpoint-method.md)|<span data-ttu-id="ee959-108">Sin implementar.</span><span class="sxs-lookup"><span data-stu-id="ee959-108">Not implemented.</span></span>|  
|[<span data-ttu-id="ee959-109">Método IsValid</span><span class="sxs-lookup"><span data-stu-id="ee959-109">IsValid Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-isvalid-method.md)|<span data-ttu-id="ee959-110">Obtiene un valor que indica si el objeto representado por este `ICorDebugHeapValue` es válido o ha sido reclamado por el recolector de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="ee959-110">Gets a value that indicates whether the object represented by this `ICorDebugHeapValue` is valid, or has been reclaimed by the garbage collector.</span></span> <span data-ttu-id="ee959-111">Este método está desusado en .NET Framework versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="ee959-111">This method has been deprecated in the .NET Framework version 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ee959-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ee959-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ee959-113">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="ee959-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee959-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ee959-114">Requirements</span></span>  
 <span data-ttu-id="ee959-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ee959-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee959-116">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ee959-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ee959-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ee959-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="ee959-118">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="ee959-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ee959-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="ee959-119">See also</span></span>

- [<span data-ttu-id="ee959-120">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="ee959-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
