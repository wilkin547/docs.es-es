---
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
ms.openlocfilehash: 078dfefc70704eaadb9cf3c06cfe58f276f7dfce
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726035"
---
# <a name="cordebugsetcontextflag-enumeration"></a><span data-ttu-id="c29c4-102">CorDebugSetContextFlag (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="c29c4-102">CorDebugSetContextFlag Enumeration</span></span>

<span data-ttu-id="c29c4-103">Indica si el contexto procede del marco activo (u hoja) en la pila o si se ha calculado mediante desenredo de otro marco.</span><span class="sxs-lookup"><span data-stu-id="c29c4-103">Indicates whether the context is from the active (or leaf) frame on the stack or has been computed by unwinding from another frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c29c4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c29c4-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugSetContextFlag  
{  
   SET_CONTEXT_FLAG_ACTIVE_FRAME = 1  
   SET_CONTEXT_FLAG_UNWIND_FRAME = 2  
}  CorDebugSetContextFlag;  
```  
  
## <a name="members"></a><span data-ttu-id="c29c4-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="c29c4-105">Members</span></span>  
  
|<span data-ttu-id="c29c4-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="c29c4-106">Member</span></span>|<span data-ttu-id="c29c4-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="c29c4-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="c29c4-108">SET_CONTEXT_FLAG_ACTIVE_FRAME</span><span class="sxs-lookup"><span data-stu-id="c29c4-108">SET_CONTEXT_FLAG_ACTIVE_FRAME</span></span>|<span data-ttu-id="c29c4-109">El contexto es el contexto activo del subproceso.</span><span class="sxs-lookup"><span data-stu-id="c29c4-109">The context is the thread’s active context.</span></span>|  
|<span data-ttu-id="c29c4-110">SET_CONTEXT_FLAG_UNWIND_FRAME</span><span class="sxs-lookup"><span data-stu-id="c29c4-110">SET_CONTEXT_FLAG_UNWIND_FRAME</span></span>|<span data-ttu-id="c29c4-111">El contexto se ha calculado desenredando de otro marco.</span><span class="sxs-lookup"><span data-stu-id="c29c4-111">The context has been computed by unwinding from another frame.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c29c4-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c29c4-112">Remarks</span></span>  

 <span data-ttu-id="c29c4-113">`CorDebugSetContextFlag` proporciona valores que usa el método [ICorDebugStackWalk:: SetContext](icordebugstackwalk-setcontext-method.md) .</span><span class="sxs-lookup"><span data-stu-id="c29c4-113">`CorDebugSetContextFlag` provides values that are used by the [ICorDebugStackWalk::SetContext](icordebugstackwalk-setcontext-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c29c4-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c29c4-114">Requirements</span></span>  

 <span data-ttu-id="c29c4-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c29c4-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c29c4-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c29c4-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c29c4-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c29c4-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c29c4-118">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c29c4-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c29c4-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c29c4-119">See also</span></span>

- [<span data-ttu-id="c29c4-120">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="c29c4-120">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="c29c4-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="c29c4-121">Debugging</span></span>](index.md)
