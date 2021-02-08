---
description: 'Más información sobre: enumeración CorDebugDecodeEventFlagsWindows'
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
ms.openlocfilehash: 765ce4b967d00bd70becca666e2ed418614d6fe3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801701"
---
# <a name="cordebugdecodeeventflagswindows-enumeration"></a><span data-ttu-id="5a956-103">Enumeración CorDebugDecodeEventFlagsWindows</span><span class="sxs-lookup"><span data-stu-id="5a956-103">CorDebugDecodeEventFlagsWindows Enumeration</span></span>

<span data-ttu-id="5a956-104">Proporciona información extra sobre los eventos de depuración en la plataforma Windows.</span><span class="sxs-lookup"><span data-stu-id="5a956-104">Provides additional information about debug events on the Windows platform.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a956-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5a956-105">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugDecodeEventFlagsWindows {  
    IS_FIRST_CHANCE = 1,  
} CorDebugDecodeEventFlagsWindows;  
```  
  
## <a name="members"></a><span data-ttu-id="5a956-106">Members</span><span class="sxs-lookup"><span data-stu-id="5a956-106">Members</span></span>  
  
|<span data-ttu-id="5a956-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="5a956-107">Member</span></span>|<span data-ttu-id="5a956-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="5a956-108">Description</span></span>|  
|------------|-----------------|  
|`IS_FIRST_CHANCE`|<span data-ttu-id="5a956-109">Indica que el evento de depuración es una primera excepción.</span><span class="sxs-lookup"><span data-stu-id="5a956-109">Indicates that the debug event is a first-chance exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5a956-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5a956-110">Remarks</span></span>  

 <span data-ttu-id="5a956-111">El método [método icordebugprocess6::D ecodeevent](icordebugprocess6-decodeevent-method.md) incluye un `dwFlags` parámetro que proporciona información adicional sobre un evento de depuración y cuyo valor depende de la arquitectura de destino.</span><span class="sxs-lookup"><span data-stu-id="5a956-111">The [ICorDebugProcess6::DecodeEvent](icordebugprocess6-decodeevent-method.md) method includes a `dwFlags` parameter that provides additional information about a debug event and whose value is dependent on the target architecture.</span></span> <span data-ttu-id="5a956-112">La enumeración `CorDebugDecodeEventFlagsWindows` se puede usar con eventos de depuración en la plataforma Windows.</span><span class="sxs-lookup"><span data-stu-id="5a956-112">The `CorDebugDecodeEventFlagsWindows` enumeration can be used with debug events on the Windows platform.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5a956-113">Esta enumeración está pensada solo para su uso en escenarios de depuración .NET Native.</span><span class="sxs-lookup"><span data-stu-id="5a956-113">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a956-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5a956-114">Requirements</span></span>  

 <span data-ttu-id="5a956-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a956-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a956-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5a956-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5a956-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5a956-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5a956-118">**.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a956-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a956-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="5a956-119">See also</span></span>

- [<span data-ttu-id="5a956-120">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="5a956-120">Debugging Enumerations</span></span>](debugging-enumerations.md)
