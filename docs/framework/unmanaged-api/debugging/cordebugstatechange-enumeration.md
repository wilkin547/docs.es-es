---
title: "Enumeración CorDebugStateChange"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugStateChange
api_location: mscordbi.dll
api_type: COM
ms.assetid: 1d4424ab-5143-4e50-a84a-ceeb4ddf3bba
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: caf49621342be0ff85ac3cb56b95bb87f524c3be
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="cordebugstatechange-enumeration"></a><span data-ttu-id="a1efd-102">Enumeración CorDebugStateChange</span><span class="sxs-lookup"><span data-stu-id="a1efd-102">CorDebugStateChange Enumeration</span></span>
<span data-ttu-id="a1efd-103">Describe la cantidad de datos almacenados en caché que se debe descartar según los cambios en el proceso.</span><span class="sxs-lookup"><span data-stu-id="a1efd-103">Describes the amount of cached data that must be discarded based on changes to the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1efd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a1efd-104">Syntax</span></span>  
  
```  
typedef enum CorDebugStateChange  
{  
    PROCESS_RUNNING = 0x0000001,   
    FLUSH_ALL       = 0x0000002,   
} CorDebugStateChange;  
```  
  
## <a name="members"></a><span data-ttu-id="a1efd-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="a1efd-105">Members</span></span>  
  
|<span data-ttu-id="a1efd-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="a1efd-106">Member</span></span>|<span data-ttu-id="a1efd-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="a1efd-107">Description</span></span>|  
|------------|-----------------|  
|`PROCESS_RUNNING`|<span data-ttu-id="a1efd-108">El proceso alcanzó un nuevo estado de memoria por ejecución directa.</span><span class="sxs-lookup"><span data-stu-id="a1efd-108">The process reached a new memory state via forward execution.</span></span>|  
|`SET_CONTEXT_FLAG_UNWIND_FRAME`|<span data-ttu-id="a1efd-109">La memoria del proceso puede ser diferente de forma arbitraria de lo que era anteriormente.</span><span class="sxs-lookup"><span data-stu-id="a1efd-109">The process' memory may be arbitrarily different than it was previously.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a1efd-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a1efd-110">Remarks</span></span>  
 <span data-ttu-id="a1efd-111">Un miembro de la `CorDebugStateChange` enumeración se proporciona como un argumento cuando el depurador llama el [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md) (método)</span><span class="sxs-lookup"><span data-stu-id="a1efd-111">A member of the `CorDebugStateChange` enumeration is provided as an argument when the debugger calls the [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md) method</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a1efd-112">Esta enumeración está pensada solo para su uso en escenarios de depuración .NET Native.</span><span class="sxs-lookup"><span data-stu-id="a1efd-112">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1efd-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a1efd-113">Requirements</span></span>  
 <span data-ttu-id="a1efd-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1efd-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1efd-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a1efd-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a1efd-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a1efd-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a1efd-117">**Versiones de .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1efd-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1efd-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="a1efd-118">See Also</span></span>  
 [<span data-ttu-id="a1efd-119">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="a1efd-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [<span data-ttu-id="a1efd-120">Depuración</span><span class="sxs-lookup"><span data-stu-id="a1efd-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
