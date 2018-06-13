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
ms.openlocfilehash: 63f6ea4a348b3035a1f0b1d3e00f61f689915fa2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33450104"
---
# <a name="corprfgcreason-enumeration"></a><span data-ttu-id="14edc-102">COR_PRF_GC_REASON (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="14edc-102">COR_PRF_GC_REASON Enumeration</span></span>
<span data-ttu-id="14edc-103">Indica el motivo por el que se está produciendo la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="14edc-103">Indicates the reason that garbage collection is occurring.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14edc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="14edc-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_GC_INDUCED = 1,  
    COR_PRF_GC_OTHER = 0  
} COR_PRF_GC_REASON;  
```  
  
## <a name="members"></a><span data-ttu-id="14edc-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="14edc-105">Members</span></span>  
  
|<span data-ttu-id="14edc-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="14edc-106">Member</span></span>|<span data-ttu-id="14edc-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="14edc-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_INDUCED`|<span data-ttu-id="14edc-108">La colección de elementos no utilizados se inducida por un <xref:System.GC.Collect%2A> método.</span><span class="sxs-lookup"><span data-stu-id="14edc-108">The garbage collection was induced by a <xref:System.GC.Collect%2A> method.</span></span>|  
|`COR_PRF_GC_OTHER`|<span data-ttu-id="14edc-109">La razón no está especificada.</span><span class="sxs-lookup"><span data-stu-id="14edc-109">The reason is unspecified.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="14edc-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="14edc-110">Requirements</span></span>  
 <span data-ttu-id="14edc-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="14edc-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14edc-112">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="14edc-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="14edc-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="14edc-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="14edc-114">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14edc-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14edc-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="14edc-115">See Also</span></span>  
 [<span data-ttu-id="14edc-116">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="14edc-116">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
