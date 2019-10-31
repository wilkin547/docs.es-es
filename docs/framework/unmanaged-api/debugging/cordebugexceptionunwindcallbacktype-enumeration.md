---
title: CorDebugExceptionUnwindCallbackType (Enumeración)
ms.date: 03/30/2017
api_name:
- CorDebugExceptionUnwindCallbackType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugExceptionUnwindCallbackType
helpviewer_keywords:
- CorDebugExceptionUnwindCallbackType enumeration [.NET Framework debugging]
ms.assetid: 783dce92-8a98-43db-8f78-888d943dd5b2
topic_type:
- apiref
ms.openlocfilehash: 5004cd293b64436c41caef1c7393d2229d1a6ccf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73098477"
---
# <a name="cordebugexceptionunwindcallbacktype-enumeration"></a><span data-ttu-id="4e3ed-102">CorDebugExceptionUnwindCallbackType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="4e3ed-102">CorDebugExceptionUnwindCallbackType Enumeration</span></span>
<span data-ttu-id="4e3ed-103">Indica el evento que la devolución de llamada señala durante la fase de desenredo.</span><span class="sxs-lookup"><span data-stu-id="4e3ed-103">Indicates the event that is being signaled by the callback during the unwind phase.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e3ed-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4e3ed-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugExceptionUnwindCallbackType {  
    DEBUG_EXCEPTION_UNWIND_BEGIN = 1,  
    DEBUG_EXCEPTION_INTERCEPTED  = 2  
} CorDebugExceptionUnwindCallbackType;  
```  
  
## <a name="members"></a><span data-ttu-id="4e3ed-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="4e3ed-105">Members</span></span>  
  
|<span data-ttu-id="4e3ed-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="4e3ed-106">Member</span></span>|<span data-ttu-id="4e3ed-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="4e3ed-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_UNWIND_BEGIN`|<span data-ttu-id="4e3ed-108">Inicio del proceso de desenredado.</span><span class="sxs-lookup"><span data-stu-id="4e3ed-108">The beginning of the unwind process.</span></span>|  
|`DEBUG_EXCEPTION_INTERCEPTED`|<span data-ttu-id="4e3ed-109">Se interceptó la excepción.</span><span class="sxs-lookup"><span data-stu-id="4e3ed-109">The exception was intercepted.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4e3ed-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4e3ed-110">Requirements</span></span>  
 <span data-ttu-id="4e3ed-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e3ed-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e3ed-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4e3ed-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4e3ed-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4e3ed-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4e3ed-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e3ed-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e3ed-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="4e3ed-115">See also</span></span>

- [<span data-ttu-id="4e3ed-116">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="4e3ed-116">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
