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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4f5a596608719889e6440e5cd42dafb82abaa074
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67753728"
---
# <a name="corprfgcreason-enumeration"></a><span data-ttu-id="b2f32-102">COR_PRF_GC_REASON (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="b2f32-102">COR_PRF_GC_REASON Enumeration</span></span>
<span data-ttu-id="b2f32-103">Indica el motivo por el que se está produciendo la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="b2f32-103">Indicates the reason that garbage collection is occurring.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2f32-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b2f32-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_GC_INDUCED = 1,  
    COR_PRF_GC_OTHER = 0  
} COR_PRF_GC_REASON;  
```  
  
## <a name="members"></a><span data-ttu-id="b2f32-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="b2f32-105">Members</span></span>  
  
|<span data-ttu-id="b2f32-106">Member</span><span class="sxs-lookup"><span data-stu-id="b2f32-106">Member</span></span>|<span data-ttu-id="b2f32-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="b2f32-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_INDUCED`|<span data-ttu-id="b2f32-108">Indujo la recolección de elementos mediante un <xref:System.GC.Collect%2A> método.</span><span class="sxs-lookup"><span data-stu-id="b2f32-108">The garbage collection was induced by a <xref:System.GC.Collect%2A> method.</span></span>|  
|`COR_PRF_GC_OTHER`|<span data-ttu-id="b2f32-109">No se especifica el motivo.</span><span class="sxs-lookup"><span data-stu-id="b2f32-109">The reason is unspecified.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b2f32-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b2f32-110">Requirements</span></span>  
 <span data-ttu-id="b2f32-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2f32-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2f32-112">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b2f32-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b2f32-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b2f32-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b2f32-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2f32-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2f32-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="b2f32-115">See also</span></span>

- [<span data-ttu-id="b2f32-116">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="b2f32-116">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
