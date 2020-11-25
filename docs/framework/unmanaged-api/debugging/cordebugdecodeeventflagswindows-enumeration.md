---
title: Enumeración CorDebugDecodeEventFlagsWindows
ms.date: 03/30/2017
api_name:
- CorDebugDecodeEventFlagsWindows
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: aa6cf962-30ae-4cfd-8895-826deeb46a54
topic_type:
- apiref
ms.openlocfilehash: 60eab923aac5dea927105e8ca9fa77eb5708f5ac
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733365"
---
# <a name="cordebugdecodeeventflagswindows-enumeration"></a><span data-ttu-id="b4fda-102">Enumeración CorDebugDecodeEventFlagsWindows</span><span class="sxs-lookup"><span data-stu-id="b4fda-102">CorDebugDecodeEventFlagsWindows Enumeration</span></span>

<span data-ttu-id="b4fda-103">Proporciona información extra sobre los eventos de depuración en la plataforma Windows.</span><span class="sxs-lookup"><span data-stu-id="b4fda-103">Provides additional information about debug events on the Windows platform.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4fda-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b4fda-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugDecodeEventFlagsWindows {  
    IS_FIRST_CHANCE = 1,  
} CorDebugDecodeEventFlagsWindows;  
```  
  
## <a name="members"></a><span data-ttu-id="b4fda-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="b4fda-105">Members</span></span>  
  
|<span data-ttu-id="b4fda-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="b4fda-106">Member</span></span>|<span data-ttu-id="b4fda-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="b4fda-107">Description</span></span>|  
|------------|-----------------|  
|`IS_FIRST_CHANCE`|<span data-ttu-id="b4fda-108">Indica que el evento de depuración es una primera excepción.</span><span class="sxs-lookup"><span data-stu-id="b4fda-108">Indicates that the debug event is a first-chance exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b4fda-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b4fda-109">Remarks</span></span>  

 <span data-ttu-id="b4fda-110">El método [método icordebugprocess6::D ecodeevent](icordebugprocess6-decodeevent-method.md) incluye un `dwFlags` parámetro que proporciona información adicional sobre un evento de depuración y cuyo valor depende de la arquitectura de destino.</span><span class="sxs-lookup"><span data-stu-id="b4fda-110">The [ICorDebugProcess6::DecodeEvent](icordebugprocess6-decodeevent-method.md) method includes a `dwFlags` parameter that provides additional information about a debug event and whose value is dependent on the target architecture.</span></span> <span data-ttu-id="b4fda-111">La enumeración `CorDebugDecodeEventFlagsWindows` se puede usar con eventos de depuración en la plataforma Windows.</span><span class="sxs-lookup"><span data-stu-id="b4fda-111">The `CorDebugDecodeEventFlagsWindows` enumeration can be used with debug events on the Windows platform.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b4fda-112">Esta enumeración está pensada solo para su uso en escenarios de depuración .NET Native.</span><span class="sxs-lookup"><span data-stu-id="b4fda-112">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4fda-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b4fda-113">Requirements</span></span>  

 <span data-ttu-id="b4fda-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4fda-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4fda-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b4fda-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b4fda-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b4fda-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b4fda-117">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4fda-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4fda-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b4fda-118">See also</span></span>

- [<span data-ttu-id="b4fda-119">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="b4fda-119">Debugging Enumerations</span></span>](debugging-enumerations.md)
