---
title: COR_PUB_ENUMPROCESS (Enumeración)
ms.date: 03/30/2017
api_name:
- COR_PUB_ENUMPROCESS
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_PUB_ENUMPROCESS
helpviewer_keywords:
- COR_PUB_ENUMPROCESS enumeration [.NET Framework debugging]
ms.assetid: 5d3ada6e-feea-47da-a7ed-b664107c137f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fcdb5883e109d7e0c73c8fb76ee61b52cf23091f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33407006"
---
# <a name="corpubenumprocess-enumeration"></a><span data-ttu-id="d2cb5-102">COR_PUB_ENUMPROCESS (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="d2cb5-102">COR_PUB_ENUMPROCESS Enumeration</span></span>
<span data-ttu-id="d2cb5-103">Identifica el tipo de proceso que se va a enumerar.</span><span class="sxs-lookup"><span data-stu-id="d2cb5-103">Identifies the type of process to be enumerated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2cb5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d2cb5-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PUB_MANAGEDONLY    = 0x00000001  
} COR_PUB_ENUMPROCESS;  
```  
  
## <a name="members"></a><span data-ttu-id="d2cb5-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="d2cb5-105">Members</span></span>  
  
|<span data-ttu-id="d2cb5-106">Nombre de miembro</span><span class="sxs-lookup"><span data-stu-id="d2cb5-106">Member name</span></span>|<span data-ttu-id="d2cb5-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="d2cb5-107">Description</span></span>|  
|-----------------|-----------------|  
|`COR_PUB_MANAGEDONLY`|<span data-ttu-id="d2cb5-108">Un proceso administrado.</span><span class="sxs-lookup"><span data-stu-id="d2cb5-108">A managed process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d2cb5-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d2cb5-109">Remarks</span></span>  
 <span data-ttu-id="d2cb5-110">La versión actual de la API de depuración no administrada enumera sólo los procesos administrados.</span><span class="sxs-lookup"><span data-stu-id="d2cb5-110">The current version of the unmanaged debugging API enumerates only managed processes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2cb5-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d2cb5-111">Requirements</span></span>  
 <span data-ttu-id="d2cb5-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d2cb5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2cb5-113">**Encabezado:** Cordebug.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="d2cb5-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="d2cb5-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d2cb5-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d2cb5-115">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2cb5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2cb5-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="d2cb5-116">See Also</span></span>  
 [<span data-ttu-id="d2cb5-117">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="d2cb5-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
