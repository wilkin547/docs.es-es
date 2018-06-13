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
ms.openlocfilehash: 563c1fccd0b1fd254d721f631b0c8312b3b09bbd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402436"
---
# <a name="cordebuggenerationtypes-enumeration"></a><span data-ttu-id="1ee5f-102">CorDebugGenerationTypes (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="1ee5f-102">CorDebugGenerationTypes Enumeration</span></span>
<span data-ttu-id="1ee5f-103">Especifica la generación de una región de memoria en el montón administrado.</span><span class="sxs-lookup"><span data-stu-id="1ee5f-103">Specifies the generation of a region of memory on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ee5f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1ee5f-104">Syntax</span></span>  
  
```  
typedef enum CorDebugGenerationTypes {  
    CorDebug_Gen0 = 0,  
    CorDebug_Gen1 = 1,  
    CorDebug_Gen2 = 2,  
    CorDebug_LOH  = 3,  
} CorDebugRegionTypes;  
```  
  
## <a name="members"></a><span data-ttu-id="1ee5f-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="1ee5f-105">Members</span></span>  
  
|<span data-ttu-id="1ee5f-106">Nombre de miembro</span><span class="sxs-lookup"><span data-stu-id="1ee5f-106">Member name</span></span>|<span data-ttu-id="1ee5f-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="1ee5f-107">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebug_Gen0`|<span data-ttu-id="1ee5f-108">Generación 0.</span><span class="sxs-lookup"><span data-stu-id="1ee5f-108">Generation 0.</span></span>|  
|`CorDebug_Gen1`|<span data-ttu-id="1ee5f-109">Generación 1.</span><span class="sxs-lookup"><span data-stu-id="1ee5f-109">Generation 1.</span></span>|  
|`CorDebug_Gen2`|<span data-ttu-id="1ee5f-110">Generación 2.</span><span class="sxs-lookup"><span data-stu-id="1ee5f-110">Generation 2.</span></span>|  
|`CorDebug_LOH`|<span data-ttu-id="1ee5f-111">El montón de objetos grandes.</span><span class="sxs-lookup"><span data-stu-id="1ee5f-111">The large object heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1ee5f-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1ee5f-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ee5f-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1ee5f-113">Requirements</span></span>  
 <span data-ttu-id="1ee5f-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1ee5f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ee5f-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1ee5f-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1ee5f-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1ee5f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1ee5f-117">**Versiones de .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ee5f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ee5f-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="1ee5f-118">See Also</span></span>  
 [<span data-ttu-id="1ee5f-119">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="1ee5f-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
