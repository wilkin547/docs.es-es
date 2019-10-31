---
title: ICorDebugBoxValue (Interfaz)
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
ms.openlocfilehash: a40e12655106cca01add065c2f95384b0eb1a286
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122806"
---
# <a name="icordebugboxvalue-interface"></a><span data-ttu-id="e8618-102">ICorDebugBoxValue (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e8618-102">ICorDebugBoxValue Interface</span></span>

<span data-ttu-id="e8618-103">Subclase de "ICorDebugHeapValue" que representa un objeto de clase de valor con conversión boxing.</span><span class="sxs-lookup"><span data-stu-id="e8618-103">A subclass of "ICorDebugHeapValue" that represents a boxed value class object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e8618-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="e8618-104">Methods</span></span>  
  
|<span data-ttu-id="e8618-105">Método</span><span class="sxs-lookup"><span data-stu-id="e8618-105">Method</span></span>|<span data-ttu-id="e8618-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="e8618-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e8618-107">GetObject (método)</span><span class="sxs-lookup"><span data-stu-id="e8618-107">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugboxvalue-getobject-method.md)|<span data-ttu-id="e8618-108">Obtiene un puntero de interfaz a la instancia "ICorDebugObjectValue" con conversión boxing.</span><span class="sxs-lookup"><span data-stu-id="e8618-108">Gets an interface pointer to the boxed "ICorDebugObjectValue" instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e8618-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e8618-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e8618-110">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="e8618-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8618-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e8618-111">Requirements</span></span>  
 <span data-ttu-id="e8618-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8618-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8618-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e8618-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e8618-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e8618-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e8618-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8618-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8618-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="e8618-116">See also</span></span>

- [<span data-ttu-id="e8618-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="e8618-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
