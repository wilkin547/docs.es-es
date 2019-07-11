---
title: CorDebugUnmappedStop (Enumeración)
ms.date: 03/30/2017
api_name:
- CorDebugUnmappedStop
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugUnmappedStop
helpviewer_keywords:
- CorDebugUnmappedStop enumeration [.NET Framework debugging]
ms.assetid: a684f7d7-d0c2-4690-b721-639e613f11f8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c2ea0bf215c0d2abfe9beb29d736f893073d3be8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739508"
---
# <a name="cordebugunmappedstop-enumeration"></a><span data-ttu-id="21359-102">CorDebugUnmappedStop (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="21359-102">CorDebugUnmappedStop Enumeration</span></span>
<span data-ttu-id="21359-103">Especifica el tipo de código no asignado que puede hacer que la ejecución paso a paso desencadene una detención de la ejecución del código.</span><span class="sxs-lookup"><span data-stu-id="21359-103">Specifies the type of unmapped code that can trigger a halt in code execution by the stepper.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21359-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="21359-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugUnmappedStop {  
    STOP_NONE               = 0x0,  
    STOP_PROLOG             = 0x01,  
    STOP_EPILOG             = 0x02,  
    STOP_NO_MAPPING_INFO    = 0x04,  
    STOP_OTHER_UNMAPPED     = 0x08,  
    STOP_UNMANAGED          = 0x10,  
    STOP_ALL                = 0xffff,  
} CorDebugUnmappedStop;  
```  
  
## <a name="members"></a><span data-ttu-id="21359-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="21359-105">Members</span></span>  
  
|<span data-ttu-id="21359-106">Member</span><span class="sxs-lookup"><span data-stu-id="21359-106">Member</span></span>|<span data-ttu-id="21359-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="21359-107">Description</span></span>|  
|------------|-----------------|  
|`STOP_NONE`|<span data-ttu-id="21359-108">No se detenga en cualquier tipo de código no asignado.</span><span class="sxs-lookup"><span data-stu-id="21359-108">Do not stop in any type of unmapped code.</span></span>|  
|`STOP_PROLOG`|<span data-ttu-id="21359-109">Detenga en código de prólogo.</span><span class="sxs-lookup"><span data-stu-id="21359-109">Stop in prolog code.</span></span>|  
|`STOP_EPILOG`|<span data-ttu-id="21359-110">Detener en el código de epílogo.</span><span class="sxs-lookup"><span data-stu-id="21359-110">Stop in epilog code.</span></span>|  
|`STOP_NO_MAPPING_INFO`|<span data-ttu-id="21359-111">Detener en el código que no tiene ninguna información de asignación.</span><span class="sxs-lookup"><span data-stu-id="21359-111">Stop in code that has no mapping information.</span></span>|  
|`STOP_OTHER_UNMAPPED`|<span data-ttu-id="21359-112">Detenga en código no asignado que no caben en el prólogo, epílogo, no hay información de asignación o categoría no administrado.</span><span class="sxs-lookup"><span data-stu-id="21359-112">Stop in unmapped code that does not fit into the prolog, epilog, no-mapping-information, or unmanaged category.</span></span>|  
|`STOP_UNMANAGED`|<span data-ttu-id="21359-113">Detenga en código no administrado.</span><span class="sxs-lookup"><span data-stu-id="21359-113">Stop in unmanaged code.</span></span> <span data-ttu-id="21359-114">Este valor solo es válido con depuración de interoperabilidad.</span><span class="sxs-lookup"><span data-stu-id="21359-114">This value is valid only with interop debugging.</span></span>|  
|`STOP_ALL`|<span data-ttu-id="21359-115">Detener en todos los tipos de código no asignado.</span><span class="sxs-lookup"><span data-stu-id="21359-115">Stop in all types of unmapped code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="21359-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="21359-116">Remarks</span></span>  
 <span data-ttu-id="21359-117">Use la [ICorDebugStepper:: SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) método para establecer las marcas que especifican el código no asignado en el que se detendrá el motor paso a paso.</span><span class="sxs-lookup"><span data-stu-id="21359-117">Use the [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) method to set the flags that specify the unmapped code in which the stepper will stop.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21359-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="21359-118">Requirements</span></span>  
 <span data-ttu-id="21359-119">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="21359-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21359-120">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="21359-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="21359-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="21359-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="21359-122">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21359-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21359-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="21359-123">See also</span></span>

- [<span data-ttu-id="21359-124">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="21359-124">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
