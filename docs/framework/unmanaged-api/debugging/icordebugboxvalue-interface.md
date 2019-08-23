---
title: Interfaz ICorDebugBoxValue
ms.date: 03/30/2017
api_name:
- ICorDebugBoxValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBoxValue
helpviewer_keywords:
- ICorDebugBoxValue interface [.NET Framework debugging]
ms.assetid: 3d3ae7e2-97d4-46de-a2c3-cb78f3490f9d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c21e5bb70815fa54d1b458894ca33becde204758
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69912920"
---
# <a name="icordebugboxvalue-interface"></a><span data-ttu-id="e0f77-102">Interfaz ICorDebugBoxValue</span><span class="sxs-lookup"><span data-stu-id="e0f77-102">ICorDebugBoxValue Interface</span></span>

<span data-ttu-id="e0f77-103">Subclase de "ICorDebugHeapValue" que representa un objeto de clase de valor con conversión boxing.</span><span class="sxs-lookup"><span data-stu-id="e0f77-103">A subclass of "ICorDebugHeapValue" that represents a boxed value class object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e0f77-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="e0f77-104">Methods</span></span>  
  
|<span data-ttu-id="e0f77-105">Método</span><span class="sxs-lookup"><span data-stu-id="e0f77-105">Method</span></span>|<span data-ttu-id="e0f77-106">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="e0f77-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e0f77-107">GetObject (método)</span><span class="sxs-lookup"><span data-stu-id="e0f77-107">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugboxvalue-getobject-method.md)|<span data-ttu-id="e0f77-108">Obtiene un puntero de interfaz a la instancia "ICorDebugObjectValue" con conversión boxing.</span><span class="sxs-lookup"><span data-stu-id="e0f77-108">Gets an interface pointer to the boxed "ICorDebugObjectValue" instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e0f77-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e0f77-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e0f77-110">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="e0f77-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0f77-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e0f77-111">Requirements</span></span>  
 <span data-ttu-id="e0f77-112">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0f77-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0f77-113">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="e0f77-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e0f77-114">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e0f77-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e0f77-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0f77-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0f77-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="e0f77-116">See also</span></span>

- [<span data-ttu-id="e0f77-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="e0f77-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
