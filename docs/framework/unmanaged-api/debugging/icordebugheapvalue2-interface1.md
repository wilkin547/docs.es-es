---
title: Interfaz ICorDebugHeapValue2
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue2
helpviewer_keywords:
- ICorDebugHeapValue2 interface [.NET Framework debugging]
ms.assetid: 87360a52-90b1-4ada-80c0-589a556116d8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fa872453ed72a3095c135aa25e81284610ad2436
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69910218"
---
# <a name="icordebugheapvalue2-interface"></a><span data-ttu-id="42608-102">Interfaz ICorDebugHeapValue2</span><span class="sxs-lookup"><span data-stu-id="42608-102">ICorDebugHeapValue2 Interface</span></span>

<span data-ttu-id="42608-103">Extensión de ICorDebugHeapValue que proporciona compatibilidad con los identificadores de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="42608-103">An extension of ICorDebugHeapValue that provides support for common language runtime (CLR) handles.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="42608-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="42608-104">Methods</span></span>  
  
|<span data-ttu-id="42608-105">Método</span><span class="sxs-lookup"><span data-stu-id="42608-105">Method</span></span>|<span data-ttu-id="42608-106">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="42608-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="42608-107">CreateHandle (método)</span><span class="sxs-lookup"><span data-stu-id="42608-107">CreateHandle Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue2-createhandle-method.md)|<span data-ttu-id="42608-108">Crea un identificador del tipo especificado para este `ICorDebugHeapValue2` objeto.</span><span class="sxs-lookup"><span data-stu-id="42608-108">Creates a handle of the specified type for this `ICorDebugHeapValue2` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="42608-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="42608-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="42608-110">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="42608-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42608-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="42608-111">Requirements</span></span>  
 <span data-ttu-id="42608-112">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="42608-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42608-113">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="42608-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="42608-114">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="42608-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="42608-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42608-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42608-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="42608-116">See also</span></span>

- [<span data-ttu-id="42608-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="42608-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
