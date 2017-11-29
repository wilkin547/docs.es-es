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
ms.openlocfilehash: 75e740a6ca17135a3de2e945e205f4581b2f32e0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="corprfmisc-enumeration"></a><span data-ttu-id="9d6ad-102">COR_PRF_MISC (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="9d6ad-102">COR_PRF_MISC Enumeration</span></span>
<span data-ttu-id="9d6ad-103">Contiene valores constantes que especifican identificadores especiales.</span><span class="sxs-lookup"><span data-stu-id="9d6ad-103">Contains constant values that specify special identifiers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d6ad-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9d6ad-104">Syntax</span></span>  
  
```  
typedef enum {  
    PROFILER_PARENT_UNKNOWN = 0xFFFFFFFD,  
    PROFILER_GLOBAL_CLASS   = 0xFFFFFFFE,  
    PROFILER_GLOBAL_MODULE  = 0xFFFFFFFF  
} COR_PRF_MISC;  
```  
  
## <a name="members"></a><span data-ttu-id="9d6ad-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="9d6ad-105">Members</span></span>  
  
|<span data-ttu-id="9d6ad-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="9d6ad-106">Member</span></span>|<span data-ttu-id="9d6ad-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="9d6ad-107">Description</span></span>|  
|------------|-----------------|  
|`PROFILER_PARENT_UNKNOWN`|<span data-ttu-id="9d6ad-108">El identificador predeterminado utilizado por [ICorProfilerInfo:: GetModuleInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmoduleinfo-method.md) para un módulo que aún no se ha adjuntado a un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="9d6ad-108">The default identifier used by [ICorProfilerInfo::GetModuleInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmoduleinfo-method.md) for a module that has not yet been attached to an assembly.</span></span>|  
|`PROFILER_GLOBAL_CLASS`|<span data-ttu-id="9d6ad-109">El identificador de clase predeterminado para las constantes globales que no pertenecen a una clase.</span><span class="sxs-lookup"><span data-stu-id="9d6ad-109">The default class identifier for global constants that do not belong to a class.</span></span>|  
|`PROFILER_GLOBAL_MODULE`|<span data-ttu-id="9d6ad-110">Identificador del módulo predeterminado para los objetos globales que no pertenecen a un módulo.</span><span class="sxs-lookup"><span data-stu-id="9d6ad-110">The default module identifier for global objects that do not belong to a module.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9d6ad-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9d6ad-111">Requirements</span></span>  
 <span data-ttu-id="9d6ad-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9d6ad-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d6ad-113">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9d6ad-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9d6ad-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9d6ad-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9d6ad-115">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d6ad-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d6ad-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="9d6ad-116">See Also</span></span>  
 [<span data-ttu-id="9d6ad-117">Enumeraciones de generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="9d6ad-117">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
