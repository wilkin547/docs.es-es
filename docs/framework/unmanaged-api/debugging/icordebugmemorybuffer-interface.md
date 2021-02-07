---
description: 'Más información acerca de: interfaz ICorDebugMemoryBuffer'
title: Método ICorDebugMemoryBuffer
ms.date: 03/30/2017
ms.assetid: 85dc2d65-3657-4b93-9f23-9feaa95d37ff
ms.openlocfilehash: 94eeb0f31c0e1c053fabbd556768fa65dda2d328
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754022"
---
# <a name="icordebugmemorybuffer-interface"></a><span data-ttu-id="6a15f-103">Método ICorDebugMemoryBuffer</span><span class="sxs-lookup"><span data-stu-id="6a15f-103">ICorDebugMemoryBuffer Interface</span></span>

<span data-ttu-id="6a15f-104">Representa un búfer en memoria.</span><span class="sxs-lookup"><span data-stu-id="6a15f-104">Represents an in-memory buffer.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6a15f-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="6a15f-105">Methods</span></span>  
  
|<span data-ttu-id="6a15f-106">Método</span><span class="sxs-lookup"><span data-stu-id="6a15f-106">Method</span></span>|<span data-ttu-id="6a15f-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="6a15f-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6a15f-108">Método GetSize</span><span class="sxs-lookup"><span data-stu-id="6a15f-108">GetSize Method</span></span>](icordebugmemorybuffer-getsize-method.md)|<span data-ttu-id="6a15f-109">Obtiene el tamaño del búfer de memoria en bytes.</span><span class="sxs-lookup"><span data-stu-id="6a15f-109">Gets the size of the memory buffer in bytes.</span></span>|  
|[<span data-ttu-id="6a15f-110">Método GetStartAddress</span><span class="sxs-lookup"><span data-stu-id="6a15f-110">GetStartAddress Method</span></span>](icordebugmemorybuffer-getstartaddress-method.md)|<span data-ttu-id="6a15f-111">Obtiene la dirección de inicio del búfer de memoria.</span><span class="sxs-lookup"><span data-stu-id="6a15f-111">Gets the starting address of the memory buffer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6a15f-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6a15f-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6a15f-113">Esta interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="6a15f-113">This interface is available with .NET Native only.</span></span> <span data-ttu-id="6a15f-114">Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="6a15f-114">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a15f-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6a15f-115">Requirements</span></span>  

 <span data-ttu-id="6a15f-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6a15f-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a15f-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6a15f-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6a15f-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6a15f-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6a15f-119">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a15f-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a15f-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="6a15f-120">See also</span></span>

- [<span data-ttu-id="6a15f-121">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="6a15f-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="6a15f-122">Depuración</span><span class="sxs-lookup"><span data-stu-id="6a15f-122">Debugging</span></span>](index.md)
