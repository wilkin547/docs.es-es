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
ms.openlocfilehash: 02ff60852a85d003deb68cae96a184ac8d61c65f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59089417"
---
# <a name="corpubenumprocess-enumeration"></a><span data-ttu-id="636dc-102">COR_PUB_ENUMPROCESS (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="636dc-102">COR_PUB_ENUMPROCESS Enumeration</span></span>
<span data-ttu-id="636dc-103">Identifica el tipo de proceso que se va a enumerar.</span><span class="sxs-lookup"><span data-stu-id="636dc-103">Identifies the type of process to be enumerated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="636dc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="636dc-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PUB_MANAGEDONLY    = 0x00000001  
} COR_PUB_ENUMPROCESS;  
```  
  
## <a name="members"></a><span data-ttu-id="636dc-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="636dc-105">Members</span></span>  
  
|<span data-ttu-id="636dc-106">Nombre de miembro</span><span class="sxs-lookup"><span data-stu-id="636dc-106">Member name</span></span>|<span data-ttu-id="636dc-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="636dc-107">Description</span></span>|  
|-----------------|-----------------|  
|`COR_PUB_MANAGEDONLY`|<span data-ttu-id="636dc-108">Un proceso administrado.</span><span class="sxs-lookup"><span data-stu-id="636dc-108">A managed process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="636dc-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="636dc-109">Remarks</span></span>  
 <span data-ttu-id="636dc-110">La versión actual de la API de depuración no administrada enumera sólo los procesos administrados.</span><span class="sxs-lookup"><span data-stu-id="636dc-110">The current version of the unmanaged debugging API enumerates only managed processes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="636dc-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="636dc-111">Requirements</span></span>  
 <span data-ttu-id="636dc-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="636dc-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="636dc-113">**Encabezado**: CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="636dc-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="636dc-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="636dc-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="636dc-115">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="636dc-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="636dc-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="636dc-116">See also</span></span>

- [<span data-ttu-id="636dc-117">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="636dc-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
