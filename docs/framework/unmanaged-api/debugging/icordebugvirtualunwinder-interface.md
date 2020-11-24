---
title: Interfaz de ICorDebugVirtualUnwinder
ms.date: 03/30/2017
ms.assetid: a09e9ccc-0b37-43e3-95c1-bc5fa7ee5f42
ms.openlocfilehash: 67f2234d37165e421874815bdc2ef34f8f50749a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679382"
---
# <a name="icordebugvirtualunwinder-interface"></a><span data-ttu-id="b85d6-102">Interfaz de ICorDebugVirtualUnwinder</span><span class="sxs-lookup"><span data-stu-id="b85d6-102">ICorDebugVirtualUnwinder Interface</span></span>

<span data-ttu-id="b85d6-103">Proporciona métodos que ayudan al desenredo de la pila.</span><span class="sxs-lookup"><span data-stu-id="b85d6-103">Provides methods to help in stack unwinding.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b85d6-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="b85d6-104">Methods</span></span>  
  
|<span data-ttu-id="b85d6-105">Método</span><span class="sxs-lookup"><span data-stu-id="b85d6-105">Method</span></span>|<span data-ttu-id="b85d6-106">Nombre</span><span class="sxs-lookup"><span data-stu-id="b85d6-106">Name</span></span>|  
|------------|----------|  
|[<span data-ttu-id="b85d6-107">Método GetContext</span><span class="sxs-lookup"><span data-stu-id="b85d6-107">GetContext Method</span></span>](icordebugvirtualunwinder-getcontext-method.md)|<span data-ttu-id="b85d6-108">Obtiene el contexto actual de este responsable del desenredado.</span><span class="sxs-lookup"><span data-stu-id="b85d6-108">Gets the current context of this unwinder.</span></span>|  
|[<span data-ttu-id="b85d6-109">Next (Método)</span><span class="sxs-lookup"><span data-stu-id="b85d6-109">Next Method</span></span>](icordebugvirtualunwinder-next-method.md)|<span data-ttu-id="b85d6-110">Avanza hasta el contexto del llamador.</span><span class="sxs-lookup"><span data-stu-id="b85d6-110">Advances to the caller's context.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b85d6-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b85d6-111">Remarks</span></span>  

 <span data-ttu-id="b85d6-112">Los miembros de la interfaz `ICorDebugVirtualUnwinder` se implementan mediante el depurador para ayudar al desenredo de pila.</span><span class="sxs-lookup"><span data-stu-id="b85d6-112">The members of the `ICorDebugVirtualUnwinder` interface are implemented by the debugger to help in stack unwinding.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b85d6-113">Esta interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="b85d6-113">This interface is available with .NET Native only.</span></span> <span data-ttu-id="b85d6-114">Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="b85d6-114">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b85d6-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b85d6-115">Requirements</span></span>  

 <span data-ttu-id="b85d6-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b85d6-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b85d6-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b85d6-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b85d6-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b85d6-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b85d6-119">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b85d6-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b85d6-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b85d6-120">See also</span></span>

- [<span data-ttu-id="b85d6-121">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="b85d6-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="b85d6-122">Depuración</span><span class="sxs-lookup"><span data-stu-id="b85d6-122">Debugging</span></span>](index.md)
