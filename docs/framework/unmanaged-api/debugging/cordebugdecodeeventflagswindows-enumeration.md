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
ms.openlocfilehash: da3a100bd552eaa3233642b006e0265adbcac1ca
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132211"
---
# <a name="cordebugdecodeeventflagswindows-enumeration"></a><span data-ttu-id="b335a-102">Enumeración CorDebugDecodeEventFlagsWindows</span><span class="sxs-lookup"><span data-stu-id="b335a-102">CorDebugDecodeEventFlagsWindows Enumeration</span></span>
<span data-ttu-id="b335a-103">Proporciona información extra sobre los eventos de depuración en la plataforma Windows.</span><span class="sxs-lookup"><span data-stu-id="b335a-103">Provides additional information about debug events on the Windows platform.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b335a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b335a-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugDecodeEventFlagsWindows {  
    IS_FIRST_CHANCE = 1,  
} CorDebugDecodeEventFlagsWindows;  
```  
  
## <a name="members"></a><span data-ttu-id="b335a-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="b335a-105">Members</span></span>  
  
|<span data-ttu-id="b335a-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="b335a-106">Member</span></span>|<span data-ttu-id="b335a-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="b335a-107">Description</span></span>|  
|------------|-----------------|  
|`IS_FIRST_CHANCE`|<span data-ttu-id="b335a-108">Indica que el evento de depuración es una primera excepción.</span><span class="sxs-lookup"><span data-stu-id="b335a-108">Indicates that the debug event is a first-chance exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b335a-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b335a-109">Remarks</span></span>  
 <span data-ttu-id="b335a-110">El método [método icordebugprocess6::D ecodeevent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) incluye un parámetro de `dwFlags` que proporciona información adicional sobre un evento de depuración y cuyo valor depende de la arquitectura de destino.</span><span class="sxs-lookup"><span data-stu-id="b335a-110">The [ICorDebugProcess6::DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) method includes a `dwFlags` parameter that provides additional information about a debug event and whose value is dependent on the target architecture.</span></span> <span data-ttu-id="b335a-111">La enumeración `CorDebugDecodeEventFlagsWindows` se puede usar con eventos de depuración en la plataforma Windows.</span><span class="sxs-lookup"><span data-stu-id="b335a-111">The `CorDebugDecodeEventFlagsWindows` enumeration can be used with debug events on the Windows platform.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b335a-112">Esta enumeración está pensada solo para su uso en escenarios de depuración .NET Native.</span><span class="sxs-lookup"><span data-stu-id="b335a-112">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b335a-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b335a-113">Requirements</span></span>  
 <span data-ttu-id="b335a-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b335a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b335a-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b335a-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b335a-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b335a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b335a-117">**Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b335a-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b335a-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="b335a-118">See also</span></span>

- [<span data-ttu-id="b335a-119">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="b335a-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
