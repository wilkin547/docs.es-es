---
description: 'Más información sobre: enumeración CorDebugDebugEventKind'
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
ms.openlocfilehash: 62094c934873a74fdab01fad87c42126e28cb0f4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801714"
---
# <a name="cordebugdebugeventkind-enumeration"></a><span data-ttu-id="b2a16-103">Enumeración CorDebugDebugEventKind</span><span class="sxs-lookup"><span data-stu-id="b2a16-103">CorDebugDebugEventKind Enumeration</span></span>

<span data-ttu-id="b2a16-104">Indica el tipo de evento cuya información se descodifica mediante el método [DecodeEvent](icordebugprocess6-decodeevent-method.md) .</span><span class="sxs-lookup"><span data-stu-id="b2a16-104">Indicates the type of event whose information is decoded by the [DecodeEvent](icordebugprocess6-decodeevent-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2a16-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b2a16-105">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="b2a16-106">Members</span><span class="sxs-lookup"><span data-stu-id="b2a16-106">Members</span></span>  
  
|<span data-ttu-id="b2a16-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="b2a16-107">Member</span></span>|<span data-ttu-id="b2a16-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="b2a16-108">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EVENT_KIND_MODULE_LOADED`|<span data-ttu-id="b2a16-109">Evento load del módulo.</span><span class="sxs-lookup"><span data-stu-id="b2a16-109">A module load event.</span></span>|  
|`DEBUG_EVENT_KIND_MODULE_UNLOADED`|<span data-ttu-id="b2a16-110">Evento unload del módulo.</span><span class="sxs-lookup"><span data-stu-id="b2a16-110">A module unload event.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_FIRST_CHANCE`|<span data-ttu-id="b2a16-111">Primera excepción.</span><span class="sxs-lookup"><span data-stu-id="b2a16-111">A first-chance exception.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_USER_FIRST_CHANCE`|<span data-ttu-id="b2a16-112">Primera excepción de usuario.</span><span class="sxs-lookup"><span data-stu-id="b2a16-112">A first-chance user exception.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_CATCH_HANDLER_FOUND`|<span data-ttu-id="b2a16-113">Excepción para la que existe un controlador `catch`.</span><span class="sxs-lookup"><span data-stu-id="b2a16-113">An exception for which a `catch` handler exists.</span></span>|  
|`DEBUG_EVENT_KIND_MANAGED_EXCEPTION_UNHANDLED`|<span data-ttu-id="b2a16-114">Excepción sin controlar.</span><span class="sxs-lookup"><span data-stu-id="b2a16-114">An unhandled exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b2a16-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b2a16-115">Remarks</span></span>  

 <span data-ttu-id="b2a16-116">Un miembro de la `CorDebugDebugEventKind` enumeración se devuelve mediante una llamada al método [ICorDebugDebugEvent:: GetEventKind](icordebugdebugevent-geteventkind-method.md) .</span><span class="sxs-lookup"><span data-stu-id="b2a16-116">A member of the `CorDebugDebugEventKind` enumeration is returned by calling the [ICorDebugDebugEvent::GetEventKind](icordebugdebugevent-geteventkind-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b2a16-117">Esta enumeración está pensada solo para su uso en escenarios de depuración .NET Native.</span><span class="sxs-lookup"><span data-stu-id="b2a16-117">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2a16-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b2a16-118">Requirements</span></span>  

 <span data-ttu-id="b2a16-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2a16-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2a16-120">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b2a16-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b2a16-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b2a16-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b2a16-122">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2a16-122">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2a16-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="b2a16-123">See also</span></span>

- [<span data-ttu-id="b2a16-124">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="b2a16-124">Debugging Enumerations</span></span>](debugging-enumerations.md)
