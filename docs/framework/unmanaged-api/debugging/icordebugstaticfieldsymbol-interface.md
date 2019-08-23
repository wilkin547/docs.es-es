---
title: Interfaz ICorDebugStaticFieldSymbol
ms.date: 03/30/2017
ms.assetid: c0b93609-631e-4b15-878a-189ede922631
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7f4e245e96ac9d47db10072e50a5b3c516d5dd27
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962677"
---
# <a name="icordebugstaticfieldsymbol-interface"></a><span data-ttu-id="5bdc6-102">Interfaz ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="5bdc6-102">ICorDebugStaticFieldSymbol Interface</span></span>
<span data-ttu-id="5bdc6-103">Representa la información de símbolos de depuración para un campo estático.</span><span class="sxs-lookup"><span data-stu-id="5bdc6-103">Represents the debug symbol information for a static field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5bdc6-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="5bdc6-104">Methods</span></span>  
  
|<span data-ttu-id="5bdc6-105">Método</span><span class="sxs-lookup"><span data-stu-id="5bdc6-105">Method</span></span>|<span data-ttu-id="5bdc6-106">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="5bdc6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5bdc6-107">GetAddress (método)</span><span class="sxs-lookup"><span data-stu-id="5bdc6-107">GetAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-getaddress-method.md)|<span data-ttu-id="5bdc6-108">Obtiene la dirección del campo estático.</span><span class="sxs-lookup"><span data-stu-id="5bdc6-108">Gets the address of the static field.</span></span>|  
|[<span data-ttu-id="5bdc6-109">GetName (método)</span><span class="sxs-lookup"><span data-stu-id="5bdc6-109">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-getname-method.md)|<span data-ttu-id="5bdc6-110">Obtiene el nombre del campo estático.</span><span class="sxs-lookup"><span data-stu-id="5bdc6-110">Gets the name of the static field.</span></span>|  
|[<span data-ttu-id="5bdc6-111">GetSize (método)</span><span class="sxs-lookup"><span data-stu-id="5bdc6-111">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-getsize-method.md)|<span data-ttu-id="5bdc6-112">Obtiene el tamaño del campo estático, en bytes.</span><span class="sxs-lookup"><span data-stu-id="5bdc6-112">Gets the size in bytes of the static field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5bdc6-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5bdc6-113">Remarks</span></span>  
 <span data-ttu-id="5bdc6-114">La interfaz `ICorDebugStaticFieldSymbol` se utiliza para recuperar la información de símbolos de depuración para un campo estático.</span><span class="sxs-lookup"><span data-stu-id="5bdc6-114">The `ICorDebugStaticFieldSymbol` interface is used to retrieve the debug symbol information for a static field.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5bdc6-115">Esta interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="5bdc6-115">This interface is available with .NET Native only.</span></span> <span data-ttu-id="5bdc6-116">Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="5bdc6-116">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5bdc6-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5bdc6-117">Requirements</span></span>  
 <span data-ttu-id="5bdc6-118">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5bdc6-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5bdc6-119">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="5bdc6-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5bdc6-120">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5bdc6-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5bdc6-121">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5bdc6-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bdc6-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="5bdc6-122">See also</span></span>

- [<span data-ttu-id="5bdc6-123">ICorDebugInstanceFieldSymbol (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5bdc6-123">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="5bdc6-124">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="5bdc6-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="5bdc6-125">Depuración</span><span class="sxs-lookup"><span data-stu-id="5bdc6-125">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
