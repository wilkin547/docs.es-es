---
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
ms.openlocfilehash: a7a450e85f7eaa765766ffa985d7c01538e2669c
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795799"
---
# <a name="cordebugmappingresult-enumeration"></a><span data-ttu-id="fc5ea-102">CorDebugMappingResult (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="fc5ea-102">CorDebugMappingResult Enumeration</span></span>
<span data-ttu-id="fc5ea-103">Proporciona información detallada sobre cómo se obtuvo el valor del puntero de instrucción (IP).</span><span class="sxs-lookup"><span data-stu-id="fc5ea-103">Provides the details of how the value of the instruction pointer (IP) was obtained.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc5ea-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fc5ea-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="fc5ea-105">Members</span><span class="sxs-lookup"><span data-stu-id="fc5ea-105">Members</span></span>  
  
|<span data-ttu-id="fc5ea-106">Member</span><span class="sxs-lookup"><span data-stu-id="fc5ea-106">Member</span></span>|<span data-ttu-id="fc5ea-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="fc5ea-107">Description</span></span>|  
|------------|-----------------|  
|`MAPPING_PROLOG`|<span data-ttu-id="fc5ea-108">El código nativo está en el prólogo, por lo que el valor de la dirección IP es 0.</span><span class="sxs-lookup"><span data-stu-id="fc5ea-108">The native code is in the prolog, so the value of the IP is 0.</span></span>|  
|`MAPPING_EPILOG`|<span data-ttu-id="fc5ea-109">El código nativo está en un epílogo, por lo que el valor de la dirección IP es la dirección de la última instrucción del método.</span><span class="sxs-lookup"><span data-stu-id="fc5ea-109">The native code is in an epilog, so the value of the IP is the address of the last instruction of the method.</span></span>|  
|`MAPPING_NO_INFO`|<span data-ttu-id="fc5ea-110">No hay información de asignación disponible para el método, por lo que el valor de la dirección IP es 0.</span><span class="sxs-lookup"><span data-stu-id="fc5ea-110">No mapping information is available for the method, so the value of the IP is 0.</span></span>|  
|`MAPPING_UNMAPPED_ADDRESS`|<span data-ttu-id="fc5ea-111">Aunque hay información de asignación para el método, la dirección actual no se puede asignar al código del lenguaje intermedio de Microsoft (MSIL).</span><span class="sxs-lookup"><span data-stu-id="fc5ea-111">Although there is mapping information for the method, the current address cannot be mapped to Microsoft intermediate language (MSIL) code.</span></span> <span data-ttu-id="fc5ea-112">El valor de la dirección IP es 0.</span><span class="sxs-lookup"><span data-stu-id="fc5ea-112">The value of the IP is 0.</span></span>|  
|`MAPPING_EXACT`|<span data-ttu-id="fc5ea-113">El método se asigna exactamente al código MSIL o el marco se ha interpretado, por lo que el valor de la dirección IP es preciso.</span><span class="sxs-lookup"><span data-stu-id="fc5ea-113">Either the method maps exactly to MSIL code or the frame has been interpreted, so the value of the IP is accurate.</span></span>|  
|`MAPPING_APPROXIMATE`|<span data-ttu-id="fc5ea-114">El método se ha asignado correctamente, pero el valor de la dirección IP puede ser aproximado.</span><span class="sxs-lookup"><span data-stu-id="fc5ea-114">The method was successfully mapped, but the value of the IP may be approximate.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fc5ea-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fc5ea-115">Remarks</span></span>  
 <span data-ttu-id="fc5ea-116">Puede usar el método [ICorDebugILFrame:: GetIP](icordebugilframe-getip-method.md) para obtener el valor del puntero de instrucción.</span><span class="sxs-lookup"><span data-stu-id="fc5ea-116">You can use the [ICorDebugILFrame::GetIP](icordebugilframe-getip-method.md) method to obtain the value of the instruction pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc5ea-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fc5ea-117">Requirements</span></span>  
 <span data-ttu-id="fc5ea-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc5ea-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc5ea-119">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fc5ea-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fc5ea-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fc5ea-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fc5ea-121">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc5ea-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc5ea-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="fc5ea-122">See also</span></span>

- [<span data-ttu-id="fc5ea-123">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="fc5ea-123">Debugging Enumerations</span></span>](debugging-enumerations.md)
