---
title: Interfaz ICorDebugInstanceFieldSymbol
ms.date: 03/30/2017
ms.assetid: a4a8f259-b83a-4425-ae8b-72b067dbc0d9
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0e5f63df9354df6a4d142c2f6ae12f9a0d5600fb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69910137"
---
# <a name="icordebuginstancefieldsymbol-interface"></a><span data-ttu-id="7d844-102">Interfaz ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="7d844-102">ICorDebugInstanceFieldSymbol Interface</span></span>
<span data-ttu-id="7d844-103">Representa la información de símbolos de depuración para un campo de instancia.</span><span class="sxs-lookup"><span data-stu-id="7d844-103">Represents the debug symbol information for an instance field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7d844-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="7d844-104">Methods</span></span>  
  
|<span data-ttu-id="7d844-105">Método</span><span class="sxs-lookup"><span data-stu-id="7d844-105">Method</span></span>|<span data-ttu-id="7d844-106">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="7d844-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7d844-107">GetName (método)</span><span class="sxs-lookup"><span data-stu-id="7d844-107">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-getname-method.md)|<span data-ttu-id="7d844-108">Obtiene el nombre del campo de instancia.</span><span class="sxs-lookup"><span data-stu-id="7d844-108">Gets the name of the instance field.</span></span>|  
|[<span data-ttu-id="7d844-109">GetOffset (método)</span><span class="sxs-lookup"><span data-stu-id="7d844-109">GetOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-getoffset-method.md)|<span data-ttu-id="7d844-110">Obtiene el desplazamiento en bytes de este campo de instancia en su clase primaria.</span><span class="sxs-lookup"><span data-stu-id="7d844-110">Gets the offset in bytes of this instance field in its parent class.</span></span>|  
|[<span data-ttu-id="7d844-111">GetSize (método)</span><span class="sxs-lookup"><span data-stu-id="7d844-111">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-getsize-method.md)|<span data-ttu-id="7d844-112">Obtiene el tamaño, en bytes, del campo de instancia.</span><span class="sxs-lookup"><span data-stu-id="7d844-112">Gets the size in bytes of the instance field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7d844-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7d844-113">Remarks</span></span>  
 <span data-ttu-id="7d844-114">La interfaz `ICorDebugInstanceFieldSymbol` se utiliza para recuperar la información de símbolos de depuración para un campo de instancia.</span><span class="sxs-lookup"><span data-stu-id="7d844-114">The `ICorDebugInstanceFieldSymbol` interface is used to retrieve the debug symbol information for an instance field.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7d844-115">Esta interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="7d844-115">This interface is available with .NET Native only.</span></span> <span data-ttu-id="7d844-116">Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="7d844-116">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d844-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7d844-117">Requirements</span></span>  
 <span data-ttu-id="7d844-118">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7d844-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d844-119">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="7d844-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7d844-120">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7d844-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7d844-121">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d844-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d844-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="7d844-122">See also</span></span>

- [<span data-ttu-id="7d844-123">ICorDebugStaticFieldSymbol (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7d844-123">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="7d844-124">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="7d844-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="7d844-125">Depuración</span><span class="sxs-lookup"><span data-stu-id="7d844-125">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
