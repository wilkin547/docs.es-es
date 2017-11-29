---
title: "COR_PRF_GC_REASON (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_GC_REASON
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_GC_REASON
helpviewer_keywords: COR_PRF_GC_REASON enumeration [.NET Framework profiling]
ms.assetid: 72822b95-a7fb-485e-9d55-1cb016d9a458
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 7a5797c3e629bc87caf40b187bba47bc1cffbfdf
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="corprfgcreason-enumeration"></a><span data-ttu-id="8a110-102">COR_PRF_GC_REASON (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="8a110-102">COR_PRF_GC_REASON Enumeration</span></span>
<span data-ttu-id="8a110-103">Indica el motivo por el que se está produciendo la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="8a110-103">Indicates the reason that garbage collection is occurring.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a110-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8a110-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_GC_INDUCED = 1,  
    COR_PRF_GC_OTHER = 0  
} COR_PRF_GC_REASON;  
```  
  
## <a name="members"></a><span data-ttu-id="8a110-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="8a110-105">Members</span></span>  
  
|<span data-ttu-id="8a110-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="8a110-106">Member</span></span>|<span data-ttu-id="8a110-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="8a110-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_GC_INDUCED`|<span data-ttu-id="8a110-108">La colección de elementos no utilizados se inducida por un <xref:System.GC.Collect%2A> método.</span><span class="sxs-lookup"><span data-stu-id="8a110-108">The garbage collection was induced by a <xref:System.GC.Collect%2A> method.</span></span>|  
|`COR_PRF_GC_OTHER`|<span data-ttu-id="8a110-109">La razón no está especificada.</span><span class="sxs-lookup"><span data-stu-id="8a110-109">The reason is unspecified.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8a110-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8a110-110">Requirements</span></span>  
 <span data-ttu-id="8a110-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a110-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a110-112">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8a110-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8a110-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8a110-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8a110-114">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a110-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a110-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="8a110-115">See Also</span></span>  
 [<span data-ttu-id="8a110-116">Enumeraciones de generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="8a110-116">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
