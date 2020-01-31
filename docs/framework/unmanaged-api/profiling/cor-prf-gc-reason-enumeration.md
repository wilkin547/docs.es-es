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
ms.openlocfilehash: ec33e55f840fe735091364ebc35cb7b7c165c10a
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867196"
---
# <a name="cor_prf_gc_reason-enumeration"></a><span data-ttu-id="b18cb-102">COR_PRF_GC_REASON (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="b18cb-102">COR_PRF_GC_REASON Enumeration</span></span>
<span data-ttu-id="b18cb-103">Indica el motivo por el que se está produciendo la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="b18cb-103">Indicates the reason that garbage collection is occurring.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b18cb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b18cb-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_GC_INDUCED = 1,  
    COR_PRF_GC_OTHER = 0  
} COR_PRF_GC_REASON;  
```  
  
## <a name="members"></a><span data-ttu-id="b18cb-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="b18cb-105">Members</span></span>  
  
|<span data-ttu-id="b18cb-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="b18cb-106">Member</span></span>|<span data-ttu-id="b18cb-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="b18cb-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_INDUCED`|<span data-ttu-id="b18cb-108">Un método <xref:System.GC.Collect%2A> indujo la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="b18cb-108">The garbage collection was induced by a <xref:System.GC.Collect%2A> method.</span></span>|  
|`COR_PRF_GC_OTHER`|<span data-ttu-id="b18cb-109">Razón no especificada.</span><span class="sxs-lookup"><span data-stu-id="b18cb-109">The reason is unspecified.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b18cb-110">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="b18cb-110">Requirements</span></span>  
 <span data-ttu-id="b18cb-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b18cb-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b18cb-112">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b18cb-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b18cb-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b18cb-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b18cb-114">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b18cb-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b18cb-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="b18cb-115">See also</span></span>

- [<span data-ttu-id="b18cb-116">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="b18cb-116">Profiling Enumerations</span></span>](profiling-enumerations.md)
