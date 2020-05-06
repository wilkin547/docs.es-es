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
ms.openlocfilehash: 4d2be9960f8935b754791a8badd4ea98b5d54912
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795916"
---
# <a name="cordebugexceptionunwindcallbacktype-enumeration"></a><span data-ttu-id="fc857-102">CorDebugExceptionUnwindCallbackType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="fc857-102">CorDebugExceptionUnwindCallbackType Enumeration</span></span>
<span data-ttu-id="fc857-103">Indica el evento que la devolución de llamada señala durante la fase de desenredo.</span><span class="sxs-lookup"><span data-stu-id="fc857-103">Indicates the event that is being signaled by the callback during the unwind phase.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc857-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fc857-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugExceptionUnwindCallbackType {  
    DEBUG_EXCEPTION_UNWIND_BEGIN = 1,  
    DEBUG_EXCEPTION_INTERCEPTED  = 2  
} CorDebugExceptionUnwindCallbackType;  
```  
  
## <a name="members"></a><span data-ttu-id="fc857-105">Members</span><span class="sxs-lookup"><span data-stu-id="fc857-105">Members</span></span>  
  
|<span data-ttu-id="fc857-106">Member</span><span class="sxs-lookup"><span data-stu-id="fc857-106">Member</span></span>|<span data-ttu-id="fc857-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="fc857-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_UNWIND_BEGIN`|<span data-ttu-id="fc857-108">Inicio del proceso de desenredado.</span><span class="sxs-lookup"><span data-stu-id="fc857-108">The beginning of the unwind process.</span></span>|  
|`DEBUG_EXCEPTION_INTERCEPTED`|<span data-ttu-id="fc857-109">Se interceptó la excepción.</span><span class="sxs-lookup"><span data-stu-id="fc857-109">The exception was intercepted.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fc857-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fc857-110">Requirements</span></span>  
 <span data-ttu-id="fc857-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc857-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc857-112">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fc857-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fc857-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fc857-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fc857-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc857-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc857-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="fc857-115">See also</span></span>

- [<span data-ttu-id="fc857-116">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="fc857-116">Debugging Enumerations</span></span>](debugging-enumerations.md)
