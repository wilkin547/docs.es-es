---
description: 'Más información sobre: enumeración Cordebugunmappedstop ('
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
ms.openlocfilehash: 9c4f70c5de451689f98a1c08627fd6df5128fdbd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801532"
---
# <a name="cordebugunmappedstop-enumeration"></a><span data-ttu-id="232d2-103">CorDebugUnmappedStop (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="232d2-103">CorDebugUnmappedStop Enumeration</span></span>

<span data-ttu-id="232d2-104">Especifica el tipo de código no asignado que puede hacer que la ejecución paso a paso desencadene una detención de la ejecución del código.</span><span class="sxs-lookup"><span data-stu-id="232d2-104">Specifies the type of unmapped code that can trigger a halt in code execution by the stepper.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="232d2-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="232d2-105">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="232d2-106">Members</span><span class="sxs-lookup"><span data-stu-id="232d2-106">Members</span></span>  
  
|<span data-ttu-id="232d2-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="232d2-107">Member</span></span>|<span data-ttu-id="232d2-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="232d2-108">Description</span></span>|  
|------------|-----------------|  
|`STOP_NONE`|<span data-ttu-id="232d2-109">No se detenga en ningún tipo de código sin asignar.</span><span class="sxs-lookup"><span data-stu-id="232d2-109">Do not stop in any type of unmapped code.</span></span>|  
|`STOP_PROLOG`|<span data-ttu-id="232d2-110">Detenga el código de prólogo.</span><span class="sxs-lookup"><span data-stu-id="232d2-110">Stop in prolog code.</span></span>|  
|`STOP_EPILOG`|<span data-ttu-id="232d2-111">Detenga el código de epílogo.</span><span class="sxs-lookup"><span data-stu-id="232d2-111">Stop in epilog code.</span></span>|  
|`STOP_NO_MAPPING_INFO`|<span data-ttu-id="232d2-112">Detenga el código que no tenga información de asignación.</span><span class="sxs-lookup"><span data-stu-id="232d2-112">Stop in code that has no mapping information.</span></span>|  
|`STOP_OTHER_UNMAPPED`|<span data-ttu-id="232d2-113">Detenga en el código no asignado que no se ajuste a la categoría prólogo, epílogo, sin asignación-información o no administrada.</span><span class="sxs-lookup"><span data-stu-id="232d2-113">Stop in unmapped code that does not fit into the prolog, epilog, no-mapping-information, or unmanaged category.</span></span>|  
|`STOP_UNMANAGED`|<span data-ttu-id="232d2-114">Detenga el código no administrado.</span><span class="sxs-lookup"><span data-stu-id="232d2-114">Stop in unmanaged code.</span></span> <span data-ttu-id="232d2-115">Este valor solo es válido con la depuración de interoperabilidad.</span><span class="sxs-lookup"><span data-stu-id="232d2-115">This value is valid only with interop debugging.</span></span>|  
|`STOP_ALL`|<span data-ttu-id="232d2-116">Detenga en todos los tipos de código sin asignar.</span><span class="sxs-lookup"><span data-stu-id="232d2-116">Stop in all types of unmapped code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="232d2-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="232d2-117">Remarks</span></span>  

 <span data-ttu-id="232d2-118">Use el método [ICorDebugStepper:: setunmappedstopmask (](icordebugstepper-setunmappedstopmask-method.md) para establecer las marcas que especifican el código no asignado en el que se detendrá el stepper.</span><span class="sxs-lookup"><span data-stu-id="232d2-118">Use the [ICorDebugStepper::SetUnmappedStopMask](icordebugstepper-setunmappedstopmask-method.md) method to set the flags that specify the unmapped code in which the stepper will stop.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="232d2-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="232d2-119">Requirements</span></span>  

 <span data-ttu-id="232d2-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="232d2-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="232d2-121">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="232d2-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="232d2-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="232d2-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="232d2-123">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="232d2-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="232d2-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="232d2-124">See also</span></span>

- [<span data-ttu-id="232d2-125">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="232d2-125">Debugging Enumerations</span></span>](debugging-enumerations.md)
