---
description: 'Más información sobre: enumeración CorDebugExceptionUnwindCallbackType ('
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
ms.openlocfilehash: 3e12cffcdf1eb921330f658215c52501dce83eff
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99747029"
---
# <a name="cordebugexceptionunwindcallbacktype-enumeration"></a><span data-ttu-id="13e7f-103">CorDebugExceptionUnwindCallbackType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="13e7f-103">CorDebugExceptionUnwindCallbackType Enumeration</span></span>

<span data-ttu-id="13e7f-104">Indica el evento que la devolución de llamada señala durante la fase de desenredo.</span><span class="sxs-lookup"><span data-stu-id="13e7f-104">Indicates the event that is being signaled by the callback during the unwind phase.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13e7f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="13e7f-105">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugExceptionUnwindCallbackType {  
    DEBUG_EXCEPTION_UNWIND_BEGIN = 1,  
    DEBUG_EXCEPTION_INTERCEPTED  = 2  
} CorDebugExceptionUnwindCallbackType;  
```  
  
## <a name="members"></a><span data-ttu-id="13e7f-106">Members</span><span class="sxs-lookup"><span data-stu-id="13e7f-106">Members</span></span>  
  
|<span data-ttu-id="13e7f-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="13e7f-107">Member</span></span>|<span data-ttu-id="13e7f-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="13e7f-108">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_UNWIND_BEGIN`|<span data-ttu-id="13e7f-109">Inicio del proceso de desenredado.</span><span class="sxs-lookup"><span data-stu-id="13e7f-109">The beginning of the unwind process.</span></span>|  
|`DEBUG_EXCEPTION_INTERCEPTED`|<span data-ttu-id="13e7f-110">Se interceptó la excepción.</span><span class="sxs-lookup"><span data-stu-id="13e7f-110">The exception was intercepted.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="13e7f-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="13e7f-111">Requirements</span></span>  

 <span data-ttu-id="13e7f-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="13e7f-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13e7f-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="13e7f-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="13e7f-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="13e7f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="13e7f-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13e7f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13e7f-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="13e7f-116">See also</span></span>

- [<span data-ttu-id="13e7f-117">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="13e7f-117">Debugging Enumerations</span></span>](debugging-enumerations.md)
