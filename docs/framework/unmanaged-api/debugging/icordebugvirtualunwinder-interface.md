---
description: 'Más información acerca de: interfaz ICorDebugVirtualUnwinder'
title: Interfaz de ICorDebugVirtualUnwinder
ms.date: 03/30/2017
ms.assetid: a09e9ccc-0b37-43e3-95c1-bc5fa7ee5f42
ms.openlocfilehash: e941ace2e7f72c9f7956c03bae19f9b92094b338
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99738083"
---
# <a name="icordebugvirtualunwinder-interface"></a><span data-ttu-id="a47e6-103">Interfaz de ICorDebugVirtualUnwinder</span><span class="sxs-lookup"><span data-stu-id="a47e6-103">ICorDebugVirtualUnwinder Interface</span></span>

<span data-ttu-id="a47e6-104">Proporciona métodos que ayudan al desenredo de la pila.</span><span class="sxs-lookup"><span data-stu-id="a47e6-104">Provides methods to help in stack unwinding.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a47e6-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="a47e6-105">Methods</span></span>  
  
|<span data-ttu-id="a47e6-106">Método</span><span class="sxs-lookup"><span data-stu-id="a47e6-106">Method</span></span>|<span data-ttu-id="a47e6-107">Nombre</span><span class="sxs-lookup"><span data-stu-id="a47e6-107">Name</span></span>|  
|------------|----------|  
|[<span data-ttu-id="a47e6-108">Método GetContext</span><span class="sxs-lookup"><span data-stu-id="a47e6-108">GetContext Method</span></span>](icordebugvirtualunwinder-getcontext-method.md)|<span data-ttu-id="a47e6-109">Obtiene el contexto actual de este responsable del desenredado.</span><span class="sxs-lookup"><span data-stu-id="a47e6-109">Gets the current context of this unwinder.</span></span>|  
|[<span data-ttu-id="a47e6-110">Next (método)</span><span class="sxs-lookup"><span data-stu-id="a47e6-110">Next Method</span></span>](icordebugvirtualunwinder-next-method.md)|<span data-ttu-id="a47e6-111">Avanza hasta el contexto del llamador.</span><span class="sxs-lookup"><span data-stu-id="a47e6-111">Advances to the caller's context.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a47e6-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a47e6-112">Remarks</span></span>  

 <span data-ttu-id="a47e6-113">Los miembros de la interfaz `ICorDebugVirtualUnwinder` se implementan mediante el depurador para ayudar al desenredo de pila.</span><span class="sxs-lookup"><span data-stu-id="a47e6-113">The members of the `ICorDebugVirtualUnwinder` interface are implemented by the debugger to help in stack unwinding.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a47e6-114">Esta interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="a47e6-114">This interface is available with .NET Native only.</span></span> <span data-ttu-id="a47e6-115">Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="a47e6-115">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a47e6-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a47e6-116">Requirements</span></span>  

 <span data-ttu-id="a47e6-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a47e6-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a47e6-118">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a47e6-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a47e6-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a47e6-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a47e6-120">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a47e6-120">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a47e6-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="a47e6-121">See also</span></span>

- [<span data-ttu-id="a47e6-122">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="a47e6-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="a47e6-123">Depuración</span><span class="sxs-lookup"><span data-stu-id="a47e6-123">Debugging</span></span>](index.md)
