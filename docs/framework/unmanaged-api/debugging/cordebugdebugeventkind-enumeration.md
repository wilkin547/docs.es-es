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
ms.openlocfilehash: de4ac1f39ea9cfb4b616bd4e2c85e5de530dbb0b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132231"
---
# <a name="cordebugdebugeventkind-enumeration"></a><span data-ttu-id="3b212-102">Enumeración CorDebugDebugEventKind</span><span class="sxs-lookup"><span data-stu-id="3b212-102">CorDebugDebugEventKind Enumeration</span></span>
<span data-ttu-id="3b212-103">Indica el tipo de evento cuya información se descodifica mediante el método [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) .</span><span class="sxs-lookup"><span data-stu-id="3b212-103">Indicates the type of event whose information is decoded by the [DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b212-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3b212-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugDebugEventKind {  
    DEBUG_EVENT_KIND_MODULE_LOADED                          = 1,  
    DEBUG_EVENT_KIND_MODULE_UNLOADED                        = 2,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_FIRST_CHANCE         = 3,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_USER_FIRST_CHANCE    = 4,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_CATCH_HANDLER_FOUND  = 5,  
    DEBUG_EVENT_KIND_MANAGED_EXCEPTION_UNHANDLED            = 6  
} CorDebugRecordFormat;  
```  
  
## <a name="members"></a><span data-ttu-id="3b212-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="3b212-105">Members</span></span>  
  
|<span data-ttu-id="3b212-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="3b212-106">Member</span></span>|<span data-ttu-id="3b212-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="3b212-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EVENT_KIND_MODULE_LOADED`|<span data-ttu-id="3b212-108">Evento load del módulo.</span><span class="sxs-lookup"><span data-stu-id="3b212-108">A module load event.</span></span>|  
|`DEBUG_EVENT_KIND_MODULE_UNLOADED`|<span data-ttu-id="3b212-109">Evento unload del módulo.</span><span class="sxs-lookup"><span data-stu-id="3b212-109">A module unload event.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_FIRST_CHANCE`|<span data-ttu-id="3b212-110">Primera excepción.</span><span class="sxs-lookup"><span data-stu-id="3b212-110">A first-chance exception.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_USER_FIRST_CHANCE`|<span data-ttu-id="3b212-111">Primera excepción de usuario.</span><span class="sxs-lookup"><span data-stu-id="3b212-111">A first-chance user exception.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_CATCH_HANDLER_FOUND`|<span data-ttu-id="3b212-112">Excepción para la que existe un controlador `catch`.</span><span class="sxs-lookup"><span data-stu-id="3b212-112">An exception for which a `catch` handler exists.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_UNHANDLED`|<span data-ttu-id="3b212-113">Excepción sin controlar.</span><span class="sxs-lookup"><span data-stu-id="3b212-113">An unhandled exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3b212-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3b212-114">Remarks</span></span>  
 <span data-ttu-id="3b212-115">Un miembro de la enumeración `CorDebugDebugEventKind` se devuelve llamando al método [ICorDebugDebugEvent:: GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) .</span><span class="sxs-lookup"><span data-stu-id="3b212-115">A member of the `CorDebugDebugEventKind` enumeration is returned by calling the [ICorDebugDebugEvent::GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3b212-116">Esta enumeración está pensada solo para su uso en escenarios de depuración .NET Native.</span><span class="sxs-lookup"><span data-stu-id="3b212-116">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b212-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3b212-117">Requirements</span></span>  
 <span data-ttu-id="3b212-118">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3b212-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b212-119">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3b212-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3b212-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3b212-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3b212-121">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b212-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b212-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="3b212-122">See also</span></span>

- [<span data-ttu-id="3b212-123">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="3b212-123">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
