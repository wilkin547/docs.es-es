---
description: 'Más información sobre: enumeración Cordebugexceptioncallbacktype ('
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
ms.openlocfilehash: 41b9cdf707de017703ee3756b3d04a38163bb03b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801688"
---
# <a name="cordebugexceptioncallbacktype-enumeration"></a><span data-ttu-id="7d933-103">CorDebugExceptionCallbackType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="7d933-103">CorDebugExceptionCallbackType Enumeration</span></span>

<span data-ttu-id="7d933-104">Indica el tipo de devolución de llamada que se realiza desde un evento [ICorDebugManagedCallback2:: Exception](icordebugmanagedcallback2-exception-method.md) .</span><span class="sxs-lookup"><span data-stu-id="7d933-104">Indicates the type of callback that is made from an [ICorDebugManagedCallback2::Exception](icordebugmanagedcallback2-exception-method.md) event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d933-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7d933-105">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugExceptionCallbackType {  
    DEBUG_EXCEPTION_FIRST_CHANCE         = 1,  
    DEBUG_EXCEPTION_USER_FIRST_CHANCE    = 2,  
    DEBUG_EXCEPTION_CATCH_HANDLER_FOUND  = 3,  
    DEBUG_EXCEPTION_UNHANDLED            = 4  
} CorDebugExceptionCallbackType;  
```  
  
## <a name="members"></a><span data-ttu-id="7d933-106">Members</span><span class="sxs-lookup"><span data-stu-id="7d933-106">Members</span></span>  
  
|<span data-ttu-id="7d933-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="7d933-107">Member</span></span>|<span data-ttu-id="7d933-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="7d933-108">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_FIRST_CHANCE`|<span data-ttu-id="7d933-109">Se ha producido una excepción.</span><span class="sxs-lookup"><span data-stu-id="7d933-109">An exception was thrown.</span></span>|  
|`DEBUG_EXCEPTION_USER_FIRST_CHANCE`|<span data-ttu-id="7d933-110">El proceso Windup de la excepción entró en el código de usuario.</span><span class="sxs-lookup"><span data-stu-id="7d933-110">The exception windup process entered user code.</span></span>|  
|`DEBUG_EXCEPTION_CATCH_HANDLER_FOUND`|<span data-ttu-id="7d933-111">El proceso Windup de excepción encontró un `catch` bloque en el código de usuario.</span><span class="sxs-lookup"><span data-stu-id="7d933-111">The exception windup process found a `catch` block in user code.</span></span>|  
|`DEBUG_EXCEPTION_UNHANDLED`|<span data-ttu-id="7d933-112">No se controló la excepción.</span><span class="sxs-lookup"><span data-stu-id="7d933-112">The exception was not handled.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7d933-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7d933-113">Requirements</span></span>  

 <span data-ttu-id="7d933-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7d933-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d933-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7d933-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7d933-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7d933-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7d933-117">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d933-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d933-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="7d933-118">See also</span></span>

- [<span data-ttu-id="7d933-119">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="7d933-119">Debugging Enumerations</span></span>](debugging-enumerations.md)
