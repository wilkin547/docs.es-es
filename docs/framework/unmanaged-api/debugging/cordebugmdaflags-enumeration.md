---
title: CorDebugMDAFlags (Enumeración)
ms.date: 03/30/2017
api_name:
- CorDebugMDAFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugMDAFlags
helpviewer_keywords:
- CorDebugMDAFlags enumeration [.NET Framework debugging]
ms.assetid: 7c0c92fe-8bd2-477f-b307-aca0143732ca
topic_type:
- apiref
ms.openlocfilehash: c7af194351290ad937e40a2fc8b960c2c242629c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132792"
---
# <a name="cordebugmdaflags-enumeration"></a><span data-ttu-id="5f267-102">CorDebugMDAFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="5f267-102">CorDebugMDAFlags Enumeration</span></span>
<span data-ttu-id="5f267-103">Especifica el estado del subproceso en el que se activa el asistente para la depuración administrada (MDA).</span><span class="sxs-lookup"><span data-stu-id="5f267-103">Specifies the status of the thread on which the managed debugging assistant (MDA) is fired.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f267-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5f267-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugMDAFlags {  
    MDA_FLAG_SLIP = 0x2  
} CorDebugMDAFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="5f267-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="5f267-105">Members</span></span>  
  
|<span data-ttu-id="5f267-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="5f267-106">Member</span></span>|<span data-ttu-id="5f267-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="5f267-107">Description</span></span>|  
|------------|-----------------|  
|`MDA_FLAG_SLIP`|<span data-ttu-id="5f267-108">El subproceso en el que se ha desencadenado el MDA se ha retrasado desde que se activó el MDA.</span><span class="sxs-lookup"><span data-stu-id="5f267-108">The thread on which the MDA was fired has slipped since the MDA was fired.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5f267-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5f267-109">Remarks</span></span>  
 <span data-ttu-id="5f267-110">Cuando la pila de llamadas ya no describe dónde se generó originalmente el MDA, se considera que el subproceso se ha *retrasado*.</span><span class="sxs-lookup"><span data-stu-id="5f267-110">When the call stack no longer describes where the MDA was originally raised, the thread is considered to have *slipped*.</span></span> <span data-ttu-id="5f267-111">Se trata de una circunstancia inusual realizada por la ejecución del subproceso de una operación no válida al salir.</span><span class="sxs-lookup"><span data-stu-id="5f267-111">This is an unusual circumstance brought about by the thread's execution of an invalid operation upon exiting.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f267-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5f267-112">Requirements</span></span>  
 <span data-ttu-id="5f267-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f267-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f267-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5f267-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5f267-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5f267-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5f267-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f267-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f267-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="5f267-117">See also</span></span>

- [<span data-ttu-id="5f267-118">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="5f267-118">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
