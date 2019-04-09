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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5a4cd4d353c22921ed3dba1dc08fe2cee7e429f8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59173087"
---
# <a name="cordebugexceptionobjectstackframe-structure"></a><span data-ttu-id="4a370-102">CorDebugExceptionObjectStackFrame (Estructura)</span><span class="sxs-lookup"><span data-stu-id="4a370-102">CorDebugExceptionObjectStackFrame Structure</span></span>
<span data-ttu-id="4a370-103">Representa información del marco de pila de un objeto de excepción.</span><span class="sxs-lookup"><span data-stu-id="4a370-103">Represents stack frame information from an exception object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a370-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4a370-104">Syntax</span></span>  
  
```  
typedef struct CorDebugExceptionObjectStackFrame {  
    ICorDebugModule* pModule;  
    CORDB_ADDRESS ip;  
    mdMethodDef methodDef;  
    BOOL isLastForeignExceptionFrame;  
} CorDebugExceptionObjectStackFrame;  
```  
  
## <a name="members"></a><span data-ttu-id="4a370-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="4a370-105">Members</span></span>  
  
|<span data-ttu-id="4a370-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="4a370-106">Member</span></span>|<span data-ttu-id="4a370-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="4a370-107">Description</span></span>|  
|------------|-----------------|  
|`pModule`|<span data-ttu-id="4a370-108">Un puntero al objeto ICorDebugModule del marco actual.</span><span class="sxs-lookup"><span data-stu-id="4a370-108">A pointer to the ICorDebugModule object for the current frame.</span></span>|  
|`ip`|<span data-ttu-id="4a370-109">El valor del puntero de instrucción (EIP/RIP) para el marco actual.</span><span class="sxs-lookup"><span data-stu-id="4a370-109">The value of the instruction pointer (EIP/RIP) for the current frame.</span></span>|  
|`methodDef`|<span data-ttu-id="4a370-110">El token de método para el marco actual.</span><span class="sxs-lookup"><span data-stu-id="4a370-110">The method token for the current frame.</span></span>|  
|`isLastForeignExceptionFrame`|<span data-ttu-id="4a370-111">Un valor que indica si el marco es el último en una excepción externa.</span><span class="sxs-lookup"><span data-stu-id="4a370-111">A value that indicates whether the frame is the last frame in a foreign exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4a370-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4a370-112">Remarks</span></span>  
 <span data-ttu-id="4a370-113">El llamador debe liberar el puntero al objeto ICorDebugModule una vez que ya no está en uso.</span><span class="sxs-lookup"><span data-stu-id="4a370-113">The caller must release the pointer to the ICorDebugModule object once it is no longer in use.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a370-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4a370-114">Requirements</span></span>  
 <span data-ttu-id="4a370-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a370-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a370-116">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4a370-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4a370-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4a370-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="4a370-118">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="4a370-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4a370-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="4a370-119">See also</span></span>

- [<span data-ttu-id="4a370-120">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="4a370-120">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="4a370-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="4a370-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
