---
description: 'Más información acerca de: enumeración COR_PRF_GC_REASON'
title: COR_PRF_GC_REASON (Enumeración)
ms.date: 03/30/2017
api_name:
- COR_PRF_GC_REASON
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_REASON
helpviewer_keywords:
- COR_PRF_GC_REASON enumeration [.NET Framework profiling]
ms.assetid: 72822b95-a7fb-485e-9d55-1cb016d9a458
topic_type:
- apiref
ms.openlocfilehash: f5c8201f2023e07f9bb9d540f6d5f8fca1c19419
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99648806"
---
# <a name="cor_prf_gc_reason-enumeration"></a><span data-ttu-id="63ffe-103">COR_PRF_GC_REASON (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="63ffe-103">COR_PRF_GC_REASON Enumeration</span></span>

<span data-ttu-id="63ffe-104">Indica el motivo por el que se está produciendo la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="63ffe-104">Indicates the reason that garbage collection is occurring.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63ffe-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="63ffe-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_GC_INDUCED = 1,  
    COR_PRF_GC_OTHER = 0  
} COR_PRF_GC_REASON;  
```  
  
## <a name="members"></a><span data-ttu-id="63ffe-106">Members</span><span class="sxs-lookup"><span data-stu-id="63ffe-106">Members</span></span>  
  
|<span data-ttu-id="63ffe-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="63ffe-107">Member</span></span>|<span data-ttu-id="63ffe-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="63ffe-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_INDUCED`|<span data-ttu-id="63ffe-109">Un método indujo la recolección de elementos no utilizados <xref:System.GC.Collect%2A> .</span><span class="sxs-lookup"><span data-stu-id="63ffe-109">The garbage collection was induced by a <xref:System.GC.Collect%2A> method.</span></span>|  
|`COR_PRF_GC_OTHER`|<span data-ttu-id="63ffe-110">Razón no especificada.</span><span class="sxs-lookup"><span data-stu-id="63ffe-110">The reason is unspecified.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="63ffe-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="63ffe-111">Requirements</span></span>  

 <span data-ttu-id="63ffe-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63ffe-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63ffe-113">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="63ffe-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="63ffe-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="63ffe-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="63ffe-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63ffe-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63ffe-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="63ffe-116">See also</span></span>

- [<span data-ttu-id="63ffe-117">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="63ffe-117">Profiling Enumerations</span></span>](profiling-enumerations.md)
