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
ms.openlocfilehash: 23e168b0f322a580917c3fcfcb767a7d4d4628f6
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793883"
---
# <a name="cordebugunmappedstop-enumeration"></a><span data-ttu-id="e563f-102">CorDebugUnmappedStop (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="e563f-102">CorDebugUnmappedStop Enumeration</span></span>
<span data-ttu-id="e563f-103">Especifica el tipo de código no asignado que puede hacer que la ejecución paso a paso desencadene una detención de la ejecución del código.</span><span class="sxs-lookup"><span data-stu-id="e563f-103">Specifies the type of unmapped code that can trigger a halt in code execution by the stepper.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e563f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e563f-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="e563f-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="e563f-105">Members</span></span>  
  
|<span data-ttu-id="e563f-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="e563f-106">Member</span></span>|<span data-ttu-id="e563f-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="e563f-107">Description</span></span>|  
|------------|-----------------|  
|`STOP_NONE`|<span data-ttu-id="e563f-108">No se detenga en ningún tipo de código sin asignar.</span><span class="sxs-lookup"><span data-stu-id="e563f-108">Do not stop in any type of unmapped code.</span></span>|  
|`STOP_PROLOG`|<span data-ttu-id="e563f-109">Detenga el código de prólogo.</span><span class="sxs-lookup"><span data-stu-id="e563f-109">Stop in prolog code.</span></span>|  
|`STOP_EPILOG`|<span data-ttu-id="e563f-110">Detenga el código de epílogo.</span><span class="sxs-lookup"><span data-stu-id="e563f-110">Stop in epilog code.</span></span>|  
|`STOP_NO_MAPPING_INFO`|<span data-ttu-id="e563f-111">Detenga el código que no tenga información de asignación.</span><span class="sxs-lookup"><span data-stu-id="e563f-111">Stop in code that has no mapping information.</span></span>|  
|`STOP_OTHER_UNMAPPED`|<span data-ttu-id="e563f-112">Detenga en el código no asignado que no se ajuste a la categoría prólogo, epílogo, sin asignación-información o no administrada.</span><span class="sxs-lookup"><span data-stu-id="e563f-112">Stop in unmapped code that does not fit into the prolog, epilog, no-mapping-information, or unmanaged category.</span></span>|  
|`STOP_UNMANAGED`|<span data-ttu-id="e563f-113">Detenga el código no administrado.</span><span class="sxs-lookup"><span data-stu-id="e563f-113">Stop in unmanaged code.</span></span> <span data-ttu-id="e563f-114">Este valor solo es válido con la depuración de interoperabilidad.</span><span class="sxs-lookup"><span data-stu-id="e563f-114">This value is valid only with interop debugging.</span></span>|  
|`STOP_ALL`|<span data-ttu-id="e563f-115">Detenga en todos los tipos de código sin asignar.</span><span class="sxs-lookup"><span data-stu-id="e563f-115">Stop in all types of unmapped code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e563f-116">Notas</span><span class="sxs-lookup"><span data-stu-id="e563f-116">Remarks</span></span>  
 <span data-ttu-id="e563f-117">Use el método [ICorDebugStepper:: setunmappedstopmask (](icordebugstepper-setunmappedstopmask-method.md) para establecer las marcas que especifican el código no asignado en el que se detendrá el stepper.</span><span class="sxs-lookup"><span data-stu-id="e563f-117">Use the [ICorDebugStepper::SetUnmappedStopMask](icordebugstepper-setunmappedstopmask-method.md) method to set the flags that specify the unmapped code in which the stepper will stop.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e563f-118">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="e563f-118">Requirements</span></span>  
 <span data-ttu-id="e563f-119">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e563f-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e563f-120">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e563f-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e563f-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e563f-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e563f-122">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e563f-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e563f-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="e563f-123">See also</span></span>

- [<span data-ttu-id="e563f-124">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="e563f-124">Debugging Enumerations</span></span>](debugging-enumerations.md)
