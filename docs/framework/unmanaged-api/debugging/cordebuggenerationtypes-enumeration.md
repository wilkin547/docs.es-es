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
ms.openlocfilehash: 362e917e1684c91bde80a8b5c2e6a27a18a99190
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73098197"
---
# <a name="cordebuggenerationtypes-enumeration"></a><span data-ttu-id="0b6f6-102">CorDebugGenerationTypes (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="0b6f6-102">CorDebugGenerationTypes Enumeration</span></span>
<span data-ttu-id="0b6f6-103">Especifica la generación de una región de memoria en el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="0b6f6-103">Specifies the generation of a region of memory on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b6f6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0b6f6-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugGenerationTypes {  
    CorDebug_Gen0 = 0,  
    CorDebug_Gen1 = 1,  
    CorDebug_Gen2 = 2,  
    CorDebug_LOH  = 3,  
} CorDebugRegionTypes;  
```  
  
## <a name="members"></a><span data-ttu-id="0b6f6-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="0b6f6-105">Members</span></span>  
  
|<span data-ttu-id="0b6f6-106">Nombre de miembro</span><span class="sxs-lookup"><span data-stu-id="0b6f6-106">Member name</span></span>|<span data-ttu-id="0b6f6-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="0b6f6-107">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebug_Gen0`|<span data-ttu-id="0b6f6-108">Generación 0.</span><span class="sxs-lookup"><span data-stu-id="0b6f6-108">Generation 0.</span></span>|  
|`CorDebug_Gen1`|<span data-ttu-id="0b6f6-109">Generación 1.</span><span class="sxs-lookup"><span data-stu-id="0b6f6-109">Generation 1.</span></span>|  
|`CorDebug_Gen2`|<span data-ttu-id="0b6f6-110">Generación 2.</span><span class="sxs-lookup"><span data-stu-id="0b6f6-110">Generation 2.</span></span>|  
|`CorDebug_LOH`|<span data-ttu-id="0b6f6-111">Montón de objetos grandes.</span><span class="sxs-lookup"><span data-stu-id="0b6f6-111">The large object heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0b6f6-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0b6f6-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b6f6-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0b6f6-113">Requirements</span></span>  
 <span data-ttu-id="0b6f6-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0b6f6-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b6f6-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0b6f6-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0b6f6-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0b6f6-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0b6f6-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b6f6-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b6f6-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="0b6f6-118">See also</span></span>

- [<span data-ttu-id="0b6f6-119">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="0b6f6-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
