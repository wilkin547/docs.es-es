---
title: CorDebugExceptionFlags (Enumeración)
ms.date: 03/30/2017
api_name:
- CorDebugExceptionFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugExceptionFlags
helpviewer_keywords:
- CorDebugExceptionFlags enumeration [.NET Framework debugging]
ms.assetid: b22687a8-e9cf-4e65-a1b0-f92a81bc524e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2c7b9b25673685dde8b75702c80f525515917ae1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59078712"
---
# <a name="cordebugexceptionflags-enumeration"></a><span data-ttu-id="8c41b-102">CorDebugExceptionFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="8c41b-102">CorDebugExceptionFlags Enumeration</span></span>
<span data-ttu-id="8c41b-103">Proporciona información adicional sobre una excepción.</span><span class="sxs-lookup"><span data-stu-id="8c41b-103">Provides additional information about an exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c41b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8c41b-104">Syntax</span></span>  
  
```  
typedef enum CorDebugExceptionFlags {  
    DEBUG_EXCEPTION_NONE = 0,  
    DEBUG_EXCEPTION_CAN_BE_INTERCEPTED = 0x0001  
} CorDebugExceptionFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="8c41b-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="8c41b-105">Members</span></span>  
  
|<span data-ttu-id="8c41b-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="8c41b-106">Member</span></span>|<span data-ttu-id="8c41b-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="8c41b-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_NONE`|<span data-ttu-id="8c41b-108">No hay ninguna excepción.</span><span class="sxs-lookup"><span data-stu-id="8c41b-108">There is no exception.</span></span>|  
|`DEBUG_EXCEPTION_CAN_BE_INTERCEPTED`|<span data-ttu-id="8c41b-109">La excepción se puede interceptar.</span><span class="sxs-lookup"><span data-stu-id="8c41b-109">The exception is interceptable.</span></span><br /><br /> <span data-ttu-id="8c41b-110">Sin embargo, la temporización de la excepción podría hacer que el depurador no la intercepte.</span><span class="sxs-lookup"><span data-stu-id="8c41b-110">The timing of the exception may still be such that the debugger cannot intercept it.</span></span> <span data-ttu-id="8c41b-111">Por ejemplo, si no hay ningún código administrado debajo de la devolución de llamada actual o el evento de excepción se produjo por una asociación Just-In-Time (JIT), la excepción no se puede interceptar.</span><span class="sxs-lookup"><span data-stu-id="8c41b-111">For example, if there is no managed code below the current callback or the exception event resulted from a just-in-time (JIT) attachment, the exception cannot be intercepted.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8c41b-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8c41b-112">Remarks</span></span>  
 <span data-ttu-id="8c41b-113">Se pueden agregar nuevos valores a esta enumeración en versiones posteriores, por lo que debe preparar el código que usa `CorDebugExceptionFlags` para valores no esperados.</span><span class="sxs-lookup"><span data-stu-id="8c41b-113">New values may be added to this enumeration in later versions, so you should prepare code that uses `CorDebugExceptionFlags` for unexpected values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c41b-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8c41b-114">Requirements</span></span>  
 <span data-ttu-id="8c41b-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c41b-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c41b-116">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8c41b-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8c41b-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8c41b-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8c41b-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c41b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c41b-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="8c41b-119">See also</span></span>

- [<span data-ttu-id="8c41b-120">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="8c41b-120">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
