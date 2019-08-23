---
title: Método ICorDebugMemoryBuffer
ms.date: 03/30/2017
ms.assetid: 85dc2d65-3657-4b93-9f23-9feaa95d37ff
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 77fa6b1a8c7a559b9d88c0173e389ec11a75ec8b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69914785"
---
# <a name="icordebugmemorybuffer-interface"></a><span data-ttu-id="94e48-102">Método ICorDebugMemoryBuffer</span><span class="sxs-lookup"><span data-stu-id="94e48-102">ICorDebugMemoryBuffer Interface</span></span>
<span data-ttu-id="94e48-103">Representa un búfer en memoria.</span><span class="sxs-lookup"><span data-stu-id="94e48-103">Represents an in-memory buffer.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="94e48-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="94e48-104">Methods</span></span>  
  
|<span data-ttu-id="94e48-105">Método</span><span class="sxs-lookup"><span data-stu-id="94e48-105">Method</span></span>|<span data-ttu-id="94e48-106">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="94e48-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="94e48-107">GetSize (método)</span><span class="sxs-lookup"><span data-stu-id="94e48-107">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-getsize-method.md)|<span data-ttu-id="94e48-108">Obtiene el tamaño del búfer de memoria en bytes.</span><span class="sxs-lookup"><span data-stu-id="94e48-108">Gets the size of the memory buffer in bytes.</span></span>|  
|[<span data-ttu-id="94e48-109">GetStartAddress (método)</span><span class="sxs-lookup"><span data-stu-id="94e48-109">GetStartAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-getstartaddress-method.md)|<span data-ttu-id="94e48-110">Obtiene la dirección de inicio del búfer de memoria.</span><span class="sxs-lookup"><span data-stu-id="94e48-110">Gets the starting address of the memory buffer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="94e48-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="94e48-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="94e48-112">Esta interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="94e48-112">This interface is available with .NET Native only.</span></span> <span data-ttu-id="94e48-113">Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="94e48-113">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94e48-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="94e48-114">Requirements</span></span>  
 <span data-ttu-id="94e48-115">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94e48-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94e48-116">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="94e48-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="94e48-117">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="94e48-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="94e48-118">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94e48-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94e48-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="94e48-119">See also</span></span>

- [<span data-ttu-id="94e48-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="94e48-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="94e48-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="94e48-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
