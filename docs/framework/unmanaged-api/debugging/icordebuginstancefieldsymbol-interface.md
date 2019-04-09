---
title: Interfaz ICorDebugInstanceFieldSymbol
ms.date: 03/30/2017
ms.assetid: a4a8f259-b83a-4425-ae8b-72b067dbc0d9
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b5c0759989e069169c7e68b71206d9a50b04ad63
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59111493"
---
# <a name="icordebuginstancefieldsymbol-interface"></a><span data-ttu-id="e42f3-102">Interfaz ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="e42f3-102">ICorDebugInstanceFieldSymbol Interface</span></span>
<span data-ttu-id="e42f3-103">Representa la información de símbolos de depuración para un campo de instancia.</span><span class="sxs-lookup"><span data-stu-id="e42f3-103">Represents the debug symbol information for an instance field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e42f3-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="e42f3-104">Methods</span></span>  
  
|<span data-ttu-id="e42f3-105">Método</span><span class="sxs-lookup"><span data-stu-id="e42f3-105">Method</span></span>|<span data-ttu-id="e42f3-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="e42f3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e42f3-107">Método GetName</span><span class="sxs-lookup"><span data-stu-id="e42f3-107">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-getname-method.md)|<span data-ttu-id="e42f3-108">Obtiene el nombre del campo de instancia.</span><span class="sxs-lookup"><span data-stu-id="e42f3-108">Gets the name of the instance field.</span></span>|  
|[<span data-ttu-id="e42f3-109">Método GetOffset</span><span class="sxs-lookup"><span data-stu-id="e42f3-109">GetOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-getoffset-method.md)|<span data-ttu-id="e42f3-110">Obtiene el desplazamiento en bytes de este campo de instancia en su clase primaria.</span><span class="sxs-lookup"><span data-stu-id="e42f3-110">Gets the offset in bytes of this instance field in its parent class.</span></span>|  
|[<span data-ttu-id="e42f3-111">Método GetSize</span><span class="sxs-lookup"><span data-stu-id="e42f3-111">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-getsize-method.md)|<span data-ttu-id="e42f3-112">Obtiene el tamaño, en bytes, del campo de instancia.</span><span class="sxs-lookup"><span data-stu-id="e42f3-112">Gets the size in bytes of the instance field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e42f3-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e42f3-113">Remarks</span></span>  
 <span data-ttu-id="e42f3-114">La interfaz `ICorDebugInstanceFieldSymbol` se utiliza para recuperar la información de símbolos de depuración para un campo de instancia.</span><span class="sxs-lookup"><span data-stu-id="e42f3-114">The `ICorDebugInstanceFieldSymbol` interface is used to retrieve the debug symbol information for an instance field.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e42f3-115">Esta interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="e42f3-115">This interface is available with .NET Native only.</span></span> <span data-ttu-id="e42f3-116">Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="e42f3-116">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e42f3-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e42f3-117">Requirements</span></span>  
 <span data-ttu-id="e42f3-118">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e42f3-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e42f3-119">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e42f3-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e42f3-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e42f3-120">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="e42f3-121">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="e42f3-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e42f3-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="e42f3-122">See also</span></span>

- [<span data-ttu-id="e42f3-123">Interfaz ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="e42f3-123">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="e42f3-124">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="e42f3-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="e42f3-125">Depuración</span><span class="sxs-lookup"><span data-stu-id="e42f3-125">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
