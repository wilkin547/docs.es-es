---
title: ICorDebugValue3 (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugValue3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue3
helpviewer_keywords:
- ICorDebugValue3 interface [.NET Framework debugging]
ms.assetid: 7d5385d3-f4a5-47c4-8478-a3513b5e9406
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 300d2263c076c9028340863e2f7a3fa27a36ef9d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59221982"
---
# <a name="icordebugvalue3-interface"></a><span data-ttu-id="34e93-102">ICorDebugValue3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="34e93-102">ICorDebugValue3 Interface</span></span>
<span data-ttu-id="34e93-103">Extiende las interfaces "ICorDebugValue" y "ICorDebugValue2" para proporcionar compatibilidad para matrices que son superiores a 2 GB.</span><span class="sxs-lookup"><span data-stu-id="34e93-103">Extends the "ICorDebugValue" and "ICorDebugValue2" interfaces to provide support for arrays that are larger than 2 GB.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="34e93-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="34e93-104">Methods</span></span>  
  
|<span data-ttu-id="34e93-105">Método</span><span class="sxs-lookup"><span data-stu-id="34e93-105">Method</span></span>|<span data-ttu-id="34e93-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="34e93-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="34e93-107">Método GetSize64</span><span class="sxs-lookup"><span data-stu-id="34e93-107">GetSize64 Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md)|<span data-ttu-id="34e93-108">Obtiene el tamaño, en bytes, de este `ICorDebugValue3` objeto.</span><span class="sxs-lookup"><span data-stu-id="34e93-108">Gets the size, in bytes, of this `ICorDebugValue3` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="34e93-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="34e93-109">Remarks</span></span>  
 <span data-ttu-id="34e93-110">El [ICorDebugValue](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) método devuelve un tamaño de objeto que va de 0 a 2.147.483.647 bytes.</span><span class="sxs-lookup"><span data-stu-id="34e93-110">The [ICorDebugValue::GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) method returns an object size that ranges from 0 to 2,147,483,647 bytes.</span></span> <span data-ttu-id="34e93-111">En el [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], el tamaño de matrices puede superar los 2 GB.</span><span class="sxs-lookup"><span data-stu-id="34e93-111">In the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], the size of arrays can exceed 2 GB.</span></span> <span data-ttu-id="34e93-112">El `ICorDebugValue3` interfaz le permite determinar el tamaño de estas matrices.</span><span class="sxs-lookup"><span data-stu-id="34e93-112">The `ICorDebugValue3` interface enables you to determine the size of these arrays.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34e93-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="34e93-113">Requirements</span></span>  
 <span data-ttu-id="34e93-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="34e93-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34e93-115">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="34e93-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="34e93-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="34e93-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="34e93-117">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="34e93-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="34e93-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="34e93-118">See also</span></span>

- [<span data-ttu-id="34e93-119">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="34e93-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="34e93-120">Depuración</span><span class="sxs-lookup"><span data-stu-id="34e93-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
