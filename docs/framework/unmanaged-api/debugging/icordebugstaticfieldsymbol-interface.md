---
title: ICorDebugStaticFieldSymbol (Interfaz)
ms.date: 03/30/2017
ms.assetid: c0b93609-631e-4b15-878a-189ede922631
ms.openlocfilehash: b50b9c8435f19e1a77229f01dc85514f5f75c9f5
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791798"
---
# <a name="icordebugstaticfieldsymbol-interface"></a><span data-ttu-id="03c29-102">ICorDebugStaticFieldSymbol (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="03c29-102">ICorDebugStaticFieldSymbol Interface</span></span>
<span data-ttu-id="03c29-103">Representa la información de símbolos de depuración para un campo estático.</span><span class="sxs-lookup"><span data-stu-id="03c29-103">Represents the debug symbol information for a static field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="03c29-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="03c29-104">Methods</span></span>  
  
|<span data-ttu-id="03c29-105">Método</span><span class="sxs-lookup"><span data-stu-id="03c29-105">Method</span></span>|<span data-ttu-id="03c29-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="03c29-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="03c29-107">GetAddress (método)</span><span class="sxs-lookup"><span data-stu-id="03c29-107">GetAddress Method</span></span>](icordebugstaticfieldsymbol-getaddress-method.md)|<span data-ttu-id="03c29-108">Obtiene la dirección del campo estático.</span><span class="sxs-lookup"><span data-stu-id="03c29-108">Gets the address of the static field.</span></span>|  
|[<span data-ttu-id="03c29-109">GetName (método)</span><span class="sxs-lookup"><span data-stu-id="03c29-109">GetName Method</span></span>](icordebugstaticfieldsymbol-getname-method.md)|<span data-ttu-id="03c29-110">Obtiene el nombre del campo estático.</span><span class="sxs-lookup"><span data-stu-id="03c29-110">Gets the name of the static field.</span></span>|  
|[<span data-ttu-id="03c29-111">GetSize (método)</span><span class="sxs-lookup"><span data-stu-id="03c29-111">GetSize Method</span></span>](icordebugstaticfieldsymbol-getsize-method.md)|<span data-ttu-id="03c29-112">Obtiene el tamaño del campo estático, en bytes.</span><span class="sxs-lookup"><span data-stu-id="03c29-112">Gets the size in bytes of the static field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="03c29-113">Notas</span><span class="sxs-lookup"><span data-stu-id="03c29-113">Remarks</span></span>  
 <span data-ttu-id="03c29-114">La interfaz `ICorDebugStaticFieldSymbol` se utiliza para recuperar la información de símbolos de depuración para un campo estático.</span><span class="sxs-lookup"><span data-stu-id="03c29-114">The `ICorDebugStaticFieldSymbol` interface is used to retrieve the debug symbol information for a static field.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="03c29-115">Esta interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="03c29-115">This interface is available with .NET Native only.</span></span> <span data-ttu-id="03c29-116">Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="03c29-116">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03c29-117">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="03c29-117">Requirements</span></span>  
 <span data-ttu-id="03c29-118">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="03c29-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03c29-119">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="03c29-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="03c29-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="03c29-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="03c29-121">**.NET Framework versiones:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03c29-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03c29-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="03c29-122">See also</span></span>

- [<span data-ttu-id="03c29-123">ICorDebugInstanceFieldSymbol (interfaz)</span><span class="sxs-lookup"><span data-stu-id="03c29-123">ICorDebugInstanceFieldSymbol Interface</span></span>](icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="03c29-124">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="03c29-124">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="03c29-125">Depuración</span><span class="sxs-lookup"><span data-stu-id="03c29-125">Debugging</span></span>](index.md)
