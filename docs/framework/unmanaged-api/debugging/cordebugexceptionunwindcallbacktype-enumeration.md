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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59155628"
---
# <a name="cordebugexceptionunwindcallbacktype-enumeration"></a><span data-ttu-id="02353-102">CorDebugExceptionUnwindCallbackType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="02353-102">CorDebugExceptionUnwindCallbackType Enumeration</span></span>
<span data-ttu-id="02353-103">Indica el evento que la devolución de llamada señala durante la fase de desenredo.</span><span class="sxs-lookup"><span data-stu-id="02353-103">Indicates the event that is being signaled by the callback during the unwind phase.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02353-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="02353-104">Syntax</span></span>  
  
```  
typedef enum CorDebugExceptionUnwindCallbackType {  
    DEBUG_EXCEPTION_UNWIND_BEGIN = 1,  
    DEBUG_EXCEPTION_INTERCEPTED  = 2  
} CorDebugExceptionUnwindCallbackType;  
```  
  
## <a name="members"></a><span data-ttu-id="02353-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="02353-105">Members</span></span>  
  
|<span data-ttu-id="02353-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="02353-106">Member</span></span>|<span data-ttu-id="02353-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="02353-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_UNWIND_BEGIN`|<span data-ttu-id="02353-108">El principio del proceso de desenredo.</span><span class="sxs-lookup"><span data-stu-id="02353-108">The beginning of the unwind process.</span></span>|  
|`DEBUG_EXCEPTION_INTERCEPTED`|<span data-ttu-id="02353-109">Se interceptó la excepción.</span><span class="sxs-lookup"><span data-stu-id="02353-109">The exception was intercepted.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="02353-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="02353-110">Requirements</span></span>  
 <span data-ttu-id="02353-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="02353-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02353-112">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="02353-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="02353-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="02353-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="02353-114">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="02353-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="02353-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="02353-115">See also</span></span>

- [<span data-ttu-id="02353-116">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="02353-116">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
