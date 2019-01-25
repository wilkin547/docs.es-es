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
ms.openlocfilehash: a45929c3eef5e9127e89dd88346c6207f3f1bc65
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54559503"
---
# <a name="cordebugdebugeventkind-enumeration"></a><span data-ttu-id="ce4f9-102">Enumeración CorDebugDebugEventKind</span><span class="sxs-lookup"><span data-stu-id="ce4f9-102">CorDebugDebugEventKind Enumeration</span></span>
<span data-ttu-id="ce4f9-103">Indica el tipo de evento cuya información se descodifica mediante la [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="ce4f9-103">Indicates the type of event whose information is decoded by the [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce4f9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ce4f9-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="ce4f9-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="ce4f9-105">Members</span></span>  
  
|<span data-ttu-id="ce4f9-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="ce4f9-106">Member</span></span>|<span data-ttu-id="ce4f9-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="ce4f9-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EVENT_KIND_MODULE_LOADED`|<span data-ttu-id="ce4f9-108">Evento load del módulo.</span><span class="sxs-lookup"><span data-stu-id="ce4f9-108">A module load event.</span></span>|  
|`DEBUG_EVENT_KIND_MODULE_UNLOADED`|<span data-ttu-id="ce4f9-109">Evento unload del módulo.</span><span class="sxs-lookup"><span data-stu-id="ce4f9-109">A module unload event.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_FIRST_CHANCE`|<span data-ttu-id="ce4f9-110">Primera excepción.</span><span class="sxs-lookup"><span data-stu-id="ce4f9-110">A first-chance exception.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_USER_FIRST_CHANCE`|<span data-ttu-id="ce4f9-111">Primera excepción de usuario.</span><span class="sxs-lookup"><span data-stu-id="ce4f9-111">A first-chance user exception.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_CATCH_HANDLER_FOUND`|<span data-ttu-id="ce4f9-112">Excepción para la que existe un controlador `catch`.</span><span class="sxs-lookup"><span data-stu-id="ce4f9-112">An exception for which a `catch` handler exists.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_UNHANDLED`|<span data-ttu-id="ce4f9-113">Excepción sin controlar.</span><span class="sxs-lookup"><span data-stu-id="ce4f9-113">An unhandled exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ce4f9-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ce4f9-114">Remarks</span></span>  
 <span data-ttu-id="ce4f9-115">Un miembro de la `CorDebugDebugEventKind` enumeración se devuelve mediante una llamada a la [icordebugdebugevent:: Geteventkind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="ce4f9-115">A member of the `CorDebugDebugEventKind` enumeration is returned by calling the [ICorDebugDebugEvent::GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ce4f9-116">Esta enumeración está pensada solo para su uso en escenarios de depuración .NET Native.</span><span class="sxs-lookup"><span data-stu-id="ce4f9-116">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce4f9-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ce4f9-117">Requirements</span></span>  
 <span data-ttu-id="ce4f9-118">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce4f9-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce4f9-119">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ce4f9-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ce4f9-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ce4f9-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ce4f9-121">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce4f9-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce4f9-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="ce4f9-122">See also</span></span>
- [<span data-ttu-id="ce4f9-123">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="ce4f9-123">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
