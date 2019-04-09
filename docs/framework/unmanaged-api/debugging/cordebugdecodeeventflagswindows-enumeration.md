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
ms.openlocfilehash: 2d4e006a03db5b16de93dfd07ec7b964db4bfc1d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59207739"
---
# <a name="cordebugdecodeeventflagswindows-enumeration"></a><span data-ttu-id="3ed54-102">Enumeración CorDebugDecodeEventFlagsWindows</span><span class="sxs-lookup"><span data-stu-id="3ed54-102">CorDebugDecodeEventFlagsWindows Enumeration</span></span>
<span data-ttu-id="3ed54-103">Proporciona información extra sobre los eventos de depuración en la plataforma Windows.</span><span class="sxs-lookup"><span data-stu-id="3ed54-103">Provides additional information about debug events on the Windows platform.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ed54-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3ed54-104">Syntax</span></span>  
  
```  
typedef enum CorDebugDecodeEventFlagsWindows {  
    IS_FIRST_CHANCE = 1,  
} CorDebugDecodeEventFlagsWindows;  
```  
  
## <a name="members"></a><span data-ttu-id="3ed54-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="3ed54-105">Members</span></span>  
  
|<span data-ttu-id="3ed54-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="3ed54-106">Member</span></span>|<span data-ttu-id="3ed54-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="3ed54-107">Description</span></span>|  
|------------|-----------------|  
|`IS_FIRST_CHANCE`|<span data-ttu-id="3ed54-108">Indica que el evento de depuración es una primera excepción.</span><span class="sxs-lookup"><span data-stu-id="3ed54-108">Indicates that the debug event is a first-chance exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3ed54-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3ed54-109">Remarks</span></span>  
 <span data-ttu-id="3ed54-110">El [icordebugprocess6:: Decodeevent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) método incluye un `dwFlags` parámetro que proporciona información adicional sobre un evento de depuración y cuyo valor depende de la arquitectura de destino.</span><span class="sxs-lookup"><span data-stu-id="3ed54-110">The [ICorDebugProcess6::DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) method includes a `dwFlags` parameter that provides additional information about a debug event and whose value is dependent on the target architecture.</span></span> <span data-ttu-id="3ed54-111">La enumeración `CorDebugDecodeEventFlagsWindows` se puede usar con eventos de depuración en la plataforma Windows.</span><span class="sxs-lookup"><span data-stu-id="3ed54-111">The `CorDebugDecodeEventFlagsWindows` enumeration can be used with debug events on the Windows platform.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3ed54-112">Esta enumeración está pensada solo para su uso en escenarios de depuración .NET Native.</span><span class="sxs-lookup"><span data-stu-id="3ed54-112">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ed54-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3ed54-113">Requirements</span></span>  
 <span data-ttu-id="3ed54-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3ed54-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ed54-115">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3ed54-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3ed54-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3ed54-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="3ed54-117">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="3ed54-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3ed54-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="3ed54-118">See also</span></span>

- [<span data-ttu-id="3ed54-119">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="3ed54-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
