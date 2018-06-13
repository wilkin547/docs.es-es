---
title: ICorDebugMemoryBuffer (Interfaz)
ms.date: 03/30/2017
ms.assetid: 85dc2d65-3657-4b93-9f23-9feaa95d37ff
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4a1bc8e1206b8a82127645362cfe0a124074271c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33414409"
---
# <a name="icordebugmemorybuffer-interface"></a><span data-ttu-id="90b1f-102">ICorDebugMemoryBuffer (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="90b1f-102">ICorDebugMemoryBuffer Interface</span></span>
<span data-ttu-id="90b1f-103">Representa un búfer en memoria.</span><span class="sxs-lookup"><span data-stu-id="90b1f-103">Represents an in-memory buffer.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="90b1f-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="90b1f-104">Methods</span></span>  
  
|<span data-ttu-id="90b1f-105">Método</span><span class="sxs-lookup"><span data-stu-id="90b1f-105">Method</span></span>|<span data-ttu-id="90b1f-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="90b1f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="90b1f-107">GetSize (método)</span><span class="sxs-lookup"><span data-stu-id="90b1f-107">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-getsize-method.md)|<span data-ttu-id="90b1f-108">Obtiene el tamaño del búfer de memoria en bytes.</span><span class="sxs-lookup"><span data-stu-id="90b1f-108">Gets the size of the memory buffer in bytes.</span></span>|  
|[<span data-ttu-id="90b1f-109">GetStartAddress (método)</span><span class="sxs-lookup"><span data-stu-id="90b1f-109">GetStartAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-getstartaddress-method.md)|<span data-ttu-id="90b1f-110">Obtiene la dirección de inicio del búfer de memoria.</span><span class="sxs-lookup"><span data-stu-id="90b1f-110">Gets the starting address of the memory buffer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="90b1f-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="90b1f-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="90b1f-112">Esta interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="90b1f-112">This interface is available with .NET Native only.</span></span> <span data-ttu-id="90b1f-113">Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="90b1f-113">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90b1f-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="90b1f-114">Requirements</span></span>  
 <span data-ttu-id="90b1f-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="90b1f-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90b1f-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="90b1f-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="90b1f-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="90b1f-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="90b1f-118">**Versiones de .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90b1f-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90b1f-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="90b1f-119">See Also</span></span>  
 [<span data-ttu-id="90b1f-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="90b1f-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="90b1f-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="90b1f-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
