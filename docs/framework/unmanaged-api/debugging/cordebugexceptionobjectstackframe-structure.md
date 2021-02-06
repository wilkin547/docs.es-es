---
description: 'Más información acerca de: estructura Cordebugexceptionobjectstackframe ('
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
ms.openlocfilehash: abeb5a9f6385c494745a34c6f37d6fbc1376ad7b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99662161"
---
# <a name="cordebugexceptionobjectstackframe-structure"></a><span data-ttu-id="6eb5b-103">CorDebugExceptionObjectStackFrame (Estructura)</span><span class="sxs-lookup"><span data-stu-id="6eb5b-103">CorDebugExceptionObjectStackFrame Structure</span></span>

<span data-ttu-id="6eb5b-104">Representa información del marco de pila de un objeto de excepción.</span><span class="sxs-lookup"><span data-stu-id="6eb5b-104">Represents stack frame information from an exception object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6eb5b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6eb5b-105">Syntax</span></span>  
  
```cpp  
typedef struct CorDebugExceptionObjectStackFrame {  
    ICorDebugModule* pModule;  
    CORDB_ADDRESS ip;  
    mdMethodDef methodDef;  
    BOOL isLastForeignExceptionFrame;  
} CorDebugExceptionObjectStackFrame;  
```  
  
## <a name="members"></a><span data-ttu-id="6eb5b-106">Members</span><span class="sxs-lookup"><span data-stu-id="6eb5b-106">Members</span></span>  
  
|<span data-ttu-id="6eb5b-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="6eb5b-107">Member</span></span>|<span data-ttu-id="6eb5b-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="6eb5b-108">Description</span></span>|  
|------------|-----------------|  
|`pModule`|<span data-ttu-id="6eb5b-109">Puntero al objeto ICorDebugModule para el marco actual.</span><span class="sxs-lookup"><span data-stu-id="6eb5b-109">A pointer to the ICorDebugModule object for the current frame.</span></span>|  
|`ip`|<span data-ttu-id="6eb5b-110">El valor del puntero de instrucción (EIP/RIP) para el marco actual.</span><span class="sxs-lookup"><span data-stu-id="6eb5b-110">The value of the instruction pointer (EIP/RIP) for the current frame.</span></span>|  
|`methodDef`|<span data-ttu-id="6eb5b-111">El token del método para el marco actual.</span><span class="sxs-lookup"><span data-stu-id="6eb5b-111">The method token for the current frame.</span></span>|  
|`isLastForeignExceptionFrame`|<span data-ttu-id="6eb5b-112">Valor que indica si el marco es el último fotograma en una excepción externa.</span><span class="sxs-lookup"><span data-stu-id="6eb5b-112">A value that indicates whether the frame is the last frame in a foreign exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6eb5b-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6eb5b-113">Remarks</span></span>  

 <span data-ttu-id="6eb5b-114">El llamador debe liberar el puntero al objeto ICorDebugModule una vez que ya no esté en uso.</span><span class="sxs-lookup"><span data-stu-id="6eb5b-114">The caller must release the pointer to the ICorDebugModule object once it is no longer in use.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6eb5b-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6eb5b-115">Requirements</span></span>  

 <span data-ttu-id="6eb5b-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6eb5b-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6eb5b-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6eb5b-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6eb5b-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6eb5b-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6eb5b-119">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6eb5b-119">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6eb5b-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="6eb5b-120">See also</span></span>

- [<span data-ttu-id="6eb5b-121">Estructuras de depuración</span><span class="sxs-lookup"><span data-stu-id="6eb5b-121">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="6eb5b-122">Depuración</span><span class="sxs-lookup"><span data-stu-id="6eb5b-122">Debugging</span></span>](index.md)
