---
title: CorDebugGenerationTypes (Enumeración)
ms.date: 03/30/2017
api_name:
- CorDebugGenerationTypes
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugGenerationTypes
helpviewer_keywords:
- CorDebugGenerationTypes enumeration [.NET Framework debugging]
ms.assetid: 9f25b64f-eedd-4ae5-8b0e-cfdfb9b6c5d8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c1707a09f14fbab6150c2ecbcd188d7bf88064fa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61989669"
---
# <a name="cordebuggenerationtypes-enumeration"></a><span data-ttu-id="92170-102">CorDebugGenerationTypes (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="92170-102">CorDebugGenerationTypes Enumeration</span></span>
<span data-ttu-id="92170-103">Especifica la generación de una región de memoria en el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="92170-103">Specifies the generation of a region of memory on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92170-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="92170-104">Syntax</span></span>  
  
```  
typedef enum CorDebugGenerationTypes {  
    CorDebug_Gen0 = 0,  
    CorDebug_Gen1 = 1,  
    CorDebug_Gen2 = 2,  
    CorDebug_LOH  = 3,  
} CorDebugRegionTypes;  
```  
  
## <a name="members"></a><span data-ttu-id="92170-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="92170-105">Members</span></span>  
  
|<span data-ttu-id="92170-106">Nombre de miembro</span><span class="sxs-lookup"><span data-stu-id="92170-106">Member name</span></span>|<span data-ttu-id="92170-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="92170-107">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebug_Gen0`|<span data-ttu-id="92170-108">Generación 0.</span><span class="sxs-lookup"><span data-stu-id="92170-108">Generation 0.</span></span>|  
|`CorDebug_Gen1`|<span data-ttu-id="92170-109">Generación 1.</span><span class="sxs-lookup"><span data-stu-id="92170-109">Generation 1.</span></span>|  
|`CorDebug_Gen2`|<span data-ttu-id="92170-110">Generación 2.</span><span class="sxs-lookup"><span data-stu-id="92170-110">Generation 2.</span></span>|  
|`CorDebug_LOH`|<span data-ttu-id="92170-111">El montón de objetos grandes.</span><span class="sxs-lookup"><span data-stu-id="92170-111">The large object heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="92170-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="92170-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92170-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="92170-113">Requirements</span></span>  
 <span data-ttu-id="92170-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="92170-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92170-115">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="92170-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="92170-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="92170-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="92170-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92170-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92170-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="92170-118">See also</span></span>

- [<span data-ttu-id="92170-119">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="92170-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
