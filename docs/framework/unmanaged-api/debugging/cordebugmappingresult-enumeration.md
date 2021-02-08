---
description: 'Más información sobre: enumeración CorDebugMappingResult ('
title: CorDebugMappingResult (Enumeración)
ms.date: 03/30/2017
api_name:
- CorDebugMappingResult
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugMappingResult
helpviewer_keywords:
- CorDebugMappingResult enumeration [.NET Framework debugging]
ms.assetid: 701281dd-2936-45c8-a1f0-3bf7332b093b
topic_type:
- apiref
ms.openlocfilehash: 03454e2fbfa8fabca89805ea51a6cfba27aa792f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801597"
---
# <a name="cordebugmappingresult-enumeration"></a><span data-ttu-id="375da-103">CorDebugMappingResult (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="375da-103">CorDebugMappingResult Enumeration</span></span>

<span data-ttu-id="375da-104">Proporciona información detallada sobre cómo se obtuvo el valor del puntero de instrucción (IP).</span><span class="sxs-lookup"><span data-stu-id="375da-104">Provides the details of how the value of the instruction pointer (IP) was obtained.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="375da-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="375da-105">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugMappingResult {  
    MAPPING_PROLOG              = 0x1,  
    MAPPING_EPILOG              = 0x2,  
    MAPPING_NO_INFO             = 0x4,  
    MAPPING_UNMAPPED_ADDRESS    = 0x8,  
    MAPPING_EXACT               = 0x10,  
    MAPPING_APPROXIMATE         = 0x20,  
} CorDebugMappingResult;  
```  
  
## <a name="members"></a><span data-ttu-id="375da-106">Members</span><span class="sxs-lookup"><span data-stu-id="375da-106">Members</span></span>  
  
|<span data-ttu-id="375da-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="375da-107">Member</span></span>|<span data-ttu-id="375da-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="375da-108">Description</span></span>|  
|------------|-----------------|  
|`MAPPING_PROLOG`|<span data-ttu-id="375da-109">El código nativo está en el prólogo, por lo que el valor de la dirección IP es 0.</span><span class="sxs-lookup"><span data-stu-id="375da-109">The native code is in the prolog, so the value of the IP is 0.</span></span>|  
|`MAPPING_EPILOG`|<span data-ttu-id="375da-110">El código nativo está en un epílogo, por lo que el valor de la dirección IP es la dirección de la última instrucción del método.</span><span class="sxs-lookup"><span data-stu-id="375da-110">The native code is in an epilog, so the value of the IP is the address of the last instruction of the method.</span></span>|  
|`MAPPING_NO_INFO`|<span data-ttu-id="375da-111">No hay información de asignación disponible para el método, por lo que el valor de la dirección IP es 0.</span><span class="sxs-lookup"><span data-stu-id="375da-111">No mapping information is available for the method, so the value of the IP is 0.</span></span>|  
|`MAPPING_UNMAPPED_ADDRESS`|<span data-ttu-id="375da-112">Aunque hay información de asignación para el método, la dirección actual no se puede asignar al código del lenguaje intermedio de Microsoft (MSIL).</span><span class="sxs-lookup"><span data-stu-id="375da-112">Although there is mapping information for the method, the current address cannot be mapped to Microsoft intermediate language (MSIL) code.</span></span> <span data-ttu-id="375da-113">El valor de la dirección IP es 0.</span><span class="sxs-lookup"><span data-stu-id="375da-113">The value of the IP is 0.</span></span>|  
|`MAPPING_EXACT`|<span data-ttu-id="375da-114">El método se asigna exactamente al código MSIL o el marco se ha interpretado, por lo que el valor de la dirección IP es preciso.</span><span class="sxs-lookup"><span data-stu-id="375da-114">Either the method maps exactly to MSIL code or the frame has been interpreted, so the value of the IP is accurate.</span></span>|  
|`MAPPING_APPROXIMATE`|<span data-ttu-id="375da-115">El método se ha asignado correctamente, pero el valor de la dirección IP puede ser aproximado.</span><span class="sxs-lookup"><span data-stu-id="375da-115">The method was successfully mapped, but the value of the IP may be approximate.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="375da-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="375da-116">Remarks</span></span>  

 <span data-ttu-id="375da-117">Puede usar el método [ICorDebugILFrame:: GetIP](icordebugilframe-getip-method.md) para obtener el valor del puntero de instrucción.</span><span class="sxs-lookup"><span data-stu-id="375da-117">You can use the [ICorDebugILFrame::GetIP](icordebugilframe-getip-method.md) method to obtain the value of the instruction pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="375da-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="375da-118">Requirements</span></span>  

 <span data-ttu-id="375da-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="375da-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="375da-120">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="375da-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="375da-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="375da-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="375da-122">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="375da-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="375da-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="375da-123">See also</span></span>

- [<span data-ttu-id="375da-124">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="375da-124">Debugging Enumerations</span></span>](debugging-enumerations.md)
