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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59085901"
---
# <a name="cordebuggenerationtypes-enumeration"></a><span data-ttu-id="28a4d-102">CorDebugGenerationTypes (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="28a4d-102">CorDebugGenerationTypes Enumeration</span></span>
<span data-ttu-id="28a4d-103">Especifica la generación de una región de memoria en el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="28a4d-103">Specifies the generation of a region of memory on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28a4d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="28a4d-104">Syntax</span></span>  
  
```  
typedef enum CorDebugGenerationTypes {  
    CorDebug_Gen0 = 0,  
    CorDebug_Gen1 = 1,  
    CorDebug_Gen2 = 2,  
    CorDebug_LOH  = 3,  
} CorDebugRegionTypes;  
```  
  
## <a name="members"></a><span data-ttu-id="28a4d-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="28a4d-105">Members</span></span>  
  
|<span data-ttu-id="28a4d-106">Nombre de miembro</span><span class="sxs-lookup"><span data-stu-id="28a4d-106">Member name</span></span>|<span data-ttu-id="28a4d-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="28a4d-107">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebug_Gen0`|<span data-ttu-id="28a4d-108">Generación 0.</span><span class="sxs-lookup"><span data-stu-id="28a4d-108">Generation 0.</span></span>|  
|`CorDebug_Gen1`|<span data-ttu-id="28a4d-109">Generación 1.</span><span class="sxs-lookup"><span data-stu-id="28a4d-109">Generation 1.</span></span>|  
|`CorDebug_Gen2`|<span data-ttu-id="28a4d-110">Generación 2.</span><span class="sxs-lookup"><span data-stu-id="28a4d-110">Generation 2.</span></span>|  
|`CorDebug_LOH`|<span data-ttu-id="28a4d-111">El montón de objetos grandes.</span><span class="sxs-lookup"><span data-stu-id="28a4d-111">The large object heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="28a4d-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="28a4d-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28a4d-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="28a4d-113">Requirements</span></span>  
 <span data-ttu-id="28a4d-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="28a4d-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28a4d-115">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="28a4d-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="28a4d-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="28a4d-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="28a4d-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28a4d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28a4d-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="28a4d-118">See also</span></span>

- [<span data-ttu-id="28a4d-119">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="28a4d-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
