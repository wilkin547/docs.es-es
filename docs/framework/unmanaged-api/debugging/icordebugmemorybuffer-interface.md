---
title: Método ICorDebugMemoryBuffer
ms.date: 03/30/2017
ms.assetid: 85dc2d65-3657-4b93-9f23-9feaa95d37ff
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e12b50e964ec470b843ae35c960f20c5675fd572
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59072914"
---
# <a name="icordebugmemorybuffer-interface"></a><span data-ttu-id="eb44c-102">Método ICorDebugMemoryBuffer</span><span class="sxs-lookup"><span data-stu-id="eb44c-102">ICorDebugMemoryBuffer Interface</span></span>
<span data-ttu-id="eb44c-103">Representa un búfer en memoria.</span><span class="sxs-lookup"><span data-stu-id="eb44c-103">Represents an in-memory buffer.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="eb44c-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="eb44c-104">Methods</span></span>  
  
|<span data-ttu-id="eb44c-105">Método</span><span class="sxs-lookup"><span data-stu-id="eb44c-105">Method</span></span>|<span data-ttu-id="eb44c-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="eb44c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="eb44c-107">Método GetSize</span><span class="sxs-lookup"><span data-stu-id="eb44c-107">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-getsize-method.md)|<span data-ttu-id="eb44c-108">Obtiene el tamaño del búfer de memoria en bytes.</span><span class="sxs-lookup"><span data-stu-id="eb44c-108">Gets the size of the memory buffer in bytes.</span></span>|  
|[<span data-ttu-id="eb44c-109">Método GetStartAddress</span><span class="sxs-lookup"><span data-stu-id="eb44c-109">GetStartAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-getstartaddress-method.md)|<span data-ttu-id="eb44c-110">Obtiene la dirección de inicio del búfer de memoria.</span><span class="sxs-lookup"><span data-stu-id="eb44c-110">Gets the starting address of the memory buffer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eb44c-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="eb44c-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="eb44c-112">Esta interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="eb44c-112">This interface is available with .NET Native only.</span></span> <span data-ttu-id="eb44c-113">Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="eb44c-113">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb44c-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="eb44c-114">Requirements</span></span>  
 <span data-ttu-id="eb44c-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eb44c-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb44c-116">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eb44c-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eb44c-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eb44c-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="eb44c-118">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="eb44c-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="eb44c-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="eb44c-119">See also</span></span>

- [<span data-ttu-id="eb44c-120">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="eb44c-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="eb44c-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="eb44c-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
