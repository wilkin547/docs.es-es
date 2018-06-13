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
ms.openlocfilehash: 9f2f5af86e210493cd8ba0eb8afe10d22b84b18c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33408013"
---
# <a name="cordebugdebugeventkind-enumeration"></a><span data-ttu-id="9ba00-102">Enumeración CorDebugDebugEventKind</span><span class="sxs-lookup"><span data-stu-id="9ba00-102">CorDebugDebugEventKind Enumeration</span></span>
<span data-ttu-id="9ba00-103">Indica el tipo de evento cuya información se descodifica por la [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="9ba00-103">Indicates the type of event whose information is decoded by the [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ba00-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9ba00-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="9ba00-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="9ba00-105">Members</span></span>  
  
|<span data-ttu-id="9ba00-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="9ba00-106">Member</span></span>|<span data-ttu-id="9ba00-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="9ba00-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EVENT_KIND_MODULE_LOADED`|<span data-ttu-id="9ba00-108">Evento load del módulo.</span><span class="sxs-lookup"><span data-stu-id="9ba00-108">A module load event.</span></span>|  
|`DEBUG_EVENT_KIND_MODULE_UNLOADED`|<span data-ttu-id="9ba00-109">Evento unload del módulo.</span><span class="sxs-lookup"><span data-stu-id="9ba00-109">A module unload event.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_FIRST_CHANCE`|<span data-ttu-id="9ba00-110">Primera excepción.</span><span class="sxs-lookup"><span data-stu-id="9ba00-110">A first-chance exception.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_USER_FIRST_CHANCE`|<span data-ttu-id="9ba00-111">Primera excepción de usuario.</span><span class="sxs-lookup"><span data-stu-id="9ba00-111">A first-chance user exception.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_CATCH_HANDLER_FOUND`|<span data-ttu-id="9ba00-112">Excepción para la que existe un controlador `catch`.</span><span class="sxs-lookup"><span data-stu-id="9ba00-112">An exception for which a `catch` handler exists.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_UNHANDLED`|<span data-ttu-id="9ba00-113">Excepción sin controlar.</span><span class="sxs-lookup"><span data-stu-id="9ba00-113">An unhandled exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9ba00-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9ba00-114">Remarks</span></span>  
 <span data-ttu-id="9ba00-115">Un miembro de la `CorDebugDebugEventKind` enumeración devuelto por una llamada a la [icordebugdebugevent::](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) (método).</span><span class="sxs-lookup"><span data-stu-id="9ba00-115">A member of the `CorDebugDebugEventKind` enumeration is returned by calling the [ICorDebugDebugEvent::GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9ba00-116">Esta enumeración está pensada solo para su uso en escenarios de depuración .NET Native.</span><span class="sxs-lookup"><span data-stu-id="9ba00-116">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ba00-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9ba00-117">Requirements</span></span>  
 <span data-ttu-id="9ba00-118">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9ba00-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ba00-119">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9ba00-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9ba00-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9ba00-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9ba00-121">**Versiones de .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ba00-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ba00-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="9ba00-122">See Also</span></span>  
 [<span data-ttu-id="9ba00-123">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="9ba00-123">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
