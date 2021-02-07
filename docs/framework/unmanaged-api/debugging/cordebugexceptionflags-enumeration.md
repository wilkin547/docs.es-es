---
description: 'Más información sobre: enumeración Cordebugexceptionflags ('
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
ms.openlocfilehash: c0036c2674f3202623da1a8fdeea14165a2a6e62
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99747054"
---
# <a name="cordebugexceptionflags-enumeration"></a><span data-ttu-id="e7192-103">CorDebugExceptionFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="e7192-103">CorDebugExceptionFlags Enumeration</span></span>

<span data-ttu-id="e7192-104">Proporciona información adicional sobre una excepción.</span><span class="sxs-lookup"><span data-stu-id="e7192-104">Provides additional information about an exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7192-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e7192-105">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugExceptionFlags {  
    DEBUG_EXCEPTION_NONE = 0,  
    DEBUG_EXCEPTION_CAN_BE_INTERCEPTED = 0x0001  
} CorDebugExceptionFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="e7192-106">Members</span><span class="sxs-lookup"><span data-stu-id="e7192-106">Members</span></span>  
  
|<span data-ttu-id="e7192-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="e7192-107">Member</span></span>|<span data-ttu-id="e7192-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="e7192-108">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_NONE`|<span data-ttu-id="e7192-109">No hay ninguna excepción.</span><span class="sxs-lookup"><span data-stu-id="e7192-109">There is no exception.</span></span>|  
|`DEBUG_EXCEPTION_CAN_BE_INTERCEPTED`|<span data-ttu-id="e7192-110">La excepción se puede interceptar.</span><span class="sxs-lookup"><span data-stu-id="e7192-110">The exception is interceptable.</span></span><br /><br /> <span data-ttu-id="e7192-111">Sin embargo, la temporización de la excepción podría hacer que el depurador no la intercepte.</span><span class="sxs-lookup"><span data-stu-id="e7192-111">The timing of the exception may still be such that the debugger cannot intercept it.</span></span> <span data-ttu-id="e7192-112">Por ejemplo, si no hay ningún código administrado debajo de la devolución de llamada actual o el evento de excepción se produjo por una asociación Just-In-Time (JIT), la excepción no se puede interceptar.</span><span class="sxs-lookup"><span data-stu-id="e7192-112">For example, if there is no managed code below the current callback or the exception event resulted from a just-in-time (JIT) attachment, the exception cannot be intercepted.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e7192-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e7192-113">Remarks</span></span>  

 <span data-ttu-id="e7192-114">Se pueden agregar nuevos valores a esta enumeración en versiones posteriores, por lo que debe preparar el código que usa `CorDebugExceptionFlags` para valores no esperados.</span><span class="sxs-lookup"><span data-stu-id="e7192-114">New values may be added to this enumeration in later versions, so you should prepare code that uses `CorDebugExceptionFlags` for unexpected values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7192-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e7192-115">Requirements</span></span>  

 <span data-ttu-id="e7192-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7192-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7192-117">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e7192-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e7192-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e7192-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e7192-119">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7192-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7192-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="e7192-120">See also</span></span>

- [<span data-ttu-id="e7192-121">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="e7192-121">Debugging Enumerations</span></span>](debugging-enumerations.md)
