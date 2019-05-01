---
title: Interfaz de ICorDebugVirtualUnwinder
ms.date: 03/30/2017
ms.assetid: a09e9ccc-0b37-43e3-95c1-bc5fa7ee5f42
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 639cfc514d2a206f0de72db4b0bac02b53305ae3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61946164"
---
# <a name="icordebugvirtualunwinder-interface"></a><span data-ttu-id="63226-102">Interfaz de ICorDebugVirtualUnwinder</span><span class="sxs-lookup"><span data-stu-id="63226-102">ICorDebugVirtualUnwinder Interface</span></span>
<span data-ttu-id="63226-103">Proporciona métodos que ayudan al desenredo de la pila.</span><span class="sxs-lookup"><span data-stu-id="63226-103">Provides methods to help in stack unwinding.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="63226-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="63226-104">Methods</span></span>  
  
|<span data-ttu-id="63226-105">Método</span><span class="sxs-lookup"><span data-stu-id="63226-105">Method</span></span>|<span data-ttu-id="63226-106">Name</span><span class="sxs-lookup"><span data-stu-id="63226-106">Name</span></span>|  
|------------|----------|  
|[<span data-ttu-id="63226-107">GetContext (método)</span><span class="sxs-lookup"><span data-stu-id="63226-107">GetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvirtualunwinder-getcontext-method.md)|<span data-ttu-id="63226-108">Obtiene el contexto actual de este responsable del desenredado.</span><span class="sxs-lookup"><span data-stu-id="63226-108">Gets the current context of this unwinder.</span></span>|  
|[<span data-ttu-id="63226-109">Next (método)</span><span class="sxs-lookup"><span data-stu-id="63226-109">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvirtualunwinder-next-method.md)|<span data-ttu-id="63226-110">Avanza hasta el contexto del llamador.</span><span class="sxs-lookup"><span data-stu-id="63226-110">Advances to the caller's context.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="63226-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="63226-111">Remarks</span></span>  
 <span data-ttu-id="63226-112">Los miembros de la interfaz `ICorDebugVirtualUnwinder` se implementan mediante el depurador para ayudar al desenredo de pila.</span><span class="sxs-lookup"><span data-stu-id="63226-112">The members of the `ICorDebugVirtualUnwinder` interface are implemented by the debugger to help in stack unwinding.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="63226-113">Esta interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="63226-113">This interface is available with .NET Native only.</span></span> <span data-ttu-id="63226-114">Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="63226-114">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63226-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="63226-115">Requirements</span></span>  
 <span data-ttu-id="63226-116">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63226-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63226-117">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="63226-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="63226-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="63226-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="63226-119">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63226-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63226-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="63226-120">See also</span></span>

- [<span data-ttu-id="63226-121">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="63226-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="63226-122">Depuración</span><span class="sxs-lookup"><span data-stu-id="63226-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
