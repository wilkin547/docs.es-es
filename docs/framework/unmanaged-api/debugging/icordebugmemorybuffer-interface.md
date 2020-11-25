---
title: Método ICorDebugMemoryBuffer
ms.date: 03/30/2017
ms.assetid: 85dc2d65-3657-4b93-9f23-9feaa95d37ff
ms.openlocfilehash: 2765852309401d2aa30f91b506ba55156cd8a3e2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710753"
---
# <a name="icordebugmemorybuffer-interface"></a><span data-ttu-id="10146-102">Método ICorDebugMemoryBuffer</span><span class="sxs-lookup"><span data-stu-id="10146-102">ICorDebugMemoryBuffer Interface</span></span>

<span data-ttu-id="10146-103">Representa un búfer en memoria.</span><span class="sxs-lookup"><span data-stu-id="10146-103">Represents an in-memory buffer.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="10146-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="10146-104">Methods</span></span>  
  
|<span data-ttu-id="10146-105">Método</span><span class="sxs-lookup"><span data-stu-id="10146-105">Method</span></span>|<span data-ttu-id="10146-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="10146-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="10146-107">Método GetSize</span><span class="sxs-lookup"><span data-stu-id="10146-107">GetSize Method</span></span>](icordebugmemorybuffer-getsize-method.md)|<span data-ttu-id="10146-108">Obtiene el tamaño del búfer de memoria en bytes.</span><span class="sxs-lookup"><span data-stu-id="10146-108">Gets the size of the memory buffer in bytes.</span></span>|  
|[<span data-ttu-id="10146-109">Método GetStartAddress</span><span class="sxs-lookup"><span data-stu-id="10146-109">GetStartAddress Method</span></span>](icordebugmemorybuffer-getstartaddress-method.md)|<span data-ttu-id="10146-110">Obtiene la dirección de inicio del búfer de memoria.</span><span class="sxs-lookup"><span data-stu-id="10146-110">Gets the starting address of the memory buffer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="10146-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="10146-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="10146-112">Esta interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="10146-112">This interface is available with .NET Native only.</span></span> <span data-ttu-id="10146-113">Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="10146-113">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10146-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="10146-114">Requirements</span></span>  

 <span data-ttu-id="10146-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10146-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10146-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="10146-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="10146-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="10146-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="10146-118">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10146-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10146-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="10146-119">See also</span></span>

- [<span data-ttu-id="10146-120">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="10146-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="10146-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="10146-121">Debugging</span></span>](index.md)
