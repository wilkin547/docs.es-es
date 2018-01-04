---
title: ICorDebugMemoryBuffer (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 85dc2d65-3657-4b93-9f23-9feaa95d37ff
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 98703b07f6601307b5f26aa14b2faf67f8823be5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmemorybuffer-interface"></a><span data-ttu-id="8cd1c-102">ICorDebugMemoryBuffer (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8cd1c-102">ICorDebugMemoryBuffer Interface</span></span>
<span data-ttu-id="8cd1c-103">Representa un búfer en memoria.</span><span class="sxs-lookup"><span data-stu-id="8cd1c-103">Represents an in-memory buffer.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8cd1c-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="8cd1c-104">Methods</span></span>  
  
|<span data-ttu-id="8cd1c-105">Método</span><span class="sxs-lookup"><span data-stu-id="8cd1c-105">Method</span></span>|<span data-ttu-id="8cd1c-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="8cd1c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8cd1c-107">GetSize (método)</span><span class="sxs-lookup"><span data-stu-id="8cd1c-107">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-getsize-method.md)|<span data-ttu-id="8cd1c-108">Obtiene el tamaño del búfer de memoria en bytes.</span><span class="sxs-lookup"><span data-stu-id="8cd1c-108">Gets the size of the memory buffer in bytes.</span></span>|  
|[<span data-ttu-id="8cd1c-109">GetStartAddress (método)</span><span class="sxs-lookup"><span data-stu-id="8cd1c-109">GetStartAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-getstartaddress-method.md)|<span data-ttu-id="8cd1c-110">Obtiene la dirección de inicio del búfer de memoria.</span><span class="sxs-lookup"><span data-stu-id="8cd1c-110">Gets the starting address of the memory buffer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8cd1c-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8cd1c-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8cd1c-112">Esta interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="8cd1c-112">This interface is available with .NET Native only.</span></span> <span data-ttu-id="8cd1c-113">Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="8cd1c-113">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8cd1c-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8cd1c-114">Requirements</span></span>  
 <span data-ttu-id="8cd1c-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8cd1c-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8cd1c-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8cd1c-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8cd1c-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8cd1c-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8cd1c-118">**Versiones de .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8cd1c-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cd1c-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="8cd1c-119">See Also</span></span>  
 [<span data-ttu-id="8cd1c-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="8cd1c-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="8cd1c-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="8cd1c-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
