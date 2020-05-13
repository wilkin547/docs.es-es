---
title: Interfaz ICorDebugStaticFieldSymbol
ms.date: 03/30/2017
ms.assetid: c0b93609-631e-4b15-878a-189ede922631
ms.openlocfilehash: f9b82f0f98a668555a8096d7575c049c31cae93a
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379439"
---
# <a name="icordebugstaticfieldsymbol-interface"></a><span data-ttu-id="0f968-102">Interfaz ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="0f968-102">ICorDebugStaticFieldSymbol Interface</span></span>
<span data-ttu-id="0f968-103">Representa la información de símbolos de depuración para un campo estático.</span><span class="sxs-lookup"><span data-stu-id="0f968-103">Represents the debug symbol information for a static field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0f968-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="0f968-104">Methods</span></span>  
  
|<span data-ttu-id="0f968-105">Método</span><span class="sxs-lookup"><span data-stu-id="0f968-105">Method</span></span>|<span data-ttu-id="0f968-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="0f968-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0f968-107">Método GetAddress</span><span class="sxs-lookup"><span data-stu-id="0f968-107">GetAddress Method</span></span>](icordebugstaticfieldsymbol-getaddress-method.md)|<span data-ttu-id="0f968-108">Obtiene la dirección del campo estático.</span><span class="sxs-lookup"><span data-stu-id="0f968-108">Gets the address of the static field.</span></span>|  
|[<span data-ttu-id="0f968-109">Método GetName</span><span class="sxs-lookup"><span data-stu-id="0f968-109">GetName Method</span></span>](icordebugstaticfieldsymbol-getname-method.md)|<span data-ttu-id="0f968-110">Obtiene el nombre del campo estático.</span><span class="sxs-lookup"><span data-stu-id="0f968-110">Gets the name of the static field.</span></span>|  
|[<span data-ttu-id="0f968-111">Método GetSize</span><span class="sxs-lookup"><span data-stu-id="0f968-111">GetSize Method</span></span>](icordebugstaticfieldsymbol-getsize-method.md)|<span data-ttu-id="0f968-112">Obtiene el tamaño del campo estático, en bytes.</span><span class="sxs-lookup"><span data-stu-id="0f968-112">Gets the size in bytes of the static field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0f968-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0f968-113">Remarks</span></span>  
 <span data-ttu-id="0f968-114">La interfaz `ICorDebugStaticFieldSymbol` se utiliza para recuperar la información de símbolos de depuración para un campo estático.</span><span class="sxs-lookup"><span data-stu-id="0f968-114">The `ICorDebugStaticFieldSymbol` interface is used to retrieve the debug symbol information for a static field.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0f968-115">Esta interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="0f968-115">This interface is available with .NET Native only.</span></span> <span data-ttu-id="0f968-116">Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="0f968-116">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f968-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0f968-117">Requirements</span></span>  
 <span data-ttu-id="0f968-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0f968-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f968-119">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0f968-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0f968-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0f968-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0f968-121">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f968-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f968-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0f968-122">See also</span></span>

- [<span data-ttu-id="0f968-123">Interfaz ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="0f968-123">ICorDebugInstanceFieldSymbol Interface</span></span>](icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="0f968-124">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="0f968-124">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="0f968-125">Depuración</span><span class="sxs-lookup"><span data-stu-id="0f968-125">Debugging</span></span>](index.md)
