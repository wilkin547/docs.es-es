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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7ca3f5a6af6ea19ec81af3f6ac0a028440f80d56
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33407964"
---
# <a name="cordebugmappingresult-enumeration"></a><span data-ttu-id="2b991-102">CorDebugMappingResult (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="2b991-102">CorDebugMappingResult Enumeration</span></span>
<span data-ttu-id="2b991-103">Proporciona información detallada sobre cómo se obtuvo el valor del puntero de instrucción (IP).</span><span class="sxs-lookup"><span data-stu-id="2b991-103">Provides the details of how the value of the instruction pointer (IP) was obtained.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b991-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2b991-104">Syntax</span></span>  
  
```  
typedef enum CorDebugMappingResult {  
    MAPPING_PROLOG              = 0x1,  
    MAPPING_EPILOG              = 0x2,  
    MAPPING_NO_INFO             = 0x4,  
    MAPPING_UNMAPPED_ADDRESS    = 0x8,  
    MAPPING_EXACT               = 0x10,  
    MAPPING_APPROXIMATE         = 0x20,  
} CorDebugMappingResult;  
```  
  
## <a name="members"></a><span data-ttu-id="2b991-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="2b991-105">Members</span></span>  
  
|<span data-ttu-id="2b991-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="2b991-106">Member</span></span>|<span data-ttu-id="2b991-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="2b991-107">Description</span></span>|  
|------------|-----------------|  
|`MAPPING_PROLOG`|<span data-ttu-id="2b991-108">El código nativo está en el prólogo, por lo que el valor de la dirección IP es 0.</span><span class="sxs-lookup"><span data-stu-id="2b991-108">The native code is in the prolog, so the value of the IP is 0.</span></span>|  
|`MAPPING_EPILOG`|<span data-ttu-id="2b991-109">El código nativo está en un epílogo, por lo que el valor de la dirección IP es la dirección de la última instrucción del método.</span><span class="sxs-lookup"><span data-stu-id="2b991-109">The native code is in an epilog, so the value of the IP is the address of the last instruction of the method.</span></span>|  
|`MAPPING_NO_INFO`|<span data-ttu-id="2b991-110">No hay información de asignación está disponible para el método, por lo que el valor de la dirección IP es 0.</span><span class="sxs-lookup"><span data-stu-id="2b991-110">No mapping information is available for the method, so the value of the IP is 0.</span></span>|  
|`MAPPING_UNMAPPED_ADDRESS`|<span data-ttu-id="2b991-111">Aunque no hay información de asignación para el método, la dirección actual no se puede asignar al código de lenguaje intermedio (MSIL) de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2b991-111">Although there is mapping information for the method, the current address cannot be mapped to Microsoft intermediate language (MSIL) code.</span></span> <span data-ttu-id="2b991-112">El valor de la dirección IP es 0.</span><span class="sxs-lookup"><span data-stu-id="2b991-112">The value of the IP is 0.</span></span>|  
|`MAPPING_EXACT`|<span data-ttu-id="2b991-113">El método se asigna exactamente a código MSIL o se ha interpretado el marco, por lo que el valor de la dirección IP es preciso.</span><span class="sxs-lookup"><span data-stu-id="2b991-113">Either the method maps exactly to MSIL code or the frame has been interpreted, so the value of the IP is accurate.</span></span>|  
|`MAPPING_APPROXIMATE`|<span data-ttu-id="2b991-114">El método se ha asignado correctamente, pero el valor de la dirección IP puede ser aproximado.</span><span class="sxs-lookup"><span data-stu-id="2b991-114">The method was successfully mapped, but the value of the IP may be approximate.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2b991-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2b991-115">Remarks</span></span>  
 <span data-ttu-id="2b991-116">Puede usar el [ICorDebugILFrame:: GetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getip-method.md) método para obtener el valor del puntero de instrucción.</span><span class="sxs-lookup"><span data-stu-id="2b991-116">You can use the [ICorDebugILFrame::GetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getip-method.md) method to obtain the value of the instruction pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b991-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2b991-117">Requirements</span></span>  
 <span data-ttu-id="2b991-118">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2b991-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b991-119">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2b991-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2b991-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2b991-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2b991-121">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b991-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b991-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="2b991-122">See Also</span></span>  
 [<span data-ttu-id="2b991-123">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="2b991-123">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
