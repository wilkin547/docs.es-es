---
title: ICorDebugMemoryBuffer (Interfaz)
ms.date: 03/30/2017
ms.assetid: 85dc2d65-3657-4b93-9f23-9feaa95d37ff
ms.openlocfilehash: fa1bbca1e771cbc2b3475891862875b97b9e7f90
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793136"
---
# <a name="icordebugmemorybuffer-interface"></a><span data-ttu-id="0e1c1-102">ICorDebugMemoryBuffer (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0e1c1-102">ICorDebugMemoryBuffer Interface</span></span>
<span data-ttu-id="0e1c1-103">Representa un búfer en memoria.</span><span class="sxs-lookup"><span data-stu-id="0e1c1-103">Represents an in-memory buffer.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0e1c1-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="0e1c1-104">Methods</span></span>  
  
|<span data-ttu-id="0e1c1-105">Método</span><span class="sxs-lookup"><span data-stu-id="0e1c1-105">Method</span></span>|<span data-ttu-id="0e1c1-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="0e1c1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0e1c1-107">GetSize (método)</span><span class="sxs-lookup"><span data-stu-id="0e1c1-107">GetSize Method</span></span>](icordebugmemorybuffer-getsize-method.md)|<span data-ttu-id="0e1c1-108">Obtiene el tamaño del búfer de memoria en bytes.</span><span class="sxs-lookup"><span data-stu-id="0e1c1-108">Gets the size of the memory buffer in bytes.</span></span>|  
|[<span data-ttu-id="0e1c1-109">GetStartAddress (método)</span><span class="sxs-lookup"><span data-stu-id="0e1c1-109">GetStartAddress Method</span></span>](icordebugmemorybuffer-getstartaddress-method.md)|<span data-ttu-id="0e1c1-110">Obtiene la dirección de inicio del búfer de memoria.</span><span class="sxs-lookup"><span data-stu-id="0e1c1-110">Gets the starting address of the memory buffer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0e1c1-111">Notas</span><span class="sxs-lookup"><span data-stu-id="0e1c1-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0e1c1-112">Esta interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="0e1c1-112">This interface is available with .NET Native only.</span></span> <span data-ttu-id="0e1c1-113">Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="0e1c1-113">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e1c1-114">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="0e1c1-114">Requirements</span></span>  
 <span data-ttu-id="0e1c1-115">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e1c1-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e1c1-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0e1c1-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0e1c1-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0e1c1-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0e1c1-118">**.NET Framework versiones:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e1c1-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e1c1-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="0e1c1-119">See also</span></span>

- [<span data-ttu-id="0e1c1-120">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="0e1c1-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="0e1c1-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="0e1c1-121">Debugging</span></span>](index.md)
