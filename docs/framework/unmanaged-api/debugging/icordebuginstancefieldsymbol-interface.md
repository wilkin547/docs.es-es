---
title: Interfaz ICorDebugInstanceFieldSymbol
ms.date: 03/30/2017
ms.assetid: a4a8f259-b83a-4425-ae8b-72b067dbc0d9
ms.openlocfilehash: 2ed1d70f554ca0a4a49639fe53a2ddbb0497c0a1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122731"
---
# <a name="icordebuginstancefieldsymbol-interface"></a><span data-ttu-id="22dd8-102">Interfaz ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="22dd8-102">ICorDebugInstanceFieldSymbol Interface</span></span>
<span data-ttu-id="22dd8-103">Representa la información de símbolos de depuración para un campo de instancia.</span><span class="sxs-lookup"><span data-stu-id="22dd8-103">Represents the debug symbol information for an instance field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="22dd8-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="22dd8-104">Methods</span></span>  
  
|<span data-ttu-id="22dd8-105">Método</span><span class="sxs-lookup"><span data-stu-id="22dd8-105">Method</span></span>|<span data-ttu-id="22dd8-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="22dd8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="22dd8-107">GetName (método)</span><span class="sxs-lookup"><span data-stu-id="22dd8-107">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-getname-method.md)|<span data-ttu-id="22dd8-108">Obtiene el nombre del campo de instancia.</span><span class="sxs-lookup"><span data-stu-id="22dd8-108">Gets the name of the instance field.</span></span>|  
|[<span data-ttu-id="22dd8-109">GetOffset (método)</span><span class="sxs-lookup"><span data-stu-id="22dd8-109">GetOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-getoffset-method.md)|<span data-ttu-id="22dd8-110">Obtiene el desplazamiento en bytes de este campo de instancia en su clase primaria.</span><span class="sxs-lookup"><span data-stu-id="22dd8-110">Gets the offset in bytes of this instance field in its parent class.</span></span>|  
|[<span data-ttu-id="22dd8-111">GetSize (método)</span><span class="sxs-lookup"><span data-stu-id="22dd8-111">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-getsize-method.md)|<span data-ttu-id="22dd8-112">Obtiene el tamaño, en bytes, del campo de instancia.</span><span class="sxs-lookup"><span data-stu-id="22dd8-112">Gets the size in bytes of the instance field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="22dd8-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="22dd8-113">Remarks</span></span>  
 <span data-ttu-id="22dd8-114">La interfaz `ICorDebugInstanceFieldSymbol` se utiliza para recuperar la información de símbolos de depuración para un campo de instancia.</span><span class="sxs-lookup"><span data-stu-id="22dd8-114">The `ICorDebugInstanceFieldSymbol` interface is used to retrieve the debug symbol information for an instance field.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="22dd8-115">Esta interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="22dd8-115">This interface is available with .NET Native only.</span></span> <span data-ttu-id="22dd8-116">Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="22dd8-116">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22dd8-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="22dd8-117">Requirements</span></span>  
 <span data-ttu-id="22dd8-118">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22dd8-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22dd8-119">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="22dd8-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="22dd8-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="22dd8-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="22dd8-121">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22dd8-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22dd8-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="22dd8-122">See also</span></span>

- [<span data-ttu-id="22dd8-123">ICorDebugStaticFieldSymbol (interfaz)</span><span class="sxs-lookup"><span data-stu-id="22dd8-123">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="22dd8-124">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="22dd8-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="22dd8-125">Depuración</span><span class="sxs-lookup"><span data-stu-id="22dd8-125">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
