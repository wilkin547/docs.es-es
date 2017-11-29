---
title: Interfaz de ICorDebugVirtualUnwinder
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: a09e9ccc-0b37-43e3-95c1-bc5fa7ee5f42
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d22fa926b300384b7f790468b1b3d0becafdb942
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugvirtualunwinder-interface"></a><span data-ttu-id="8a5ab-102">Interfaz de ICorDebugVirtualUnwinder</span><span class="sxs-lookup"><span data-stu-id="8a5ab-102">ICorDebugVirtualUnwinder Interface</span></span>
<span data-ttu-id="8a5ab-103">Proporciona métodos que ayudan al desenredo de la pila.</span><span class="sxs-lookup"><span data-stu-id="8a5ab-103">Provides methods to help in stack unwinding.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8a5ab-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="8a5ab-104">Methods</span></span>  
  
|<span data-ttu-id="8a5ab-105">Método</span><span class="sxs-lookup"><span data-stu-id="8a5ab-105">Method</span></span>|<span data-ttu-id="8a5ab-106">Name</span><span class="sxs-lookup"><span data-stu-id="8a5ab-106">Name</span></span>|  
|------------|----------|  
|[<span data-ttu-id="8a5ab-107">GetContext (método)</span><span class="sxs-lookup"><span data-stu-id="8a5ab-107">GetContext Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvirtualunwinder-getcontext-method.md)|<span data-ttu-id="8a5ab-108">Obtiene el contexto actual de este responsable del desenredado.</span><span class="sxs-lookup"><span data-stu-id="8a5ab-108">Gets the current context of this unwinder.</span></span>|  
|[<span data-ttu-id="8a5ab-109">Next (método)</span><span class="sxs-lookup"><span data-stu-id="8a5ab-109">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvirtualunwinder-next-method.md)|<span data-ttu-id="8a5ab-110">Avanza hasta el contexto del llamador.</span><span class="sxs-lookup"><span data-stu-id="8a5ab-110">Advances to the caller's context.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8a5ab-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8a5ab-111">Remarks</span></span>  
 <span data-ttu-id="8a5ab-112">Los miembros de la interfaz `ICorDebugVirtualUnwinder` se implementan mediante el depurador para ayudar al desenredo de pila.</span><span class="sxs-lookup"><span data-stu-id="8a5ab-112">The members of the `ICorDebugVirtualUnwinder` interface are implemented by the debugger to help in stack unwinding.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8a5ab-113">Esta interfaz solo está disponible con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="8a5ab-113">This interface is available with .NET Native only.</span></span> <span data-ttu-id="8a5ab-114">Si implementa esta interfaz para escenarios de ICorDebug fuera de .NET Native, Common Language Runtime ignorará esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="8a5ab-114">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a5ab-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8a5ab-115">Requirements</span></span>  
 <span data-ttu-id="8a5ab-116">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a5ab-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a5ab-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8a5ab-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8a5ab-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8a5ab-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8a5ab-119">**Versiones de .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a5ab-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a5ab-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="8a5ab-120">See Also</span></span>  
 [<span data-ttu-id="8a5ab-121">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="8a5ab-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="8a5ab-122">Depuración</span><span class="sxs-lookup"><span data-stu-id="8a5ab-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
