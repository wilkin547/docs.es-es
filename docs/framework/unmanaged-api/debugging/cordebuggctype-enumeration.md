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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e08a486089a5697b9b3bb4b52c69fda3b661a6ab
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54654755"
---
# <a name="cordebuggctype-enumeration"></a><span data-ttu-id="39403-102">CorDebugGCType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="39403-102">CorDebugGCType Enumeration</span></span>
<span data-ttu-id="39403-103">Indica si el recolector de elementos no utilizados se está ejecutando en una estación de trabajo o en un servidor.</span><span class="sxs-lookup"><span data-stu-id="39403-103">Indicates whether the garbage collector is running on a workstation or a server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39403-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="39403-104">Syntax</span></span>  
  
```  
typedef enum CorDebugGCType {  
    CorDebugWorkstationGC  = 0,  
    CorDebugServerGC       = ( CorDebugWorkstationGC + 1 )  
} CorDebugGCType;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="39403-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="39403-105">Parameters</span></span>  
  
## <a name="members"></a><span data-ttu-id="39403-106">Miembros</span><span class="sxs-lookup"><span data-stu-id="39403-106">Members</span></span>  
  
|<span data-ttu-id="39403-107">Nombre de miembro</span><span class="sxs-lookup"><span data-stu-id="39403-107">Member name</span></span>|<span data-ttu-id="39403-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="39403-108">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebugWorkstationGC`|<span data-ttu-id="39403-109">El recolector de elementos no utilizados se ejecuta en una estación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="39403-109">The garbage collector is running on a workstation.</span></span>|  
|`CorDebugServerGC`|<span data-ttu-id="39403-110">El recolector de elementos no utilizados se ejecuta en un servidor.</span><span class="sxs-lookup"><span data-stu-id="39403-110">The garbage collector is running on a server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="39403-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="39403-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39403-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="39403-112">Requirements</span></span>  
 <span data-ttu-id="39403-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="39403-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39403-114">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="39403-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="39403-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="39403-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="39403-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39403-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39403-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="39403-117">See also</span></span>
- [<span data-ttu-id="39403-118">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="39403-118">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
