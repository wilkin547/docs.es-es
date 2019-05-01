---
title: Método ICorDebugMemoryBuffer
ms.date: 03/30/2017
ms.assetid: 85dc2d65-3657-4b93-9f23-9feaa95d37ff
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e12b50e964ec470b843ae35c960f20c5675fd572
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61955472"
---
# <a name="icordebugmemorybuffer-interface"></a><span data-ttu-id="70dc5-102">Método ICorDebugMemoryBuffer</span><span class="sxs-lookup"><span data-stu-id="70dc5-102">ICorDebugMemoryBuffer Interface</span></span>
<span data-ttu-id="70dc5-103">Representa un búfer en memoria.</span><span class="sxs-lookup"><span data-stu-id="70dc5-103">Represents an in-memory buffer.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="70dc5-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="70dc5-104">Methods</span></span>  
  
|<span data-ttu-id="70dc5-105">Método</span><span class="sxs-lookup"><span data-stu-id="70dc5-105">Method</span></span>|<span data-ttu-id="70dc5-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="70dc5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="70dc5-107">GetSize (método)</span><span class="sxs-lookup"><span data-stu-id="70dc5-107">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-getsize-method.md)|<span data-ttu-id="70dc5-108">Obtiene el tamaño del búfer de memoria en bytes.</span><span class="sxs-lookup"><span data-stu-id="70dc5-108">Gets the size of the memory buffer in bytes.</span></span>|  
|[<span data-ttu-id="70dc5-109">GetStartAddress (método)</span><span class="sxs-lookup"><span data-stu-id="70dc5-109">GetStartAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-getstartaddress-method.md)|<span data-ttu-id="70dc5-110">Obtiene la dirección de inicio del búfer de memoria.</span><span class="sxs-lookup"><span data-stu-id="70dc5-110">Gets the starting address of the memory buffer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="70dc5-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="70dc5-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="70dc5-112">Esta interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="70dc5-112">This interface is available with .NET Native only.</span></span> <span data-ttu-id="70dc5-113">Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="70dc5-113">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70dc5-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="70dc5-114">Requirements</span></span>  
 <span data-ttu-id="70dc5-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="70dc5-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70dc5-116">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="70dc5-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="70dc5-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="70dc5-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="70dc5-118">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70dc5-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70dc5-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="70dc5-119">See also</span></span>

- [<span data-ttu-id="70dc5-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="70dc5-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="70dc5-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="70dc5-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
