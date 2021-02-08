---
description: 'Más información sobre: enumeración Cordebuggctype ('
title: CorDebugGCType (Enumeración)
ms.date: 03/30/2017
api_name:
- CorDebugGCType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugGCType
helpviewer_keywords:
- CorDebugGCType enumeration [.NET Framework debugging]
ms.assetid: 880ca92a-42d4-42a5-9b9c-c2848eb39c6a
topic_type:
- apiref
ms.openlocfilehash: 4be835a9a028a882fa050991beb31d2a8dec5354
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801662"
---
# <a name="cordebuggctype-enumeration"></a><span data-ttu-id="c4e4f-103">CorDebugGCType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="c4e4f-103">CorDebugGCType Enumeration</span></span>

<span data-ttu-id="c4e4f-104">Indica si el recolector de elementos no utilizados se está ejecutando en una estación de trabajo o en un servidor.</span><span class="sxs-lookup"><span data-stu-id="c4e4f-104">Indicates whether the garbage collector is running on a workstation or a server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4e4f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c4e4f-105">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugGCType {  
    CorDebugWorkstationGC  = 0,  
    CorDebugServerGC       = ( CorDebugWorkstationGC + 1 )  
} CorDebugGCType;  
```  
  
## <a name="parameters"></a><span data-ttu-id="c4e4f-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c4e4f-106">Parameters</span></span>  
  
## <a name="members"></a><span data-ttu-id="c4e4f-107">Members</span><span class="sxs-lookup"><span data-stu-id="c4e4f-107">Members</span></span>  
  
|<span data-ttu-id="c4e4f-108">Nombre del miembro</span><span class="sxs-lookup"><span data-stu-id="c4e4f-108">Member name</span></span>|<span data-ttu-id="c4e4f-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="c4e4f-109">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebugWorkstationGC`|<span data-ttu-id="c4e4f-110">El recolector de elementos no utilizados se está ejecutando en una estación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="c4e4f-110">The garbage collector is running on a workstation.</span></span>|  
|`CorDebugServerGC`|<span data-ttu-id="c4e4f-111">El recolector de elementos no utilizados se está ejecutando en un servidor.</span><span class="sxs-lookup"><span data-stu-id="c4e4f-111">The garbage collector is running on a server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c4e4f-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c4e4f-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4e4f-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c4e4f-113">Requirements</span></span>  

 <span data-ttu-id="c4e4f-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4e4f-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4e4f-115">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c4e4f-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c4e4f-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c4e4f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c4e4f-117">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4e4f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4e4f-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="c4e4f-118">See also</span></span>

- [<span data-ttu-id="c4e4f-119">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="c4e4f-119">Debugging Enumerations</span></span>](debugging-enumerations.md)
