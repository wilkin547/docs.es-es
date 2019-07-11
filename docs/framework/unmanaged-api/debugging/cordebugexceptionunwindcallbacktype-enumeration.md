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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ef3f1d5e78efe37070bb2bdd6d2834178947af7b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740086"
---
# <a name="cordebugexceptionunwindcallbacktype-enumeration"></a><span data-ttu-id="93327-102">CorDebugExceptionUnwindCallbackType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="93327-102">CorDebugExceptionUnwindCallbackType Enumeration</span></span>
<span data-ttu-id="93327-103">Indica el evento que la devolución de llamada señala durante la fase de desenredo.</span><span class="sxs-lookup"><span data-stu-id="93327-103">Indicates the event that is being signaled by the callback during the unwind phase.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93327-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="93327-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugExceptionUnwindCallbackType {  
    DEBUG_EXCEPTION_UNWIND_BEGIN = 1,  
    DEBUG_EXCEPTION_INTERCEPTED  = 2  
} CorDebugExceptionUnwindCallbackType;  
```  
  
## <a name="members"></a><span data-ttu-id="93327-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="93327-105">Members</span></span>  
  
|<span data-ttu-id="93327-106">Member</span><span class="sxs-lookup"><span data-stu-id="93327-106">Member</span></span>|<span data-ttu-id="93327-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="93327-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_UNWIND_BEGIN`|<span data-ttu-id="93327-108">El principio del proceso de desenredo.</span><span class="sxs-lookup"><span data-stu-id="93327-108">The beginning of the unwind process.</span></span>|  
|`DEBUG_EXCEPTION_INTERCEPTED`|<span data-ttu-id="93327-109">Se interceptó la excepción.</span><span class="sxs-lookup"><span data-stu-id="93327-109">The exception was intercepted.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="93327-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="93327-110">Requirements</span></span>  
 <span data-ttu-id="93327-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="93327-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93327-112">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="93327-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="93327-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="93327-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="93327-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93327-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93327-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="93327-115">See also</span></span>

- [<span data-ttu-id="93327-116">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="93327-116">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
