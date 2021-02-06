---
description: 'Más información sobre: enumeración Cordebuggenerationtypes ('
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
ms.openlocfilehash: f86b2bc9bf947c6b285c50678f46494005bb5537
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99662135"
---
# <a name="cordebuggenerationtypes-enumeration"></a><span data-ttu-id="2cbe3-103">CorDebugGenerationTypes (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="2cbe3-103">CorDebugGenerationTypes Enumeration</span></span>

<span data-ttu-id="2cbe3-104">Especifica la generación de una región de memoria en el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="2cbe3-104">Specifies the generation of a region of memory on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2cbe3-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2cbe3-105">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugGenerationTypes {  
    CorDebug_Gen0 = 0,  
    CorDebug_Gen1 = 1,  
    CorDebug_Gen2 = 2,  
    CorDebug_LOH  = 3,  
} CorDebugRegionTypes;  
```  
  
## <a name="members"></a><span data-ttu-id="2cbe3-106">Members</span><span class="sxs-lookup"><span data-stu-id="2cbe3-106">Members</span></span>  
  
|<span data-ttu-id="2cbe3-107">Nombre del miembro</span><span class="sxs-lookup"><span data-stu-id="2cbe3-107">Member name</span></span>|<span data-ttu-id="2cbe3-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="2cbe3-108">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebug_Gen0`|<span data-ttu-id="2cbe3-109">Generación 0.</span><span class="sxs-lookup"><span data-stu-id="2cbe3-109">Generation 0.</span></span>|  
|`CorDebug_Gen1`|<span data-ttu-id="2cbe3-110">Generación 1</span><span class="sxs-lookup"><span data-stu-id="2cbe3-110">Generation 1.</span></span>|  
|`CorDebug_Gen2`|<span data-ttu-id="2cbe3-111">Generación 2.</span><span class="sxs-lookup"><span data-stu-id="2cbe3-111">Generation 2.</span></span>|  
|`CorDebug_LOH`|<span data-ttu-id="2cbe3-112">Montón de objetos grandes.</span><span class="sxs-lookup"><span data-stu-id="2cbe3-112">The large object heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2cbe3-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2cbe3-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2cbe3-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2cbe3-114">Requirements</span></span>  

 <span data-ttu-id="2cbe3-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2cbe3-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2cbe3-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2cbe3-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2cbe3-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2cbe3-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2cbe3-118">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2cbe3-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cbe3-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="2cbe3-119">See also</span></span>

- [<span data-ttu-id="2cbe3-120">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="2cbe3-120">Debugging Enumerations</span></span>](debugging-enumerations.md)
