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
ms.openlocfilehash: 408e72eeaa1dac83c45488d186425f30c6043280
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61786378"
---
# <a name="cordebugexceptionunwindcallbacktype-enumeration"></a><span data-ttu-id="104ce-102">CorDebugExceptionUnwindCallbackType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="104ce-102">CorDebugExceptionUnwindCallbackType Enumeration</span></span>
<span data-ttu-id="104ce-103">Indica el evento que la devolución de llamada señala durante la fase de desenredo.</span><span class="sxs-lookup"><span data-stu-id="104ce-103">Indicates the event that is being signaled by the callback during the unwind phase.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="104ce-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="104ce-104">Syntax</span></span>  
  
```  
typedef enum CorDebugExceptionUnwindCallbackType {  
    DEBUG_EXCEPTION_UNWIND_BEGIN = 1,  
    DEBUG_EXCEPTION_INTERCEPTED  = 2  
} CorDebugExceptionUnwindCallbackType;  
```  
  
## <a name="members"></a><span data-ttu-id="104ce-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="104ce-105">Members</span></span>  
  
|<span data-ttu-id="104ce-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="104ce-106">Member</span></span>|<span data-ttu-id="104ce-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="104ce-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_UNWIND_BEGIN`|<span data-ttu-id="104ce-108">El principio del proceso de desenredo.</span><span class="sxs-lookup"><span data-stu-id="104ce-108">The beginning of the unwind process.</span></span>|  
|`DEBUG_EXCEPTION_INTERCEPTED`|<span data-ttu-id="104ce-109">Se interceptó la excepción.</span><span class="sxs-lookup"><span data-stu-id="104ce-109">The exception was intercepted.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="104ce-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="104ce-110">Requirements</span></span>  
 <span data-ttu-id="104ce-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="104ce-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="104ce-112">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="104ce-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="104ce-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="104ce-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="104ce-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="104ce-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="104ce-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="104ce-115">See also</span></span>

- [<span data-ttu-id="104ce-116">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="104ce-116">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
