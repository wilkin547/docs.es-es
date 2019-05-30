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
ms.openlocfilehash: e4bf3605331e6900fd890e49bb3f71f4ca4409c7
ms.sourcegitcommit: 4735bb7741555bcb870d7b42964d3774f4897a6e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/30/2019
ms.locfileid: "66377594"
---
# <a name="icordebugvalue3-interface"></a><span data-ttu-id="5a225-102">ICorDebugValue3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5a225-102">ICorDebugValue3 Interface</span></span>
<span data-ttu-id="5a225-103">Extiende las interfaces "ICorDebugValue" y "ICorDebugValue2" para proporcionar compatibilidad para matrices que son superiores a 2 GB.</span><span class="sxs-lookup"><span data-stu-id="5a225-103">Extends the "ICorDebugValue" and "ICorDebugValue2" interfaces to provide support for arrays that are larger than 2 GB.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5a225-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="5a225-104">Methods</span></span>  
  
|<span data-ttu-id="5a225-105">Método</span><span class="sxs-lookup"><span data-stu-id="5a225-105">Method</span></span>|<span data-ttu-id="5a225-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="5a225-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5a225-107">GetSize64 (método)</span><span class="sxs-lookup"><span data-stu-id="5a225-107">GetSize64 Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md)|<span data-ttu-id="5a225-108">Obtiene el tamaño, en bytes, de este `ICorDebugValue3` objeto.</span><span class="sxs-lookup"><span data-stu-id="5a225-108">Gets the size, in bytes, of this `ICorDebugValue3` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5a225-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5a225-109">Remarks</span></span>  
 <span data-ttu-id="5a225-110">El [ICorDebugValue](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) método devuelve un tamaño de objeto que va de 0 a 2.147.483.647 bytes.</span><span class="sxs-lookup"><span data-stu-id="5a225-110">The [ICorDebugValue::GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) method returns an object size that ranges from 0 to 2,147,483,647 bytes.</span></span> <span data-ttu-id="5a225-111">En .NET Framework 4.5, el tamaño de matrices puede superar los 2 GB.</span><span class="sxs-lookup"><span data-stu-id="5a225-111">In the .NET Framework 4.5, the size of arrays can exceed 2 GB.</span></span> <span data-ttu-id="5a225-112">El `ICorDebugValue3` interfaz le permite determinar el tamaño de estas matrices.</span><span class="sxs-lookup"><span data-stu-id="5a225-112">The `ICorDebugValue3` interface enables you to determine the size of these arrays.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a225-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5a225-113">Requirements</span></span>  
 <span data-ttu-id="5a225-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a225-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a225-115">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5a225-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5a225-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5a225-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5a225-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a225-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a225-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="5a225-118">See also</span></span>

- [<span data-ttu-id="5a225-119">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="5a225-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="5a225-120">Depuración</span><span class="sxs-lookup"><span data-stu-id="5a225-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
