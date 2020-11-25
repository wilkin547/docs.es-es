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
ms.openlocfilehash: 30a522fbf96aebaa96f33f4a1dc381683f183871
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726423"
---
# <a name="cor_pub_enumprocess-enumeration"></a><span data-ttu-id="ddcea-102">COR_PUB_ENUMPROCESS (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="ddcea-102">COR_PUB_ENUMPROCESS Enumeration</span></span>

<span data-ttu-id="ddcea-103">Identifica el tipo de proceso que se va a enumerar.</span><span class="sxs-lookup"><span data-stu-id="ddcea-103">Identifies the type of process to be enumerated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ddcea-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ddcea-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PUB_MANAGEDONLY    = 0x00000001  
} COR_PUB_ENUMPROCESS;  
```  
  
## <a name="members"></a><span data-ttu-id="ddcea-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="ddcea-105">Members</span></span>  
  
|<span data-ttu-id="ddcea-106">Nombre del miembro</span><span class="sxs-lookup"><span data-stu-id="ddcea-106">Member name</span></span>|<span data-ttu-id="ddcea-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="ddcea-107">Description</span></span>|  
|-----------------|-----------------|  
|`COR_PUB_MANAGEDONLY`|<span data-ttu-id="ddcea-108">Un proceso administrado.</span><span class="sxs-lookup"><span data-stu-id="ddcea-108">A managed process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ddcea-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ddcea-109">Remarks</span></span>  

 <span data-ttu-id="ddcea-110">La versión actual de la API de depuración no administrada solo enumera los procesos administrados.</span><span class="sxs-lookup"><span data-stu-id="ddcea-110">The current version of the unmanaged debugging API enumerates only managed processes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ddcea-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ddcea-111">Requirements</span></span>  

 <span data-ttu-id="ddcea-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ddcea-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ddcea-113">**Encabezado:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="ddcea-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="ddcea-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ddcea-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ddcea-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ddcea-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddcea-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ddcea-116">See also</span></span>

- [<span data-ttu-id="ddcea-117">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="ddcea-117">Debugging Enumerations</span></span>](debugging-enumerations.md)
