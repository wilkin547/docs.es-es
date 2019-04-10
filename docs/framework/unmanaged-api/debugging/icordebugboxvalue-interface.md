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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59221969"
---
# <a name="icordebugboxvalue-interface"></a><span data-ttu-id="13e15-102">Interfaz ICorDebugBoxValue</span><span class="sxs-lookup"><span data-stu-id="13e15-102">ICorDebugBoxValue Interface</span></span>

<span data-ttu-id="13e15-103">Una subclase del ICorDebugHeapValue"" que representa un objeto de clase de valor con conversión boxing.</span><span class="sxs-lookup"><span data-stu-id="13e15-103">A subclass of "ICorDebugHeapValue" that represents a boxed value class object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="13e15-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="13e15-104">Methods</span></span>  
  
|<span data-ttu-id="13e15-105">Método</span><span class="sxs-lookup"><span data-stu-id="13e15-105">Method</span></span>|<span data-ttu-id="13e15-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="13e15-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="13e15-107">GetObject (Método)</span><span class="sxs-lookup"><span data-stu-id="13e15-107">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugboxvalue-getobject-method.md)|<span data-ttu-id="13e15-108">Obtiene un puntero de interfaz a la instancia "ICorDebugObjectValue" conversión boxing.</span><span class="sxs-lookup"><span data-stu-id="13e15-108">Gets an interface pointer to the boxed "ICorDebugObjectValue" instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="13e15-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="13e15-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="13e15-110">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="13e15-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13e15-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="13e15-111">Requirements</span></span>  
 <span data-ttu-id="13e15-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="13e15-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13e15-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="13e15-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="13e15-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="13e15-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="13e15-115">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="13e15-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="13e15-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="13e15-116">See also</span></span>

- [<span data-ttu-id="13e15-117">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="13e15-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
