---
title: Enumeración CorDebugDebugEventKind
ms.date: 03/30/2017
api_name:
- CorDebugDebugEventKind
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 6075a6cd-97e6-4472-a090-0dd14860d1f3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9e5479fad3f19c219a0ca1d5d01934ce92a7162e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61609248"
---
# <a name="cordebugdebugeventkind-enumeration"></a><span data-ttu-id="b8096-102">Enumeración CorDebugDebugEventKind</span><span class="sxs-lookup"><span data-stu-id="b8096-102">CorDebugDebugEventKind Enumeration</span></span>
<span data-ttu-id="b8096-103">Indica el tipo de evento cuya información se descodifica mediante la [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="b8096-103">Indicates the type of event whose information is decoded by the [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8096-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b8096-104">Syntax</span></span>  
  
```  
typedef enum CorDebugDebugEventKind {  
    DEBUG_EVENT_KIND_MODULE_LOADED                          = 1,  
    DEBUG_EVENT_KIND_MODULE_UNLOADED                        = 2,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_FIRST_CHANCE         = 3,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_USER_FIRST_CHANCE    = 4,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_CATCH_HANDLER_FOUND  = 5,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_UNHANDLED            = 6  
} CorDebugRecordFormat;  
```  
  
## <a name="members"></a><span data-ttu-id="b8096-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="b8096-105">Members</span></span>  
  
|<span data-ttu-id="b8096-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="b8096-106">Member</span></span>|<span data-ttu-id="b8096-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="b8096-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EVENT_KIND_MODULE_LOADED`|<span data-ttu-id="b8096-108">Evento load del módulo.</span><span class="sxs-lookup"><span data-stu-id="b8096-108">A module load event.</span></span>|  
|`DEBUG_EVENT_KIND_MODULE_UNLOADED`|<span data-ttu-id="b8096-109">Evento unload del módulo.</span><span class="sxs-lookup"><span data-stu-id="b8096-109">A module unload event.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_FIRST_CHANCE`|<span data-ttu-id="b8096-110">Primera excepción.</span><span class="sxs-lookup"><span data-stu-id="b8096-110">A first-chance exception.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_USER_FIRST_CHANCE`|<span data-ttu-id="b8096-111">Primera excepción de usuario.</span><span class="sxs-lookup"><span data-stu-id="b8096-111">A first-chance user exception.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_CATCH_HANDLER_FOUND`|<span data-ttu-id="b8096-112">Excepción para la que existe un controlador `catch`.</span><span class="sxs-lookup"><span data-stu-id="b8096-112">An exception for which a `catch` handler exists.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_UNHANDLED`|<span data-ttu-id="b8096-113">Excepción sin controlar.</span><span class="sxs-lookup"><span data-stu-id="b8096-113">An unhandled exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b8096-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b8096-114">Remarks</span></span>  
 <span data-ttu-id="b8096-115">Un miembro de la `CorDebugDebugEventKind` enumeración se devuelve mediante una llamada a la [icordebugdebugevent:: Geteventkind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="b8096-115">A member of the `CorDebugDebugEventKind` enumeration is returned by calling the [ICorDebugDebugEvent::GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b8096-116">Esta enumeración está pensada solo para su uso en escenarios de depuración .NET Native.</span><span class="sxs-lookup"><span data-stu-id="b8096-116">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8096-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b8096-117">Requirements</span></span>  
 <span data-ttu-id="b8096-118">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8096-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8096-119">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b8096-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b8096-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b8096-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b8096-121">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8096-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8096-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="b8096-122">See also</span></span>

- [<span data-ttu-id="b8096-123">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="b8096-123">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
