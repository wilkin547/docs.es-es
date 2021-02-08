---
description: 'Más información acerca de: enumeración COR_PUB_ENUMPROCESS'
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
ms.openlocfilehash: 66bbd08aabb9d2c93e385ed098bae54754a85b85
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801792"
---
# <a name="cor_pub_enumprocess-enumeration"></a><span data-ttu-id="6759a-103">COR_PUB_ENUMPROCESS (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="6759a-103">COR_PUB_ENUMPROCESS Enumeration</span></span>

<span data-ttu-id="6759a-104">Identifica el tipo de proceso que se va a enumerar.</span><span class="sxs-lookup"><span data-stu-id="6759a-104">Identifies the type of process to be enumerated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6759a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6759a-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PUB_MANAGEDONLY    = 0x00000001  
} COR_PUB_ENUMPROCESS;  
```  
  
## <a name="members"></a><span data-ttu-id="6759a-106">Members</span><span class="sxs-lookup"><span data-stu-id="6759a-106">Members</span></span>  
  
|<span data-ttu-id="6759a-107">Nombre del miembro</span><span class="sxs-lookup"><span data-stu-id="6759a-107">Member name</span></span>|<span data-ttu-id="6759a-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="6759a-108">Description</span></span>|  
|-----------------|-----------------|  
|`COR_PUB_MANAGEDONLY`|<span data-ttu-id="6759a-109">Un proceso administrado.</span><span class="sxs-lookup"><span data-stu-id="6759a-109">A managed process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6759a-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6759a-110">Remarks</span></span>  

 <span data-ttu-id="6759a-111">La versión actual de la API de depuración no administrada solo enumera los procesos administrados.</span><span class="sxs-lookup"><span data-stu-id="6759a-111">The current version of the unmanaged debugging API enumerates only managed processes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6759a-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6759a-112">Requirements</span></span>  

 <span data-ttu-id="6759a-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6759a-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6759a-114">**Encabezado:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="6759a-114">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="6759a-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6759a-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6759a-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6759a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6759a-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="6759a-117">See also</span></span>

- [<span data-ttu-id="6759a-118">Enumeraciones de depuración</span><span class="sxs-lookup"><span data-stu-id="6759a-118">Debugging Enumerations</span></span>](debugging-enumerations.md)
