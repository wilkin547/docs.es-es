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
ms.openlocfilehash: fa8bbcf4d8e5aadee6a4250d23842187d6c2af09
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405491"
---
# <a name="cordebugdecodeeventflagswindows-enumeration"></a><span data-ttu-id="6f4a3-102">Enumeración CorDebugDecodeEventFlagsWindows</span><span class="sxs-lookup"><span data-stu-id="6f4a3-102">CorDebugDecodeEventFlagsWindows Enumeration</span></span>
<span data-ttu-id="6f4a3-103">Proporciona información extra sobre los eventos de depuración en la plataforma Windows.</span><span class="sxs-lookup"><span data-stu-id="6f4a3-103">Provides additional information about debug events on the Windows platform.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f4a3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6f4a3-104">Syntax</span></span>  
  
```  
typedef enum CorDebugDecodeEventFlagsWindows {  
    IS_FIRST_CHANCE = 1,  
} CorDebugDecodeEventFlagsWindows;  
```  
  
## <a name="members"></a><span data-ttu-id="6f4a3-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="6f4a3-105">Members</span></span>  
  
|<span data-ttu-id="6f4a3-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="6f4a3-106">Member</span></span>|<span data-ttu-id="6f4a3-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="6f4a3-107">Description</span></span>|  
|------------|-----------------|  
|`IS_FIRST_CHANCE`|<span data-ttu-id="6f4a3-108">Indica que el evento de depuración es una primera excepción.</span><span class="sxs-lookup"><span data-stu-id="6f4a3-108">Indicates that the debug event is a first-chance exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6f4a3-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6f4a3-109">Remarks</span></span>  
 <span data-ttu-id="6f4a3-110">El [icordebugprocess6:: Decodeevent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) método incluye un `dwFlags` parámetro que proporciona información adicional sobre un evento de depuración y cuyo valor es dependiente de la arquitectura de destino.</span><span class="sxs-lookup"><span data-stu-id="6f4a3-110">The [ICorDebugProcess6::DecodeEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-decodeevent-method.md) method includes a `dwFlags` parameter that provides additional information about a debug event and whose value is dependent on the target architecture.</span></span> <span data-ttu-id="6f4a3-111">La enumeración `CorDebugDecodeEventFlagsWindows` se puede usar con eventos de depuración en la plataforma Windows.</span><span class="sxs-lookup"><span data-stu-id="6f4a3-111">The `CorDebugDecodeEventFlagsWindows` enumeration can be used with debug events on the Windows platform.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6f4a3-112">Esta enumeración está pensada solo para su uso en escenarios de depuración .NET Native.</span><span class="sxs-lookup"><span data-stu-id="6f4a3-112">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f4a3-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6f4a3-113">Requirements</span></span>  
 <span data-ttu-id="6f4a3-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f4a3-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f4a3-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6f4a3-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6f4a3-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6f4a3-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6f4a3-117">**Versiones de .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f4a3-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f4a3-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="6f4a3-118">See Also</span></span>  
 [<span data-ttu-id="6f4a3-119">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="6f4a3-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
