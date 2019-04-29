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
ms.openlocfilehash: 1a9a647a9c77a3c1f82ae3691e2a5e5b2f544cad
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645414"
---
# <a name="icordebugboxvalue-interface"></a><span data-ttu-id="9efb4-102">Interfaz ICorDebugBoxValue</span><span class="sxs-lookup"><span data-stu-id="9efb4-102">ICorDebugBoxValue Interface</span></span>

<span data-ttu-id="9efb4-103">Una subclase del ICorDebugHeapValue"" que representa un objeto de clase de valor con conversión boxing.</span><span class="sxs-lookup"><span data-stu-id="9efb4-103">A subclass of "ICorDebugHeapValue" that represents a boxed value class object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9efb4-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="9efb4-104">Methods</span></span>  
  
|<span data-ttu-id="9efb4-105">Método</span><span class="sxs-lookup"><span data-stu-id="9efb4-105">Method</span></span>|<span data-ttu-id="9efb4-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="9efb4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9efb4-107">GetObject (método)</span><span class="sxs-lookup"><span data-stu-id="9efb4-107">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugboxvalue-getobject-method.md)|<span data-ttu-id="9efb4-108">Obtiene un puntero de interfaz a la instancia "ICorDebugObjectValue" conversión boxing.</span><span class="sxs-lookup"><span data-stu-id="9efb4-108">Gets an interface pointer to the boxed "ICorDebugObjectValue" instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9efb4-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9efb4-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9efb4-110">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="9efb4-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9efb4-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9efb4-111">Requirements</span></span>  
 <span data-ttu-id="9efb4-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9efb4-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9efb4-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9efb4-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9efb4-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9efb4-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9efb4-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9efb4-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9efb4-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="9efb4-116">See also</span></span>

- [<span data-ttu-id="9efb4-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="9efb4-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
