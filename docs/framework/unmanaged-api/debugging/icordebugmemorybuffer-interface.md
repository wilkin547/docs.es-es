---
title: Método ICorDebugMemoryBuffer
ms.date: 03/30/2017
ms.assetid: 85dc2d65-3657-4b93-9f23-9feaa95d37ff
ms.openlocfilehash: 9e43f9a2297eb56755c7a6bba73e994441cbfeaa
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127973"
---
# <a name="icordebugmemorybuffer-interface"></a><span data-ttu-id="60801-102">Método ICorDebugMemoryBuffer</span><span class="sxs-lookup"><span data-stu-id="60801-102">ICorDebugMemoryBuffer Interface</span></span>
<span data-ttu-id="60801-103">Representa un búfer en memoria.</span><span class="sxs-lookup"><span data-stu-id="60801-103">Represents an in-memory buffer.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="60801-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="60801-104">Methods</span></span>  
  
|<span data-ttu-id="60801-105">Método</span><span class="sxs-lookup"><span data-stu-id="60801-105">Method</span></span>|<span data-ttu-id="60801-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="60801-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="60801-107">GetSize (método)</span><span class="sxs-lookup"><span data-stu-id="60801-107">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-getsize-method.md)|<span data-ttu-id="60801-108">Obtiene el tamaño del búfer de memoria en bytes.</span><span class="sxs-lookup"><span data-stu-id="60801-108">Gets the size of the memory buffer in bytes.</span></span>|  
|[<span data-ttu-id="60801-109">GetStartAddress (método)</span><span class="sxs-lookup"><span data-stu-id="60801-109">GetStartAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-getstartaddress-method.md)|<span data-ttu-id="60801-110">Obtiene la dirección de inicio del búfer de memoria.</span><span class="sxs-lookup"><span data-stu-id="60801-110">Gets the starting address of the memory buffer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="60801-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="60801-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="60801-112">Esta interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="60801-112">This interface is available with .NET Native only.</span></span> <span data-ttu-id="60801-113">Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="60801-113">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60801-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="60801-114">Requirements</span></span>  
 <span data-ttu-id="60801-115">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="60801-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60801-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="60801-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="60801-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="60801-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="60801-118">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60801-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60801-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="60801-119">See also</span></span>

- [<span data-ttu-id="60801-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="60801-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="60801-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="60801-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
