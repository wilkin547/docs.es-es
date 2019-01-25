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
ms.openlocfilehash: bfc576e1b4f0bf1666dcd585a24dbfa398e9abde
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54715860"
---
# <a name="corpubenumprocess-enumeration"></a><span data-ttu-id="4ad94-102">COR_PUB_ENUMPROCESS (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="4ad94-102">COR_PUB_ENUMPROCESS Enumeration</span></span>
<span data-ttu-id="4ad94-103">Identifica el tipo de proceso que se va a enumerar.</span><span class="sxs-lookup"><span data-stu-id="4ad94-103">Identifies the type of process to be enumerated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ad94-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4ad94-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PUB_MANAGEDONLY    = 0x00000001  
} COR_PUB_ENUMPROCESS;  
```  
  
## <a name="members"></a><span data-ttu-id="4ad94-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="4ad94-105">Members</span></span>  
  
|<span data-ttu-id="4ad94-106">Nombre de miembro</span><span class="sxs-lookup"><span data-stu-id="4ad94-106">Member name</span></span>|<span data-ttu-id="4ad94-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="4ad94-107">Description</span></span>|  
|-----------------|-----------------|  
|`COR_PUB_MANAGEDONLY`|<span data-ttu-id="4ad94-108">Un proceso administrado.</span><span class="sxs-lookup"><span data-stu-id="4ad94-108">A managed process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4ad94-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4ad94-109">Remarks</span></span>  
 <span data-ttu-id="4ad94-110">La versión actual de la API de depuración no administrada enumera sólo los procesos administrados.</span><span class="sxs-lookup"><span data-stu-id="4ad94-110">The current version of the unmanaged debugging API enumerates only managed processes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ad94-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4ad94-111">Requirements</span></span>  
 <span data-ttu-id="4ad94-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4ad94-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ad94-113">**Encabezado**: CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="4ad94-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="4ad94-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4ad94-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4ad94-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ad94-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ad94-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="4ad94-116">See also</span></span>
- [<span data-ttu-id="4ad94-117">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="4ad94-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
