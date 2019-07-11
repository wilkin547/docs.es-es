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
ms.openlocfilehash: e959ce7a77ad6ceb7f2fc848193cbd9fff028279
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739618"
---
# <a name="cordebugsetcontextflag-enumeration"></a><span data-ttu-id="2b7b9-102">CorDebugSetContextFlag (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="2b7b9-102">CorDebugSetContextFlag Enumeration</span></span>
<span data-ttu-id="2b7b9-103">Indica si el contexto procede del marco activo (u hoja) en la pila o si se ha calculado mediante desenredo de otro marco.</span><span class="sxs-lookup"><span data-stu-id="2b7b9-103">Indicates whether the context is from the active (or leaf) frame on the stack or has been computed by unwinding from another frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b7b9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2b7b9-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugSetContextFlag  
{  
   SET_CONTEXT_FLAG_ACTIVE_FRAME = 1  
   SET_CONTEXT_FLAG_UNWIND_FRAME = 2  
}  CorDebugSetContextFlag;  
```  
  
## <a name="members"></a><span data-ttu-id="2b7b9-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="2b7b9-105">Members</span></span>  
  
|<span data-ttu-id="2b7b9-106">Member</span><span class="sxs-lookup"><span data-stu-id="2b7b9-106">Member</span></span>|<span data-ttu-id="2b7b9-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="2b7b9-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="2b7b9-108">SET_CONTEXT_FLAG_ACTIVE_FRAME</span><span class="sxs-lookup"><span data-stu-id="2b7b9-108">SET_CONTEXT_FLAG_ACTIVE_FRAME</span></span>|<span data-ttu-id="2b7b9-109">El contexto es el contexto del subproceso activo.</span><span class="sxs-lookup"><span data-stu-id="2b7b9-109">The context is the thread’s active context.</span></span>|  
|<span data-ttu-id="2b7b9-110">SET_CONTEXT_FLAG_UNWIND_FRAME</span><span class="sxs-lookup"><span data-stu-id="2b7b9-110">SET_CONTEXT_FLAG_UNWIND_FRAME</span></span>|<span data-ttu-id="2b7b9-111">El contexto se ha calculado mediante desenredo de otro marco.</span><span class="sxs-lookup"><span data-stu-id="2b7b9-111">The context has been computed by unwinding from another frame.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2b7b9-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2b7b9-112">Remarks</span></span>  
 <span data-ttu-id="2b7b9-113">`CorDebugSetContextFlag` Proporciona valores que se usan por el [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-setcontext-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="2b7b9-113">`CorDebugSetContextFlag` provides values that are used by the [ICorDebugStackWalk::SetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-setcontext-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b7b9-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2b7b9-114">Requirements</span></span>  
 <span data-ttu-id="2b7b9-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2b7b9-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b7b9-116">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2b7b9-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2b7b9-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2b7b9-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2b7b9-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b7b9-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b7b9-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="2b7b9-119">See also</span></span>

- [<span data-ttu-id="2b7b9-120">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="2b7b9-120">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
- [<span data-ttu-id="2b7b9-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="2b7b9-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
