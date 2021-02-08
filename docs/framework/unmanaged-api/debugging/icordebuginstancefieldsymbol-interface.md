---
description: 'Más información acerca de: interfaz ICorDebugInstanceFieldSymbol'
title: Interfaz ICorDebugInstanceFieldSymbol
ms.date: 03/30/2017
ms.assetid: a4a8f259-b83a-4425-ae8b-72b067dbc0d9
ms.openlocfilehash: aa47c858ec5b4b0d04b851357fe81c0fc9b2e30a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791138"
---
# <a name="icordebuginstancefieldsymbol-interface"></a><span data-ttu-id="415ed-103">Interfaz ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="415ed-103">ICorDebugInstanceFieldSymbol Interface</span></span>

<span data-ttu-id="415ed-104">Representa la información de símbolos de depuración para un campo de instancia.</span><span class="sxs-lookup"><span data-stu-id="415ed-104">Represents the debug symbol information for an instance field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="415ed-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="415ed-105">Methods</span></span>  
  
|<span data-ttu-id="415ed-106">Método</span><span class="sxs-lookup"><span data-stu-id="415ed-106">Method</span></span>|<span data-ttu-id="415ed-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="415ed-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="415ed-108">Método GetName</span><span class="sxs-lookup"><span data-stu-id="415ed-108">GetName Method</span></span>](icordebuginstancefieldsymbol-getname-method.md)|<span data-ttu-id="415ed-109">Obtiene el nombre del campo de instancia.</span><span class="sxs-lookup"><span data-stu-id="415ed-109">Gets the name of the instance field.</span></span>|  
|[<span data-ttu-id="415ed-110">Método GetOffset</span><span class="sxs-lookup"><span data-stu-id="415ed-110">GetOffset Method</span></span>](icordebuginstancefieldsymbol-getoffset-method.md)|<span data-ttu-id="415ed-111">Obtiene el desplazamiento en bytes de este campo de instancia en su clase primaria.</span><span class="sxs-lookup"><span data-stu-id="415ed-111">Gets the offset in bytes of this instance field in its parent class.</span></span>|  
|[<span data-ttu-id="415ed-112">Método GetSize</span><span class="sxs-lookup"><span data-stu-id="415ed-112">GetSize Method</span></span>](icordebuginstancefieldsymbol-getsize-method.md)|<span data-ttu-id="415ed-113">Obtiene el tamaño, en bytes, del campo de instancia.</span><span class="sxs-lookup"><span data-stu-id="415ed-113">Gets the size in bytes of the instance field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="415ed-114">Observaciones</span><span class="sxs-lookup"><span data-stu-id="415ed-114">Remarks</span></span>  

 <span data-ttu-id="415ed-115">La interfaz `ICorDebugInstanceFieldSymbol` se utiliza para recuperar la información de símbolos de depuración para un campo de instancia.</span><span class="sxs-lookup"><span data-stu-id="415ed-115">The `ICorDebugInstanceFieldSymbol` interface is used to retrieve the debug symbol information for an instance field.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="415ed-116">Esta interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="415ed-116">This interface is available with .NET Native only.</span></span> <span data-ttu-id="415ed-117">Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="415ed-117">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="415ed-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="415ed-118">Requirements</span></span>  

 <span data-ttu-id="415ed-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="415ed-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="415ed-120">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="415ed-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="415ed-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="415ed-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="415ed-122">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="415ed-122">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="415ed-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="415ed-123">See also</span></span>

- [<span data-ttu-id="415ed-124">Interfaz ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="415ed-124">ICorDebugStaticFieldSymbol Interface</span></span>](icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="415ed-125">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="415ed-125">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="415ed-126">Depuración</span><span class="sxs-lookup"><span data-stu-id="415ed-126">Debugging</span></span>](index.md)
