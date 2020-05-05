---
title: CorDebugExceptionObjectStackFrame (Estructura)
ms.date: 03/30/2017
api_name:
- CorDebugExceptionObjectStackFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugExceptionObjectStackFrame
helpviewer_keywords:
- CorDebugExceptionObjectStackFrame structure [.NET Framework debugging]
ms.assetid: 542cdd81-5ae7-4361-b0ef-1ae4775df258
topic_type:
- apiref
ms.openlocfilehash: 7eccaf984b187e463195bb3804f87bbb2c7ad47b
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795929"
---
# <a name="cordebugexceptionobjectstackframe-structure"></a><span data-ttu-id="a1f22-102">CorDebugExceptionObjectStackFrame (Estructura)</span><span class="sxs-lookup"><span data-stu-id="a1f22-102">CorDebugExceptionObjectStackFrame Structure</span></span>
<span data-ttu-id="a1f22-103">Representa información del marco de pila de un objeto de excepción.</span><span class="sxs-lookup"><span data-stu-id="a1f22-103">Represents stack frame information from an exception object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1f22-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a1f22-104">Syntax</span></span>  
  
```cpp  
typedef struct CorDebugExceptionObjectStackFrame {  
    ICorDebugModule* pModule;  
    CORDB_ADDRESS ip;  
    mdMethodDef methodDef;  
    BOOL isLastForeignExceptionFrame;  
} CorDebugExceptionObjectStackFrame;  
```  
  
## <a name="members"></a><span data-ttu-id="a1f22-105">Members</span><span class="sxs-lookup"><span data-stu-id="a1f22-105">Members</span></span>  
  
|<span data-ttu-id="a1f22-106">Member</span><span class="sxs-lookup"><span data-stu-id="a1f22-106">Member</span></span>|<span data-ttu-id="a1f22-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="a1f22-107">Description</span></span>|  
|------------|-----------------|  
|`pModule`|<span data-ttu-id="a1f22-108">Puntero al objeto ICorDebugModule para el marco actual.</span><span class="sxs-lookup"><span data-stu-id="a1f22-108">A pointer to the ICorDebugModule object for the current frame.</span></span>|  
|`ip`|<span data-ttu-id="a1f22-109">El valor del puntero de instrucción (EIP/RIP) para el marco actual.</span><span class="sxs-lookup"><span data-stu-id="a1f22-109">The value of the instruction pointer (EIP/RIP) for the current frame.</span></span>|  
|`methodDef`|<span data-ttu-id="a1f22-110">El token del método para el marco actual.</span><span class="sxs-lookup"><span data-stu-id="a1f22-110">The method token for the current frame.</span></span>|  
|`isLastForeignExceptionFrame`|<span data-ttu-id="a1f22-111">Valor que indica si el marco es el último fotograma en una excepción externa.</span><span class="sxs-lookup"><span data-stu-id="a1f22-111">A value that indicates whether the frame is the last frame in a foreign exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a1f22-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a1f22-112">Remarks</span></span>  
 <span data-ttu-id="a1f22-113">El llamador debe liberar el puntero al objeto ICorDebugModule una vez que ya no esté en uso.</span><span class="sxs-lookup"><span data-stu-id="a1f22-113">The caller must release the pointer to the ICorDebugModule object once it is no longer in use.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1f22-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a1f22-114">Requirements</span></span>  
 <span data-ttu-id="a1f22-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1f22-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1f22-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a1f22-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a1f22-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a1f22-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a1f22-118">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1f22-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1f22-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="a1f22-119">See also</span></span>

- [<span data-ttu-id="a1f22-120">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="a1f22-120">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="a1f22-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="a1f22-121">Debugging</span></span>](index.md)
