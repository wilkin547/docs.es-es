---
title: CorDebugExceptionCallbackType (Enumeración)
ms.date: 03/30/2017
api_name:
- CorDebugExceptionCallbackType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugExceptionCallbackType
helpviewer_keywords:
- CorDebugExceptionCallbackType enumeration [.NET Framework debugging]
ms.assetid: 4d946ad4-3c19-42cb-bec9-8633325ba769
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 91b09be04499396a2229962fd592f29cb8bc8d04
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59155563"
---
# <a name="cordebugexceptioncallbacktype-enumeration"></a><span data-ttu-id="1ce1a-102">CorDebugExceptionCallbackType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="1ce1a-102">CorDebugExceptionCallbackType Enumeration</span></span>
<span data-ttu-id="1ce1a-103">Indica el tipo de devolución de llamada que se realiza desde un [ICorDebugManagedCallback2:: Exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exception-method.md) eventos.</span><span class="sxs-lookup"><span data-stu-id="1ce1a-103">Indicates the type of callback that is made from an [ICorDebugManagedCallback2::Exception](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exception-method.md) event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ce1a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1ce1a-104">Syntax</span></span>  
  
```  
typedef enum CorDebugExceptionCallbackType {  
    DEBUG_EXCEPTION_FIRST_CHANCE         = 1,  
    DEBUG_EXCEPTION_USER_FIRST_CHANCE    = 2,  
    DEBUG_EXCEPTION_CATCH_HANDLER_FOUND  = 3,  
    DEBUG_EXCEPTION_UNHANDLED            = 4  
} CorDebugExceptionCallbackType;  
```  
  
## <a name="members"></a><span data-ttu-id="1ce1a-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="1ce1a-105">Members</span></span>  
  
|<span data-ttu-id="1ce1a-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="1ce1a-106">Member</span></span>|<span data-ttu-id="1ce1a-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="1ce1a-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_FIRST_CHANCE`|<span data-ttu-id="1ce1a-108">Se produjo una excepción.</span><span class="sxs-lookup"><span data-stu-id="1ce1a-108">An exception was thrown.</span></span>|  
|`DEBUG_EXCEPTION_USER_FIRST_CHANCE`|<span data-ttu-id="1ce1a-109">El proceso de conclusión de la excepción escribió el código de usuario.</span><span class="sxs-lookup"><span data-stu-id="1ce1a-109">The exception windup process entered user code.</span></span>|  
|`DEBUG_EXCEPTION_CATCH_HANDLER_FOUND`|<span data-ttu-id="1ce1a-110">El proceso de conclusión de la excepción se encuentra un `catch` bloque de código de usuario.</span><span class="sxs-lookup"><span data-stu-id="1ce1a-110">The exception windup process found a `catch` block in user code.</span></span>|  
|`DEBUG_EXCEPTION_UNHANDLED`|<span data-ttu-id="1ce1a-111">No se controló la excepción.</span><span class="sxs-lookup"><span data-stu-id="1ce1a-111">The exception was not handled.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1ce1a-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1ce1a-112">Requirements</span></span>  
 <span data-ttu-id="1ce1a-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1ce1a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ce1a-114">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1ce1a-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1ce1a-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1ce1a-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1ce1a-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ce1a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ce1a-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="1ce1a-117">See also</span></span>

- [<span data-ttu-id="1ce1a-118">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="1ce1a-118">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
