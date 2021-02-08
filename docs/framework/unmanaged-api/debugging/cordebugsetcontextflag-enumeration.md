---
description: 'Más información sobre: enumeración CorDebugSetContextFlag ('
title: CorDebugSetContextFlag (Enumeración)
ms.date: 03/30/2017
api_name:
- CorDebugSetContextFlag
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugSetContextFlag
helpviewer_keywords:
- CorDebugSetContextFlag enumeration [.NET Framework debugging]
ms.assetid: b30280bb-fe75-44ed-8589-bcff081fae44
topic_type:
- apiref
ms.openlocfilehash: 625f24e516ff462cf3d0e628dfff6c08793807ce
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801558"
---
# <a name="cordebugsetcontextflag-enumeration"></a><span data-ttu-id="dbe3e-103">CorDebugSetContextFlag (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="dbe3e-103">CorDebugSetContextFlag Enumeration</span></span>

<span data-ttu-id="dbe3e-104">Indica si el contexto procede del marco activo (u hoja) en la pila o si se ha calculado mediante desenredo de otro marco.</span><span class="sxs-lookup"><span data-stu-id="dbe3e-104">Indicates whether the context is from the active (or leaf) frame on the stack or has been computed by unwinding from another frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbe3e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dbe3e-105">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugSetContextFlag  
{  
   SET_CONTEXT_FLAG_ACTIVE_FRAME = 1  
   SET_CONTEXT_FLAG_UNWIND_FRAME = 2  
}  CorDebugSetContextFlag;  
```  
  
## <a name="members"></a><span data-ttu-id="dbe3e-106">Members</span><span class="sxs-lookup"><span data-stu-id="dbe3e-106">Members</span></span>  
  
|<span data-ttu-id="dbe3e-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="dbe3e-107">Member</span></span>|<span data-ttu-id="dbe3e-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="dbe3e-108">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="dbe3e-109">SET_CONTEXT_FLAG_ACTIVE_FRAME</span><span class="sxs-lookup"><span data-stu-id="dbe3e-109">SET_CONTEXT_FLAG_ACTIVE_FRAME</span></span>|<span data-ttu-id="dbe3e-110">El contexto es el contexto activo del subproceso.</span><span class="sxs-lookup"><span data-stu-id="dbe3e-110">The context is the thread’s active context.</span></span>|  
|<span data-ttu-id="dbe3e-111">SET_CONTEXT_FLAG_UNWIND_FRAME</span><span class="sxs-lookup"><span data-stu-id="dbe3e-111">SET_CONTEXT_FLAG_UNWIND_FRAME</span></span>|<span data-ttu-id="dbe3e-112">El contexto se ha calculado desenredando de otro marco.</span><span class="sxs-lookup"><span data-stu-id="dbe3e-112">The context has been computed by unwinding from another frame.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dbe3e-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="dbe3e-113">Remarks</span></span>  

 <span data-ttu-id="dbe3e-114">`CorDebugSetContextFlag` proporciona valores que usa el método [ICorDebugStackWalk:: SetContext](icordebugstackwalk-setcontext-method.md) .</span><span class="sxs-lookup"><span data-stu-id="dbe3e-114">`CorDebugSetContextFlag` provides values that are used by the [ICorDebugStackWalk::SetContext](icordebugstackwalk-setcontext-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dbe3e-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dbe3e-115">Requirements</span></span>  

 <span data-ttu-id="dbe3e-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dbe3e-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dbe3e-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dbe3e-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dbe3e-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dbe3e-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dbe3e-119">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dbe3e-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbe3e-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="dbe3e-120">See also</span></span>

- [<span data-ttu-id="dbe3e-121">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="dbe3e-121">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="dbe3e-122">Depuración</span><span class="sxs-lookup"><span data-stu-id="dbe3e-122">Debugging</span></span>](index.md)
