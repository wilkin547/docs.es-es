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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ec23e0f272852088987fcc74767d3645778eab45
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69955680"
---
# <a name="cordebugdecodeeventflagswindows-enumeration"></a><span data-ttu-id="2df32-102">Enumeración CorDebugDecodeEventFlagsWindows</span><span class="sxs-lookup"><span data-stu-id="2df32-102">CorDebugDecodeEventFlagsWindows Enumeration</span></span>
<span data-ttu-id="2df32-103">Proporciona información extra sobre los eventos de depuración en la plataforma Windows.</span><span class="sxs-lookup"><span data-stu-id="2df32-103">Provides additional information about debug events on the Windows platform.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2df32-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2df32-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugDecodeEventFlagsWindows {  
    IS_FIRST_CHANCE = 1,  
} CorDebugDecodeEventFlagsWindows;  
```  
  
## <a name="members"></a><span data-ttu-id="2df32-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="2df32-105">Members</span></span>  
  
|<span data-ttu-id="2df32-106">Member</span><span class="sxs-lookup"><span data-stu-id="2df32-106">Member</span></span>|<span data-ttu-id="2df32-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="2df32-107">Description</span></span>|  
|------------|-----------------|  
|`IS_FIRST_CHANCE`|<span data-ttu-id="2df32-108">Indica que el evento de depuración es una primera excepción.</span><span class="sxs-lookup"><span data-stu-id="2df32-108">Indicates that the debug event is a first-chance exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2df32-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2df32-109">Remarks</span></span>  
 <span data-ttu-id="2df32-110">El método [método icordebugprocess6::D ecodeevent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) incluye un `dwFlags` parámetro que proporciona información adicional sobre un evento de depuración y cuyo valor depende de la arquitectura de destino.</span><span class="sxs-lookup"><span data-stu-id="2df32-110">The [ICorDebugProcess6::DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) method includes a `dwFlags` parameter that provides additional information about a debug event and whose value is dependent on the target architecture.</span></span> <span data-ttu-id="2df32-111">La enumeración `CorDebugDecodeEventFlagsWindows` se puede usar con eventos de depuración en la plataforma Windows.</span><span class="sxs-lookup"><span data-stu-id="2df32-111">The `CorDebugDecodeEventFlagsWindows` enumeration can be used with debug events on the Windows platform.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2df32-112">Esta enumeración está pensada solo para su uso en escenarios de depuración .NET Native.</span><span class="sxs-lookup"><span data-stu-id="2df32-112">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2df32-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2df32-113">Requirements</span></span>  
 <span data-ttu-id="2df32-114">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2df32-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2df32-115">**Encabezado**: Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="2df32-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2df32-116">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2df32-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2df32-117">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2df32-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2df32-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="2df32-118">See also</span></span>

- [<span data-ttu-id="2df32-119">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="2df32-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
