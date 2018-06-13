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
ms.openlocfilehash: e74f564a483d80fd6312cf015802750d48e73ca7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33404001"
---
# <a name="cordebuggctype-enumeration"></a><span data-ttu-id="cb078-102">CorDebugGCType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="cb078-102">CorDebugGCType Enumeration</span></span>
<span data-ttu-id="cb078-103">Indica si el recolector de elementos no utilizados se está ejecutando en una estación de trabajo o en un servidor.</span><span class="sxs-lookup"><span data-stu-id="cb078-103">Indicates whether the garbage collector is running on a workstation or a server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb078-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cb078-104">Syntax</span></span>  
  
```  
typedef enum CorDebugGCType {  
    CorDebugWorkstationGC  = 0,  
    CorDebugServerGC       = ( CorDebugWorkstationGC + 1 )  
} CorDebugGCType;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cb078-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cb078-105">Parameters</span></span>  
  
## <a name="members"></a><span data-ttu-id="cb078-106">Miembros</span><span class="sxs-lookup"><span data-stu-id="cb078-106">Members</span></span>  
  
|<span data-ttu-id="cb078-107">Nombre de miembro</span><span class="sxs-lookup"><span data-stu-id="cb078-107">Member name</span></span>|<span data-ttu-id="cb078-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="cb078-108">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebugWorkstationGC`|<span data-ttu-id="cb078-109">El recolector de elementos no utilizados se ejecuta en una estación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="cb078-109">The garbage collector is running on a workstation.</span></span>|  
|`CorDebugServerGC`|<span data-ttu-id="cb078-110">El recolector de elementos no utilizados se ejecuta en un servidor.</span><span class="sxs-lookup"><span data-stu-id="cb078-110">The garbage collector is running on a server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cb078-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cb078-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb078-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cb078-112">Requirements</span></span>  
 <span data-ttu-id="cb078-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cb078-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb078-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cb078-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cb078-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cb078-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cb078-116">**Versiones de .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb078-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb078-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="cb078-117">See Also</span></span>  
 [<span data-ttu-id="cb078-118">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="cb078-118">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
