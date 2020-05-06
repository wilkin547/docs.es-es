---
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
ms.openlocfilehash: 8dd070d2c895a94ac996be81e672bd67f59b83b7
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795903"
---
# <a name="cordebuggctype-enumeration"></a><span data-ttu-id="15143-102">CorDebugGCType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="15143-102">CorDebugGCType Enumeration</span></span>
<span data-ttu-id="15143-103">Indica si el recolector de elementos no utilizados se está ejecutando en una estación de trabajo o en un servidor.</span><span class="sxs-lookup"><span data-stu-id="15143-103">Indicates whether the garbage collector is running on a workstation or a server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15143-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="15143-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugGCType {  
    CorDebugWorkstationGC  = 0,  
    CorDebugServerGC       = ( CorDebugWorkstationGC + 1 )  
} CorDebugGCType;  
```  
  
## <a name="parameters"></a><span data-ttu-id="15143-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="15143-105">Parameters</span></span>  
  
## <a name="members"></a><span data-ttu-id="15143-106">Members</span><span class="sxs-lookup"><span data-stu-id="15143-106">Members</span></span>  
  
|<span data-ttu-id="15143-107">Nombre del miembro</span><span class="sxs-lookup"><span data-stu-id="15143-107">Member name</span></span>|<span data-ttu-id="15143-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="15143-108">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebugWorkstationGC`|<span data-ttu-id="15143-109">El recolector de elementos no utilizados se está ejecutando en una estación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="15143-109">The garbage collector is running on a workstation.</span></span>|  
|`CorDebugServerGC`|<span data-ttu-id="15143-110">El recolector de elementos no utilizados se está ejecutando en un servidor.</span><span class="sxs-lookup"><span data-stu-id="15143-110">The garbage collector is running on a server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="15143-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="15143-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15143-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="15143-112">Requirements</span></span>  
 <span data-ttu-id="15143-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15143-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15143-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="15143-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="15143-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="15143-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="15143-116">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15143-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15143-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="15143-117">See also</span></span>

- [<span data-ttu-id="15143-118">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="15143-118">Debugging Enumerations</span></span>](debugging-enumerations.md)
