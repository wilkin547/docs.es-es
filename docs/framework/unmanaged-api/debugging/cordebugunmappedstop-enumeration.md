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
ms.openlocfilehash: c1cea8adcd12ecb3078e4469e6b018ed49064e0b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59175934"
---
# <a name="cordebugunmappedstop-enumeration"></a><span data-ttu-id="d2cd4-102">CorDebugUnmappedStop (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="d2cd4-102">CorDebugUnmappedStop Enumeration</span></span>
<span data-ttu-id="d2cd4-103">Especifica el tipo de código no asignado que puede hacer que la ejecución paso a paso desencadene una detención de la ejecución del código.</span><span class="sxs-lookup"><span data-stu-id="d2cd4-103">Specifies the type of unmapped code that can trigger a halt in code execution by the stepper.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2cd4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d2cd4-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="d2cd4-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="d2cd4-105">Members</span></span>  
  
|<span data-ttu-id="d2cd4-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="d2cd4-106">Member</span></span>|<span data-ttu-id="d2cd4-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="d2cd4-107">Description</span></span>|  
|------------|-----------------|  
|`STOP_NONE`|<span data-ttu-id="d2cd4-108">No se detenga en cualquier tipo de código no asignado.</span><span class="sxs-lookup"><span data-stu-id="d2cd4-108">Do not stop in any type of unmapped code.</span></span>|  
|`STOP_PROLOG`|<span data-ttu-id="d2cd4-109">Detenga en código de prólogo.</span><span class="sxs-lookup"><span data-stu-id="d2cd4-109">Stop in prolog code.</span></span>|  
|`STOP_EPILOG`|<span data-ttu-id="d2cd4-110">Detener en el código de epílogo.</span><span class="sxs-lookup"><span data-stu-id="d2cd4-110">Stop in epilog code.</span></span>|  
|`STOP_NO_MAPPING_INFO`|<span data-ttu-id="d2cd4-111">Detener en el código que no tiene ninguna información de asignación.</span><span class="sxs-lookup"><span data-stu-id="d2cd4-111">Stop in code that has no mapping information.</span></span>|  
|`STOP_OTHER_UNMAPPED`|<span data-ttu-id="d2cd4-112">Detenga en código no asignado que no caben en el prólogo, epílogo, no hay información de asignación o categoría no administrado.</span><span class="sxs-lookup"><span data-stu-id="d2cd4-112">Stop in unmapped code that does not fit into the prolog, epilog, no-mapping-information, or unmanaged category.</span></span>|  
|`STOP_UNMANAGED`|<span data-ttu-id="d2cd4-113">Detenga en código no administrado.</span><span class="sxs-lookup"><span data-stu-id="d2cd4-113">Stop in unmanaged code.</span></span> <span data-ttu-id="d2cd4-114">Este valor solo es válido con depuración de interoperabilidad.</span><span class="sxs-lookup"><span data-stu-id="d2cd4-114">This value is valid only with interop debugging.</span></span>|  
|`STOP_ALL`|<span data-ttu-id="d2cd4-115">Detener en todos los tipos de código no asignado.</span><span class="sxs-lookup"><span data-stu-id="d2cd4-115">Stop in all types of unmapped code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d2cd4-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d2cd4-116">Remarks</span></span>  
 <span data-ttu-id="d2cd4-117">Use la [ICorDebugStepper:: SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) método para establecer las marcas que especifican el código no asignado en el que se detendrá el motor paso a paso.</span><span class="sxs-lookup"><span data-stu-id="d2cd4-117">Use the [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) method to set the flags that specify the unmapped code in which the stepper will stop.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2cd4-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d2cd4-118">Requirements</span></span>  
 <span data-ttu-id="d2cd4-119">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d2cd4-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2cd4-120">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d2cd4-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d2cd4-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d2cd4-121">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="d2cd4-122">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="d2cd4-122">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d2cd4-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="d2cd4-123">See also</span></span>

- [<span data-ttu-id="d2cd4-124">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="d2cd4-124">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
