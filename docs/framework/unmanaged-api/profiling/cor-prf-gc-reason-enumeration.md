---
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
ms.openlocfilehash: f41f00a9699d6fc135ca3b9c0b4b470ca0359279
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95682398"
---
# <a name="cor_prf_gc_reason-enumeration"></a><span data-ttu-id="420b2-102">COR_PRF_GC_REASON (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="420b2-102">COR_PRF_GC_REASON Enumeration</span></span>

<span data-ttu-id="420b2-103">Indica el motivo por el que se está produciendo la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="420b2-103">Indicates the reason that garbage collection is occurring.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="420b2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="420b2-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_GC_INDUCED = 1,  
    COR_PRF_GC_OTHER = 0  
} COR_PRF_GC_REASON;  
```  
  
## <a name="members"></a><span data-ttu-id="420b2-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="420b2-105">Members</span></span>  
  
|<span data-ttu-id="420b2-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="420b2-106">Member</span></span>|<span data-ttu-id="420b2-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="420b2-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_INDUCED`|<span data-ttu-id="420b2-108">Un método indujo la recolección de elementos no utilizados <xref:System.GC.Collect%2A> .</span><span class="sxs-lookup"><span data-stu-id="420b2-108">The garbage collection was induced by a <xref:System.GC.Collect%2A> method.</span></span>|  
|`COR_PRF_GC_OTHER`|<span data-ttu-id="420b2-109">Razón no especificada.</span><span class="sxs-lookup"><span data-stu-id="420b2-109">The reason is unspecified.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="420b2-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="420b2-110">Requirements</span></span>  

 <span data-ttu-id="420b2-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="420b2-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="420b2-112">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="420b2-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="420b2-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="420b2-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="420b2-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="420b2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="420b2-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="420b2-115">See also</span></span>

- [<span data-ttu-id="420b2-116">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="420b2-116">Profiling Enumerations</span></span>](profiling-enumerations.md)
