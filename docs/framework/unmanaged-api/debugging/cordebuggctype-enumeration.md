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
ms.openlocfilehash: 6b3075613af0403527ecf67d574c0f5733a5cd8b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712617"
---
# <a name="cordebuggctype-enumeration"></a><span data-ttu-id="2aa57-102">CorDebugGCType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="2aa57-102">CorDebugGCType Enumeration</span></span>

<span data-ttu-id="2aa57-103">Indica si el recolector de elementos no utilizados se está ejecutando en una estación de trabajo o en un servidor.</span><span class="sxs-lookup"><span data-stu-id="2aa57-103">Indicates whether the garbage collector is running on a workstation or a server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2aa57-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2aa57-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugGCType {  
    CorDebugWorkstationGC  = 0,  
    CorDebugServerGC       = ( CorDebugWorkstationGC + 1 )  
} CorDebugGCType;  
```  
  
## <a name="parameters"></a><span data-ttu-id="2aa57-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2aa57-105">Parameters</span></span>  
  
## <a name="members"></a><span data-ttu-id="2aa57-106">Miembros</span><span class="sxs-lookup"><span data-stu-id="2aa57-106">Members</span></span>  
  
|<span data-ttu-id="2aa57-107">Nombre del miembro</span><span class="sxs-lookup"><span data-stu-id="2aa57-107">Member name</span></span>|<span data-ttu-id="2aa57-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="2aa57-108">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebugWorkstationGC`|<span data-ttu-id="2aa57-109">El recolector de elementos no utilizados se está ejecutando en una estación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2aa57-109">The garbage collector is running on a workstation.</span></span>|  
|`CorDebugServerGC`|<span data-ttu-id="2aa57-110">El recolector de elementos no utilizados se está ejecutando en un servidor.</span><span class="sxs-lookup"><span data-stu-id="2aa57-110">The garbage collector is running on a server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2aa57-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2aa57-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2aa57-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2aa57-112">Requirements</span></span>  

 <span data-ttu-id="2aa57-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2aa57-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2aa57-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2aa57-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2aa57-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2aa57-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2aa57-116">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2aa57-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2aa57-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2aa57-117">See also</span></span>

- [<span data-ttu-id="2aa57-118">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="2aa57-118">Debugging Enumerations</span></span>](debugging-enumerations.md)
