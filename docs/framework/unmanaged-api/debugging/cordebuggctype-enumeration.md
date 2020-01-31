---
title: CorDebugGCType (enumeración)
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
ms.openlocfilehash: 6f4c96517375df4cd249b72953bf37812a498c0c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789361"
---
# <a name="cordebuggctype-enumeration"></a><span data-ttu-id="4b202-102">CorDebugGCType (enumeración)</span><span class="sxs-lookup"><span data-stu-id="4b202-102">CorDebugGCType Enumeration</span></span>
<span data-ttu-id="4b202-103">Indica si el recolector de elementos no utilizados se está ejecutando en una estación de trabajo o en un servidor.</span><span class="sxs-lookup"><span data-stu-id="4b202-103">Indicates whether the garbage collector is running on a workstation or a server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b202-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4b202-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugGCType {  
    CorDebugWorkstationGC  = 0,  
    CorDebugServerGC       = ( CorDebugWorkstationGC + 1 )  
} CorDebugGCType;  
```  
  
## <a name="parameters"></a><span data-ttu-id="4b202-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="4b202-105">Parameters</span></span>  
  
## <a name="members"></a><span data-ttu-id="4b202-106">Miembros</span><span class="sxs-lookup"><span data-stu-id="4b202-106">Members</span></span>  
  
|<span data-ttu-id="4b202-107">Nombre de miembro</span><span class="sxs-lookup"><span data-stu-id="4b202-107">Member name</span></span>|<span data-ttu-id="4b202-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="4b202-108">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebugWorkstationGC`|<span data-ttu-id="4b202-109">El recolector de elementos no utilizados se está ejecutando en una estación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="4b202-109">The garbage collector is running on a workstation.</span></span>|  
|`CorDebugServerGC`|<span data-ttu-id="4b202-110">El recolector de elementos no utilizados se está ejecutando en un servidor.</span><span class="sxs-lookup"><span data-stu-id="4b202-110">The garbage collector is running on a server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4b202-111">Notas</span><span class="sxs-lookup"><span data-stu-id="4b202-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b202-112">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="4b202-112">Requirements</span></span>  
 <span data-ttu-id="4b202-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b202-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b202-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4b202-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4b202-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4b202-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4b202-116">**.NET Framework versiones:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b202-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b202-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="4b202-117">See also</span></span>

- [<span data-ttu-id="4b202-118">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="4b202-118">Debugging Enumerations</span></span>](debugging-enumerations.md)
