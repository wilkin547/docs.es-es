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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5754968511f7b2db48f60b99748f10f5d27e8d21
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61599408"
---
# <a name="cordebugsetcontextflag-enumeration"></a><span data-ttu-id="0ad09-102">CorDebugSetContextFlag (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="0ad09-102">CorDebugSetContextFlag Enumeration</span></span>
<span data-ttu-id="0ad09-103">Indica si el contexto procede del marco activo (u hoja) en la pila o si se ha calculado mediante desenredo de otro marco.</span><span class="sxs-lookup"><span data-stu-id="0ad09-103">Indicates whether the context is from the active (or leaf) frame on the stack or has been computed by unwinding from another frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ad09-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0ad09-104">Syntax</span></span>  
  
```  
typedef enum CorDebugSetContextFlag  
{  
   SET_CONTEXT_FLAG_ACTIVE_FRAME = 1  
   SET_CONTEXT_FLAG_UNWIND_FRAME = 2  
}  CorDebugSetContextFlag;  
```  
  
## <a name="members"></a><span data-ttu-id="0ad09-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="0ad09-105">Members</span></span>  
  
|<span data-ttu-id="0ad09-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="0ad09-106">Member</span></span>|<span data-ttu-id="0ad09-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="0ad09-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="0ad09-108">SET_CONTEXT_FLAG_ACTIVE_FRAME</span><span class="sxs-lookup"><span data-stu-id="0ad09-108">SET_CONTEXT_FLAG_ACTIVE_FRAME</span></span>|<span data-ttu-id="0ad09-109">El contexto es el contexto del subproceso activo.</span><span class="sxs-lookup"><span data-stu-id="0ad09-109">The context is the thread’s active context.</span></span>|  
|<span data-ttu-id="0ad09-110">SET_CONTEXT_FLAG_UNWIND_FRAME</span><span class="sxs-lookup"><span data-stu-id="0ad09-110">SET_CONTEXT_FLAG_UNWIND_FRAME</span></span>|<span data-ttu-id="0ad09-111">El contexto se ha calculado mediante desenredo de otro marco.</span><span class="sxs-lookup"><span data-stu-id="0ad09-111">The context has been computed by unwinding from another frame.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0ad09-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0ad09-112">Remarks</span></span>  
 <span data-ttu-id="0ad09-113">`CorDebugSetContextFlag` Proporciona valores que se usan por el [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-setcontext-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="0ad09-113">`CorDebugSetContextFlag` provides values that are used by the [ICorDebugStackWalk::SetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-setcontext-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ad09-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0ad09-114">Requirements</span></span>  
 <span data-ttu-id="0ad09-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ad09-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ad09-116">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0ad09-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0ad09-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0ad09-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0ad09-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ad09-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ad09-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="0ad09-119">See also</span></span>

- [<span data-ttu-id="0ad09-120">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="0ad09-120">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
- [<span data-ttu-id="0ad09-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="0ad09-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
