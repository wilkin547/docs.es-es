---
title: "COR_PRF_MISC (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_MISC
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_MISC
helpviewer_keywords: COR_PRF_MISC enumeration [.NET Framework profiling]
ms.assetid: 619bb5de-e309-48b6-a3af-32d935a0ff46
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: da858ecf9fc002061d663e8c8f4d4036ef134d5a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="corprfmisc-enumeration"></a><span data-ttu-id="db2fd-102">COR_PRF_MISC (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="db2fd-102">COR_PRF_MISC Enumeration</span></span>
<span data-ttu-id="db2fd-103">Contiene valores constantes que especifican identificadores especiales.</span><span class="sxs-lookup"><span data-stu-id="db2fd-103">Contains constant values that specify special identifiers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db2fd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="db2fd-104">Syntax</span></span>  
  
```  
typedef enum {  
    PROFILER_PARENT_UNKNOWN = 0xFFFFFFFD,  
    PROFILER_GLOBAL_CLASS   = 0xFFFFFFFE,  
    PROFILER_GLOBAL_MODULE  = 0xFFFFFFFF  
} COR_PRF_MISC;  
```  
  
## <a name="members"></a><span data-ttu-id="db2fd-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="db2fd-105">Members</span></span>  
  
|<span data-ttu-id="db2fd-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="db2fd-106">Member</span></span>|<span data-ttu-id="db2fd-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="db2fd-107">Description</span></span>|  
|------------|-----------------|  
|`PROFILER_PARENT_UNKNOWN`|<span data-ttu-id="db2fd-108">El identificador predeterminado utilizado por [ICorProfilerInfo:: GetModuleInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmoduleinfo-method.md) para un módulo que aún no se ha adjuntado a un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="db2fd-108">The default identifier used by [ICorProfilerInfo::GetModuleInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmoduleinfo-method.md) for a module that has not yet been attached to an assembly.</span></span>|  
|`PROFILER_GLOBAL_CLASS`|<span data-ttu-id="db2fd-109">El identificador de clase predeterminado para las constantes globales que no pertenecen a una clase.</span><span class="sxs-lookup"><span data-stu-id="db2fd-109">The default class identifier for global constants that do not belong to a class.</span></span>|  
|`PROFILER_GLOBAL_MODULE`|<span data-ttu-id="db2fd-110">Identificador del módulo predeterminado para los objetos globales que no pertenecen a un módulo.</span><span class="sxs-lookup"><span data-stu-id="db2fd-110">The default module identifier for global objects that do not belong to a module.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="db2fd-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="db2fd-111">Requirements</span></span>  
 <span data-ttu-id="db2fd-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db2fd-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db2fd-113">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="db2fd-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="db2fd-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="db2fd-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="db2fd-115">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db2fd-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db2fd-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="db2fd-116">See Also</span></span>  
 [<span data-ttu-id="db2fd-117">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="db2fd-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
