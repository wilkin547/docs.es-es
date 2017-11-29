---
title: "Enumeración CorDebugDecodeEventFlagsWindows"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugDecodeEventFlagsWindows
api_location: mscordbi.dll
api_type: COM
ms.assetid: aa6cf962-30ae-4cfd-8895-826deeb46a54
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: facde76ec24d90795de7dfb70bfe5772a6f21531
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="cordebugdecodeeventflagswindows-enumeration"></a><span data-ttu-id="a4182-102">Enumeración CorDebugDecodeEventFlagsWindows</span><span class="sxs-lookup"><span data-stu-id="a4182-102">CorDebugDecodeEventFlagsWindows Enumeration</span></span>
<span data-ttu-id="a4182-103">Proporciona información extra sobre los eventos de depuración en la plataforma Windows.</span><span class="sxs-lookup"><span data-stu-id="a4182-103">Provides additional information about debug events on the Windows platform.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4182-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a4182-104">Syntax</span></span>  
  
```  
typedef enum CorDebugDecodeEventFlagsWindows {  
    IS_FIRST_CHANCE = 1,  
} CorDebugDecodeEventFlagsWindows;  
```  
  
## <a name="members"></a><span data-ttu-id="a4182-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="a4182-105">Members</span></span>  
  
|<span data-ttu-id="a4182-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="a4182-106">Member</span></span>|<span data-ttu-id="a4182-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="a4182-107">Description</span></span>|  
|------------|-----------------|  
|`IS_FIRST_CHANCE`|<span data-ttu-id="a4182-108">Indica que el evento de depuración es una primera excepción.</span><span class="sxs-lookup"><span data-stu-id="a4182-108">Indicates that the debug event is a first-chance exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a4182-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a4182-109">Remarks</span></span>  
 <span data-ttu-id="a4182-110">El [icordebugprocess6:: Decodeevent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) método incluye un `dwFlags` parámetro que proporciona información adicional sobre un evento de depuración y cuyo valor es dependiente de la arquitectura de destino.</span><span class="sxs-lookup"><span data-stu-id="a4182-110">The [ICorDebugProcess6::DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) method includes a `dwFlags` parameter that provides additional information about a debug event and whose value is dependent on the target architecture.</span></span> <span data-ttu-id="a4182-111">La enumeración `CorDebugDecodeEventFlagsWindows` se puede usar con eventos de depuración en la plataforma Windows.</span><span class="sxs-lookup"><span data-stu-id="a4182-111">The `CorDebugDecodeEventFlagsWindows` enumeration can be used with debug events on the Windows platform.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a4182-112">Esta enumeración está pensada solo para su uso en escenarios de depuración .NET Native.</span><span class="sxs-lookup"><span data-stu-id="a4182-112">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4182-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a4182-113">Requirements</span></span>  
 <span data-ttu-id="a4182-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a4182-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4182-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a4182-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a4182-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a4182-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a4182-117">**Versiones de .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4182-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4182-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="a4182-118">See Also</span></span>  
 [<span data-ttu-id="a4182-119">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="a4182-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
