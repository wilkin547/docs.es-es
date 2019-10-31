---
title: CorDebugIntercept (Enumeración)
ms.date: 03/30/2017
api_name:
- CorDebugIntercept
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugIntercept
helpviewer_keywords:
- CorDebugIntercept enumeration [.NET Framework debugging]
ms.assetid: 3d5b642e-7ef2-428b-a5ae-509c35ed461a
topic_type:
- apiref
ms.openlocfilehash: 144bdb1b4e479c1e75f89911ad5002e2650e405d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73098121"
---
# <a name="cordebugintercept-enumeration"></a><span data-ttu-id="78fcd-102">CorDebugIntercept (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="78fcd-102">CorDebugIntercept Enumeration</span></span>
<span data-ttu-id="78fcd-103">Indica los tipos de código que se pueden interceptar, es decir, ejecutar paso a paso.</span><span class="sxs-lookup"><span data-stu-id="78fcd-103">Indicates the types of code that can be intercepted (that is, stepped into).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78fcd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="78fcd-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugIntercept {  
    INTERCEPT_NONE                = 0x0,  
    INTERCEPT_CLASS_INIT          = 0x01,  
    INTERCEPT_EXCEPTION_FILTER    = 0x02,  
    INTERCEPT_SECURITY            = 0x04,  
    INTERCEPT_CONTEXT_POLICY      = 0x08,  
    INTERCEPT_INTERCEPTION        = 0x10,  
    INTERCEPT_ALL                 = 0xffff  
} CorDebugIntercept;  
```  
  
## <a name="members"></a><span data-ttu-id="78fcd-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="78fcd-105">Members</span></span>  
  
|<span data-ttu-id="78fcd-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="78fcd-106">Member</span></span>|<span data-ttu-id="78fcd-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="78fcd-107">Description</span></span>|  
|------------|-----------------|  
|`INTERCEPT_NONE`|<span data-ttu-id="78fcd-108">No se puede interceptar ningún código.</span><span class="sxs-lookup"><span data-stu-id="78fcd-108">No code can be intercepted.</span></span>|  
|`INTERCEPT_CLASS_INIT`|<span data-ttu-id="78fcd-109">Se puede interceptar un constructor.</span><span class="sxs-lookup"><span data-stu-id="78fcd-109">A constructor can be intercepted.</span></span>|  
|`INTERCEPT_EXCEPTION_FILTER`|<span data-ttu-id="78fcd-110">Se puede interceptar un filtro de excepción.</span><span class="sxs-lookup"><span data-stu-id="78fcd-110">An exception filter can be intercepted.</span></span>|  
|`INTERCEPT_SECURITY`|<span data-ttu-id="78fcd-111">Se puede interceptar código que exija seguridad.</span><span class="sxs-lookup"><span data-stu-id="78fcd-111">Code that enforces security can be intercepted.</span></span>|  
|`INTERCEPT_CONTEXT_POLICY`|<span data-ttu-id="78fcd-112">Se puede interceptar una directiva de contexto.</span><span class="sxs-lookup"><span data-stu-id="78fcd-112">A context policy can be intercepted.</span></span>|  
|`INTERCEPT_INTERCEPTION`|<span data-ttu-id="78fcd-113">No se utiliza.</span><span class="sxs-lookup"><span data-stu-id="78fcd-113">Not used.</span></span>|  
|`INTERCEPT_ALL`|<span data-ttu-id="78fcd-114">Se puede interceptar todo el código.</span><span class="sxs-lookup"><span data-stu-id="78fcd-114">All code can be intercepted.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="78fcd-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="78fcd-115">Remarks</span></span>  
 <span data-ttu-id="78fcd-116">Use el método [ICorDebugStepper:: setinterceptmask (](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setinterceptmask-method.md) para establecer los tipos de código que se pueden interceptar.</span><span class="sxs-lookup"><span data-stu-id="78fcd-116">Use the [ICorDebugStepper::SetInterceptMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setinterceptmask-method.md) method to establish the types of code that can be intercepted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78fcd-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="78fcd-117">Requirements</span></span>  
 <span data-ttu-id="78fcd-118">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="78fcd-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78fcd-119">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="78fcd-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="78fcd-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="78fcd-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="78fcd-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78fcd-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78fcd-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="78fcd-122">See also</span></span>

- [<span data-ttu-id="78fcd-123">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="78fcd-123">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
