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
ms.openlocfilehash: b954aa0e4db10fd4b3bde951c7f27d18b8634f5a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132185"
---
# <a name="cordebuggctype-enumeration"></a><span data-ttu-id="c0175-102">CorDebugGCType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="c0175-102">CorDebugGCType Enumeration</span></span>
<span data-ttu-id="c0175-103">Indica si el recolector de elementos no utilizados se está ejecutando en una estación de trabajo o en un servidor.</span><span class="sxs-lookup"><span data-stu-id="c0175-103">Indicates whether the garbage collector is running on a workstation or a server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0175-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c0175-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugGCType {  
    CorDebugWorkstationGC  = 0,  
    CorDebugServerGC       = ( CorDebugWorkstationGC + 1 )  
} CorDebugGCType;  
```  
  
## <a name="parameters"></a><span data-ttu-id="c0175-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c0175-105">Parameters</span></span>  
  
## <a name="members"></a><span data-ttu-id="c0175-106">Miembros</span><span class="sxs-lookup"><span data-stu-id="c0175-106">Members</span></span>  
  
|<span data-ttu-id="c0175-107">Nombre de miembro</span><span class="sxs-lookup"><span data-stu-id="c0175-107">Member name</span></span>|<span data-ttu-id="c0175-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="c0175-108">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebugWorkstationGC`|<span data-ttu-id="c0175-109">El recolector de elementos no utilizados se está ejecutando en una estación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="c0175-109">The garbage collector is running on a workstation.</span></span>|  
|`CorDebugServerGC`|<span data-ttu-id="c0175-110">El recolector de elementos no utilizados se está ejecutando en un servidor.</span><span class="sxs-lookup"><span data-stu-id="c0175-110">The garbage collector is running on a server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c0175-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c0175-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0175-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c0175-112">Requirements</span></span>  
 <span data-ttu-id="c0175-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c0175-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0175-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c0175-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c0175-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c0175-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c0175-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0175-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0175-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="c0175-117">See also</span></span>

- [<span data-ttu-id="c0175-118">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="c0175-118">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
