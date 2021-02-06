---
description: 'Más información sobre: enumeración Cordebugintercept ('
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
ms.openlocfilehash: ddd17aff309396fdcda37c731ff907224ee17db2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99661979"
---
# <a name="cordebugintercept-enumeration"></a><span data-ttu-id="c99ca-103">CorDebugIntercept (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="c99ca-103">CorDebugIntercept Enumeration</span></span>

<span data-ttu-id="c99ca-104">Indica los tipos de código que se pueden interceptar, es decir, ejecutar paso a paso.</span><span class="sxs-lookup"><span data-stu-id="c99ca-104">Indicates the types of code that can be intercepted (that is, stepped into).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c99ca-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c99ca-105">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="c99ca-106">Members</span><span class="sxs-lookup"><span data-stu-id="c99ca-106">Members</span></span>  
  
|<span data-ttu-id="c99ca-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="c99ca-107">Member</span></span>|<span data-ttu-id="c99ca-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="c99ca-108">Description</span></span>|  
|------------|-----------------|  
|`INTERCEPT_NONE`|<span data-ttu-id="c99ca-109">No se puede interceptar ningún código.</span><span class="sxs-lookup"><span data-stu-id="c99ca-109">No code can be intercepted.</span></span>|  
|`INTERCEPT_CLASS_INIT`|<span data-ttu-id="c99ca-110">Se puede interceptar un constructor.</span><span class="sxs-lookup"><span data-stu-id="c99ca-110">A constructor can be intercepted.</span></span>|  
|`INTERCEPT_EXCEPTION_FILTER`|<span data-ttu-id="c99ca-111">Se puede interceptar un filtro de excepción.</span><span class="sxs-lookup"><span data-stu-id="c99ca-111">An exception filter can be intercepted.</span></span>|  
|`INTERCEPT_SECURITY`|<span data-ttu-id="c99ca-112">Se puede interceptar código que exija seguridad.</span><span class="sxs-lookup"><span data-stu-id="c99ca-112">Code that enforces security can be intercepted.</span></span>|  
|`INTERCEPT_CONTEXT_POLICY`|<span data-ttu-id="c99ca-113">Se puede interceptar una directiva de contexto.</span><span class="sxs-lookup"><span data-stu-id="c99ca-113">A context policy can be intercepted.</span></span>|  
|`INTERCEPT_INTERCEPTION`|<span data-ttu-id="c99ca-114">No se usa.</span><span class="sxs-lookup"><span data-stu-id="c99ca-114">Not used.</span></span>|  
|`INTERCEPT_ALL`|<span data-ttu-id="c99ca-115">Se puede interceptar todo el código.</span><span class="sxs-lookup"><span data-stu-id="c99ca-115">All code can be intercepted.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c99ca-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c99ca-116">Remarks</span></span>  

 <span data-ttu-id="c99ca-117">Use el método [ICorDebugStepper:: setinterceptmask (](icordebugstepper-setinterceptmask-method.md) para establecer los tipos de código que se pueden interceptar.</span><span class="sxs-lookup"><span data-stu-id="c99ca-117">Use the [ICorDebugStepper::SetInterceptMask](icordebugstepper-setinterceptmask-method.md) method to establish the types of code that can be intercepted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c99ca-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c99ca-118">Requirements</span></span>  

 <span data-ttu-id="c99ca-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c99ca-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c99ca-120">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c99ca-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c99ca-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c99ca-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c99ca-122">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c99ca-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c99ca-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="c99ca-123">See also</span></span>

- [<span data-ttu-id="c99ca-124">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="c99ca-124">Debugging Enumerations</span></span>](debugging-enumerations.md)
