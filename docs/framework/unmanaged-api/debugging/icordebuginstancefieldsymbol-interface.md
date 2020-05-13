---
title: Interfaz ICorDebugInstanceFieldSymbol
ms.date: 03/30/2017
ms.assetid: a4a8f259-b83a-4425-ae8b-72b067dbc0d9
ms.openlocfilehash: 092f2a8acdffa9f91176bdf0ca10b8db9cff6d37
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209935"
---
# <a name="icordebuginstancefieldsymbol-interface"></a><span data-ttu-id="42c21-102">Interfaz ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="42c21-102">ICorDebugInstanceFieldSymbol Interface</span></span>
<span data-ttu-id="42c21-103">Representa la información de símbolos de depuración para un campo de instancia.</span><span class="sxs-lookup"><span data-stu-id="42c21-103">Represents the debug symbol information for an instance field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="42c21-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="42c21-104">Methods</span></span>  
  
|<span data-ttu-id="42c21-105">Método</span><span class="sxs-lookup"><span data-stu-id="42c21-105">Method</span></span>|<span data-ttu-id="42c21-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="42c21-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="42c21-107">Método GetName</span><span class="sxs-lookup"><span data-stu-id="42c21-107">GetName Method</span></span>](icordebuginstancefieldsymbol-getname-method.md)|<span data-ttu-id="42c21-108">Obtiene el nombre del campo de instancia.</span><span class="sxs-lookup"><span data-stu-id="42c21-108">Gets the name of the instance field.</span></span>|  
|[<span data-ttu-id="42c21-109">Método GetOffset</span><span class="sxs-lookup"><span data-stu-id="42c21-109">GetOffset Method</span></span>](icordebuginstancefieldsymbol-getoffset-method.md)|<span data-ttu-id="42c21-110">Obtiene el desplazamiento en bytes de este campo de instancia en su clase primaria.</span><span class="sxs-lookup"><span data-stu-id="42c21-110">Gets the offset in bytes of this instance field in its parent class.</span></span>|  
|[<span data-ttu-id="42c21-111">Método GetSize</span><span class="sxs-lookup"><span data-stu-id="42c21-111">GetSize Method</span></span>](icordebuginstancefieldsymbol-getsize-method.md)|<span data-ttu-id="42c21-112">Obtiene el tamaño, en bytes, del campo de instancia.</span><span class="sxs-lookup"><span data-stu-id="42c21-112">Gets the size in bytes of the instance field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="42c21-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="42c21-113">Remarks</span></span>  
 <span data-ttu-id="42c21-114">La interfaz `ICorDebugInstanceFieldSymbol` se utiliza para recuperar la información de símbolos de depuración para un campo de instancia.</span><span class="sxs-lookup"><span data-stu-id="42c21-114">The `ICorDebugInstanceFieldSymbol` interface is used to retrieve the debug symbol information for an instance field.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="42c21-115">Esta interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="42c21-115">This interface is available with .NET Native only.</span></span> <span data-ttu-id="42c21-116">Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="42c21-116">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42c21-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="42c21-117">Requirements</span></span>  
 <span data-ttu-id="42c21-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="42c21-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42c21-119">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="42c21-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="42c21-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="42c21-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="42c21-121">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42c21-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42c21-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="42c21-122">See also</span></span>

- [<span data-ttu-id="42c21-123">Interfaz ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="42c21-123">ICorDebugStaticFieldSymbol Interface</span></span>](icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="42c21-124">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="42c21-124">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="42c21-125">Depuración</span><span class="sxs-lookup"><span data-stu-id="42c21-125">Debugging</span></span>](index.md)
