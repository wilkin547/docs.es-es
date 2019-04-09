---
title: Interfaz ICorDebugStaticFieldSymbol
ms.date: 03/30/2017
ms.assetid: c0b93609-631e-4b15-878a-189ede922631
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 382f3fc9377c25379809badac0bc580c3593cbde
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59103901"
---
# <a name="icordebugstaticfieldsymbol-interface"></a><span data-ttu-id="ce01e-102">Interfaz ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="ce01e-102">ICorDebugStaticFieldSymbol Interface</span></span>
<span data-ttu-id="ce01e-103">Representa la información de símbolos de depuración para un campo estático.</span><span class="sxs-lookup"><span data-stu-id="ce01e-103">Represents the debug symbol information for a static field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ce01e-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="ce01e-104">Methods</span></span>  
  
|<span data-ttu-id="ce01e-105">Método</span><span class="sxs-lookup"><span data-stu-id="ce01e-105">Method</span></span>|<span data-ttu-id="ce01e-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="ce01e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ce01e-107">Método GetAddress</span><span class="sxs-lookup"><span data-stu-id="ce01e-107">GetAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-getaddress-method.md)|<span data-ttu-id="ce01e-108">Obtiene la dirección del campo estático.</span><span class="sxs-lookup"><span data-stu-id="ce01e-108">Gets the address of the static field.</span></span>|  
|[<span data-ttu-id="ce01e-109">Método GetName</span><span class="sxs-lookup"><span data-stu-id="ce01e-109">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-getname-method.md)|<span data-ttu-id="ce01e-110">Obtiene el nombre del campo estático.</span><span class="sxs-lookup"><span data-stu-id="ce01e-110">Gets the name of the static field.</span></span>|  
|[<span data-ttu-id="ce01e-111">Método GetSize</span><span class="sxs-lookup"><span data-stu-id="ce01e-111">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-getsize-method.md)|<span data-ttu-id="ce01e-112">Obtiene el tamaño del campo estático, en bytes.</span><span class="sxs-lookup"><span data-stu-id="ce01e-112">Gets the size in bytes of the static field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ce01e-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ce01e-113">Remarks</span></span>  
 <span data-ttu-id="ce01e-114">La interfaz `ICorDebugStaticFieldSymbol` se utiliza para recuperar la información de símbolos de depuración para un campo estático.</span><span class="sxs-lookup"><span data-stu-id="ce01e-114">The `ICorDebugStaticFieldSymbol` interface is used to retrieve the debug symbol information for a static field.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ce01e-115">Esta interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="ce01e-115">This interface is available with .NET Native only.</span></span> <span data-ttu-id="ce01e-116">Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="ce01e-116">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce01e-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ce01e-117">Requirements</span></span>  
 <span data-ttu-id="ce01e-118">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce01e-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce01e-119">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ce01e-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ce01e-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ce01e-120">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="ce01e-121">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="ce01e-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ce01e-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="ce01e-122">See also</span></span>

- [<span data-ttu-id="ce01e-123">Interfaz ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="ce01e-123">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="ce01e-124">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="ce01e-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="ce01e-125">Depuración</span><span class="sxs-lookup"><span data-stu-id="ce01e-125">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
